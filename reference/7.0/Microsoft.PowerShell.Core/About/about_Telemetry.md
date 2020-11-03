---
description: 描述在 PowerShell 中收集的遥测数据以及如何选择退出。
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 4aeab828d66d1f015946051419facd81ce2b78c1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199563"
---
# <a name="about-telemetry"></a><span data-ttu-id="48033-104">关于遥测</span><span class="sxs-lookup"><span data-stu-id="48033-104">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="48033-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="48033-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="48033-106">描述在 PowerShell 中收集的遥测数据以及如何选择退出。</span><span class="sxs-lookup"><span data-stu-id="48033-106">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="48033-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="48033-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="48033-108">PowerShell 将基本遥测数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="48033-108">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="48033-109">此数据帮助我们更好地了解使用 PowerShell 的环境，并能确定新功能和修复的优先级。</span><span class="sxs-lookup"><span data-stu-id="48033-109">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="48033-110">记录以下遥测点：</span><span class="sxs-lookup"><span data-stu-id="48033-110">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="48033-111">PowerShell 计数按类型 (API vs console) </span><span class="sxs-lookup"><span data-stu-id="48033-111">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="48033-112">唯一 PowerShell 使用计数</span><span class="sxs-lookup"><span data-stu-id="48033-112">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="48033-113">以下执行类型的计数：</span><span class="sxs-lookup"><span data-stu-id="48033-113">Count of the following execution types:</span></span>
  - <span data-ttu-id="48033-114">应用程序 (本机命令) </span><span class="sxs-lookup"><span data-stu-id="48033-114">Application (native commands)</span></span>
  - <span data-ttu-id="48033-115">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="48033-115">ExternalScript</span></span>
  - <span data-ttu-id="48033-116">脚本</span><span class="sxs-lookup"><span data-stu-id="48033-116">Script</span></span>
  - <span data-ttu-id="48033-117">函数</span><span class="sxs-lookup"><span data-stu-id="48033-117">Function</span></span>
  - <span data-ttu-id="48033-118">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="48033-118">Cmdlet</span></span>
- <span data-ttu-id="48033-119">已启用的 Microsoft 拥有的实验功能或 PowerShell 随附的实验功能的计数</span><span class="sxs-lookup"><span data-stu-id="48033-119">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="48033-120">托管会话计数</span><span class="sxs-lookup"><span data-stu-id="48033-120">Count of hosted sessions</span></span>
- <span data-ttu-id="48033-121">已加载的 Microsoft 拥有的模块计数</span><span class="sxs-lookup"><span data-stu-id="48033-121">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="48033-122">此数据包括 OS 名称、OS 版本、PowerShell 版本和分发通道。</span><span class="sxs-lookup"><span data-stu-id="48033-122">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="48033-123">若要选择退出此遥测，请将环境变量 POWERSHELL_TELEMETRY_OPTOUT 设置为 true、yes 或1。</span><span class="sxs-lookup"><span data-stu-id="48033-123">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>
