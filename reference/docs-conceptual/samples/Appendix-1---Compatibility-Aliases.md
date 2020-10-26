---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: 附录 1 - 兼容性别名
description: PowerShell 具有多个别名，使 UNIX  和 cmd.exe  用户可以使用熟悉的命令。
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500736"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="187e2-104">附录 1 - 兼容性别名</span><span class="sxs-lookup"><span data-stu-id="187e2-104">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="187e2-105">PowerShell 具有多个别名，使 UNIX  和 cmd.exe  用户可以使用熟悉的命令。</span><span class="sxs-lookup"><span data-stu-id="187e2-105">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="187e2-106">下表显示了这些命令及其相关的 PowerShell cmdlet 和 PowerShell 别名：</span><span class="sxs-lookup"><span data-stu-id="187e2-106">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="187e2-107">cmd.exe命令</span><span class="sxs-lookup"><span data-stu-id="187e2-107">cmd.exe command</span></span>            | <span data-ttu-id="187e2-108">UNIX 命令</span><span class="sxs-lookup"><span data-stu-id="187e2-108">UNIX command</span></span> | <span data-ttu-id="187e2-109">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="187e2-109">PowerShell cmdlet</span></span> | <span data-ttu-id="187e2-110">PowerShell 别名</span><span class="sxs-lookup"><span data-stu-id="187e2-110">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="187e2-111">**cd** 、 **chdir**</span><span class="sxs-lookup"><span data-stu-id="187e2-111">**cd** , **chdir**</span></span>                     | <span data-ttu-id="187e2-112">**cd**</span><span class="sxs-lookup"><span data-stu-id="187e2-112">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="187e2-113">**cls**</span><span class="sxs-lookup"><span data-stu-id="187e2-113">**cls**</span></span>                               | <span data-ttu-id="187e2-114">**clear**</span><span class="sxs-lookup"><span data-stu-id="187e2-114">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="187e2-115">**copy**</span><span class="sxs-lookup"><span data-stu-id="187e2-115">**copy**</span></span>                              | <span data-ttu-id="187e2-116">**cp**</span><span class="sxs-lookup"><span data-stu-id="187e2-116">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="187e2-117">**del** 、 **erase** 、 **rd** 、 **rmdir**</span><span class="sxs-lookup"><span data-stu-id="187e2-117">**del** , **erase** , **rd** , **rmdir**</span></span> | <span data-ttu-id="187e2-118">**rm**</span><span class="sxs-lookup"><span data-stu-id="187e2-118">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="187e2-119">**dir**</span><span class="sxs-lookup"><span data-stu-id="187e2-119">**dir**</span></span>                               | <span data-ttu-id="187e2-120">**ls**</span><span class="sxs-lookup"><span data-stu-id="187e2-120">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="187e2-121">echo</span><span class="sxs-lookup"><span data-stu-id="187e2-121">**echo**</span></span>                              | <span data-ttu-id="187e2-122">echo</span><span class="sxs-lookup"><span data-stu-id="187e2-122">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="187e2-123">**md**</span><span class="sxs-lookup"><span data-stu-id="187e2-123">**md**</span></span>                                | <span data-ttu-id="187e2-124">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="187e2-124">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="187e2-125">**move**</span><span class="sxs-lookup"><span data-stu-id="187e2-125">**move**</span></span>                              | <span data-ttu-id="187e2-126">**mv**</span><span class="sxs-lookup"><span data-stu-id="187e2-126">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="187e2-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="187e2-127">**popd**</span></span>                              | <span data-ttu-id="187e2-128">**popd**</span><span class="sxs-lookup"><span data-stu-id="187e2-128">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="187e2-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="187e2-129">**pushd**</span></span>                             | <span data-ttu-id="187e2-130">**pushd**</span><span class="sxs-lookup"><span data-stu-id="187e2-130">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="187e2-131">**ren**</span><span class="sxs-lookup"><span data-stu-id="187e2-131">**ren**</span></span>                               | <span data-ttu-id="187e2-132">**mv**</span><span class="sxs-lookup"><span data-stu-id="187e2-132">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="187e2-133">type</span><span class="sxs-lookup"><span data-stu-id="187e2-133">**type**</span></span>                              | <span data-ttu-id="187e2-134">**cat**</span><span class="sxs-lookup"><span data-stu-id="187e2-134">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="187e2-135">若要查找 PowerShell 别名，请使用 [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="187e2-135">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="187e2-136">若要显示 cmdlet 的别名，请使用 Definition  参数并指定 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="187e2-136">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="187e2-137">或者，要查找别名的 cmdlet 名称，请使用 name  参数并指定别名。</span><span class="sxs-lookup"><span data-stu-id="187e2-137">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
