---
ms.date: 06/12/2017
title: WMF 5.1 中的 PowerShell 引擎改进
description: 本文列出了 Windows PowerShell 5.1 中的性能改进
ms.openlocfilehash: 34a4ed1ae4b00f5763848deaf2edad895e70c59a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655858"
---
# <a name="powershell-engine-improvements"></a><span data-ttu-id="50abc-103">PowerShell 引擎改进</span><span class="sxs-lookup"><span data-stu-id="50abc-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="50abc-104">在 WMF 5.1 中，实现了针对核心 PowerShell 引擎的以下改进：</span><span class="sxs-lookup"><span data-stu-id="50abc-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>

## <a name="performance"></a><span data-ttu-id="50abc-105">性能</span><span class="sxs-lookup"><span data-stu-id="50abc-105">Performance</span></span>

<span data-ttu-id="50abc-106">性能在一些重要方面得到了改进：</span><span class="sxs-lookup"><span data-stu-id="50abc-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="50abc-107">启动</span><span class="sxs-lookup"><span data-stu-id="50abc-107">Startup</span></span>
- <span data-ttu-id="50abc-108">cmdlet 的流水线操作（例如，`ForEach-Object` 和 `Where-Object`）提速约 50%</span><span class="sxs-lookup"><span data-stu-id="50abc-108">Pipelining to cmdlets like `ForEach-Object` and `Where-Object` is approximately 50% faster</span></span>

<span data-ttu-id="50abc-109">一些示例改进（结果可能因你的硬件而异）：</span><span class="sxs-lookup"><span data-stu-id="50abc-109">Some example improvements (your results may vary depending on your hardware):</span></span>

| <span data-ttu-id="50abc-110">场景</span><span class="sxs-lookup"><span data-stu-id="50abc-110">Scenario</span></span> | <span data-ttu-id="50abc-111">5.0 时间（毫秒）</span><span class="sxs-lookup"><span data-stu-id="50abc-111">5.0 Time (ms)</span></span> | <span data-ttu-id="50abc-112">5.1 时间（毫秒）</span><span class="sxs-lookup"><span data-stu-id="50abc-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="50abc-113">900</span><span class="sxs-lookup"><span data-stu-id="50abc-113">900</span></span> | <span data-ttu-id="50abc-114">250</span><span class="sxs-lookup"><span data-stu-id="50abc-114">250</span></span> |
| <span data-ttu-id="50abc-115">PowerShell 首次运行：`powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="50abc-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="50abc-116">30000</span><span class="sxs-lookup"><span data-stu-id="50abc-116">30000</span></span> | <span data-ttu-id="50abc-117">13000</span><span class="sxs-lookup"><span data-stu-id="50abc-117">13000</span></span> |
| <span data-ttu-id="50abc-118">构建的命令分析缓存：`powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="50abc-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="50abc-119">7000</span><span class="sxs-lookup"><span data-stu-id="50abc-119">7000</span></span> | <span data-ttu-id="50abc-120">520</span><span class="sxs-lookup"><span data-stu-id="50abc-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="50abc-121">1400</span><span class="sxs-lookup"><span data-stu-id="50abc-121">1400</span></span> | <span data-ttu-id="50abc-122">750</span><span class="sxs-lookup"><span data-stu-id="50abc-122">750</span></span> |

> [!NOTE]
> <span data-ttu-id="50abc-123">与启动相关的一个更改可能会影响某些不支持的方案。</span><span class="sxs-lookup"><span data-stu-id="50abc-123">One change related to startup might impact some unsupported scenarios.</span></span> <span data-ttu-id="50abc-124">PowerShell 不再读取文件 `$pshome\*.ps1xml` -- 这些文件已转换为 C#，以避免处理 XML 文件的某些文件和 CPU 开销。</span><span class="sxs-lookup"><span data-stu-id="50abc-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span> <span data-ttu-id="50abc-125">这些文件仍存在，以同时支持 V2，因此如果更改文件内容，则不会对 V5 产生任何影响，只会影响 V2。</span><span class="sxs-lookup"><span data-stu-id="50abc-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span> <span data-ttu-id="50abc-126">请注意，更改这些文件的内容从来都不是受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="50abc-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="50abc-127">另一个显著更改是 PowerShell 如何为系统上安装的模块缓存导出的命令和其他信息。</span><span class="sxs-lookup"><span data-stu-id="50abc-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span> <span data-ttu-id="50abc-128">以前，此缓存存储在目录 `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis` 中。</span><span class="sxs-lookup"><span data-stu-id="50abc-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span> <span data-ttu-id="50abc-129">在 WMF 5.1 中，此缓存是单个文件 `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`。</span><span class="sxs-lookup"><span data-stu-id="50abc-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="50abc-130">有关详细信息，请参阅[模块分析缓存](release-notes.md#module-analysis-cache)。</span><span class="sxs-lookup"><span data-stu-id="50abc-130">See [Module Analysis Cache](release-notes.md#module-analysis-cache) for more details.</span></span>
