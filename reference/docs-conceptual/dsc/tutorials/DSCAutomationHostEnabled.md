---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: DSCAutomationHostEnabled 注册表项
description: 本文定义了可在 DSCAutomationHostEnabled 注册表项中设置的值
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656188"
---
# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="a6ddf-104">DSCAutomationHostEnabled 注册表项</span><span class="sxs-lookup"><span data-stu-id="a6ddf-104">DSCAutomationHostEnabled registry key</span></span>

> <span data-ttu-id="a6ddf-105">适用对象：Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a6ddf-105">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="a6ddf-106">DSC 使用 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System 下的 DSCAutomationHostEnabled 注册表项，以便在初始启动时配置计算机。</span><span class="sxs-lookup"><span data-stu-id="a6ddf-106">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span> <span data-ttu-id="a6ddf-107">DSCAutomationHostEnabled 支持三种模式：</span><span class="sxs-lookup"><span data-stu-id="a6ddf-107">**DSCAutomationHostEnabled** supports three modes:</span></span>

| <span data-ttu-id="a6ddf-108">DSCAutomationHostEnabled 值</span><span class="sxs-lookup"><span data-stu-id="a6ddf-108">DSCAutomationHostEnabled Value</span></span> |                                              <span data-ttu-id="a6ddf-109">说明</span><span class="sxs-lookup"><span data-stu-id="a6ddf-109">Description</span></span>                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a6ddf-110">0</span><span class="sxs-lookup"><span data-stu-id="a6ddf-110">0</span></span>                              | <span data-ttu-id="a6ddf-111">禁用对启动状态计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="a6ddf-111">Disable configuring the machine at boot-up.</span></span>                                                           |
| <span data-ttu-id="a6ddf-112">1</span><span class="sxs-lookup"><span data-stu-id="a6ddf-112">1</span></span>                              | <span data-ttu-id="a6ddf-113">启用对启动状态计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="a6ddf-113">Enable configuring the machine at boot-up.</span></span>                                                            |
| <span data-ttu-id="a6ddf-114">2</span><span class="sxs-lookup"><span data-stu-id="a6ddf-114">2</span></span>                              | <span data-ttu-id="a6ddf-115">仅在 DSC 处于挂起或当前状态时，启用对计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="a6ddf-115">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="a6ddf-116">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="a6ddf-116">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a6ddf-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6ddf-117">See Also</span></span>

<span data-ttu-id="a6ddf-118">有关如何使用此功能在初始启动时运行配置的示例，请参阅[初始启动时使用 DSC 配置虚拟机](bootstrapDsc.md)。</span><span class="sxs-lookup"><span data-stu-id="a6ddf-118">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
