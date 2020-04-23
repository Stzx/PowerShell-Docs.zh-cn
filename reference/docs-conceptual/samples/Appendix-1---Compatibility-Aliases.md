---
ms.date: 09/09/2019
keywords: powershell,cmdlet
title: 附录 1 - 兼容性别名
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "70848163"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="fb585-103">附录 1 - 兼容性别名</span><span class="sxs-lookup"><span data-stu-id="fb585-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="fb585-104">PowerShell 具有多个别名，使 UNIX  和 cmd.exe  用户可以使用熟悉的命令。</span><span class="sxs-lookup"><span data-stu-id="fb585-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="fb585-105">下表显示了这些命令及其相关的 PowerShell cmdlet 和 PowerShell 别名：</span><span class="sxs-lookup"><span data-stu-id="fb585-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|<span data-ttu-id="fb585-106">cmd.exe命令</span><span class="sxs-lookup"><span data-stu-id="fb585-106">cmd.exe command</span></span>|<span data-ttu-id="fb585-107">UNIX 命令</span><span class="sxs-lookup"><span data-stu-id="fb585-107">UNIX command</span></span>|<span data-ttu-id="fb585-108">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fb585-108">PowerShell cmdlet</span></span>|<span data-ttu-id="fb585-109">PowerShell 别名</span><span class="sxs-lookup"><span data-stu-id="fb585-109">PowerShell alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="fb585-110">**cls**</span><span class="sxs-lookup"><span data-stu-id="fb585-110">**cls**</span></span>|<span data-ttu-id="fb585-111">**clear**</span><span class="sxs-lookup"><span data-stu-id="fb585-111">**clear**</span></span>|<span data-ttu-id="fb585-112">`Clear-Host`（函数）</span><span class="sxs-lookup"><span data-stu-id="fb585-112">`Clear-Host` (function)</span></span>|`cls`|
|<span data-ttu-id="fb585-113">**copy**</span><span class="sxs-lookup"><span data-stu-id="fb585-113">**copy**</span></span>|<span data-ttu-id="fb585-114">**cp**</span><span class="sxs-lookup"><span data-stu-id="fb585-114">**cp**</span></span>|`Copy-Item`|`cpi`|
|<span data-ttu-id="fb585-115">**dir**</span><span class="sxs-lookup"><span data-stu-id="fb585-115">**dir**</span></span>|<span data-ttu-id="fb585-116">**ls**</span><span class="sxs-lookup"><span data-stu-id="fb585-116">**ls**</span></span>|`Get-ChildItem`|`gci`|
|<span data-ttu-id="fb585-117">type </span><span class="sxs-lookup"><span data-stu-id="fb585-117">**type**</span></span>|<span data-ttu-id="fb585-118">**cat**</span><span class="sxs-lookup"><span data-stu-id="fb585-118">**cat**</span></span>|`Get-Content`|`gc`|
|<span data-ttu-id="fb585-119">**move**</span><span class="sxs-lookup"><span data-stu-id="fb585-119">**move**</span></span>|<span data-ttu-id="fb585-120">**mv**</span><span class="sxs-lookup"><span data-stu-id="fb585-120">**mv**</span></span>|`Move-Item`|`mi`|
|<span data-ttu-id="fb585-121">**md**</span><span class="sxs-lookup"><span data-stu-id="fb585-121">**md**</span></span>|<span data-ttu-id="fb585-122">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="fb585-122">**mkdir**</span></span>|`New-Item`|`ni`|
|<span data-ttu-id="fb585-123">**pushd**</span><span class="sxs-lookup"><span data-stu-id="fb585-123">**pushd**</span></span>|<span data-ttu-id="fb585-124">**pushd**</span><span class="sxs-lookup"><span data-stu-id="fb585-124">**pushd**</span></span>|`Push-Location`|`pushd`|
|<span data-ttu-id="fb585-125">**popd**</span><span class="sxs-lookup"><span data-stu-id="fb585-125">**popd**</span></span>|<span data-ttu-id="fb585-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="fb585-126">**popd**</span></span>|`Pop-Location`|`popd`|
|<span data-ttu-id="fb585-127">**del**、**erase**、**rd**、**rmdir**</span><span class="sxs-lookup"><span data-stu-id="fb585-127">**del**, **erase**, **rd**, **rmdir**</span></span>|<span data-ttu-id="fb585-128">**rm**</span><span class="sxs-lookup"><span data-stu-id="fb585-128">**rm**</span></span>|`Remove-Item`|`ri`|
|<span data-ttu-id="fb585-129">**ren**</span><span class="sxs-lookup"><span data-stu-id="fb585-129">**ren**</span></span>|<span data-ttu-id="fb585-130">**mv**</span><span class="sxs-lookup"><span data-stu-id="fb585-130">**mv**</span></span>|`Rename-Item`|`rni`|
|<span data-ttu-id="fb585-131">**cd**、**chdir**</span><span class="sxs-lookup"><span data-stu-id="fb585-131">**cd**, **chdir**</span></span>|<span data-ttu-id="fb585-132">**cd**</span><span class="sxs-lookup"><span data-stu-id="fb585-132">**cd**</span></span>|`Set-Location`|`sl`|

<span data-ttu-id="fb585-133">若要查找 PowerShell 别名，请使用 [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fb585-133">To find the PowerShell aliases, use the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet.</span></span> <span data-ttu-id="fb585-134">若要显示 cmdlet 的别名，请使用 Definition  参数并指定 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="fb585-134">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="fb585-135">或者，要查找别名的 cmdlet 名称，请使用 name  参数并指定别名。</span><span class="sxs-lookup"><span data-stu-id="fb585-135">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
