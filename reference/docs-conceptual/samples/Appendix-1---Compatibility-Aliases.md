---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: 附录 1 - 兼容性别名
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758493"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="60a46-103">附录 1 - 兼容性别名</span><span class="sxs-lookup"><span data-stu-id="60a46-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="60a46-104">PowerShell 具有多个别名，使 UNIX  和 cmd.exe  用户可以使用熟悉的命令。</span><span class="sxs-lookup"><span data-stu-id="60a46-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="60a46-105">下表显示了这些命令及其相关的 PowerShell cmdlet 和 PowerShell 别名：</span><span class="sxs-lookup"><span data-stu-id="60a46-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="60a46-106">cmd.exe命令</span><span class="sxs-lookup"><span data-stu-id="60a46-106">cmd.exe command</span></span>            | <span data-ttu-id="60a46-107">UNIX 命令</span><span class="sxs-lookup"><span data-stu-id="60a46-107">UNIX command</span></span> | <span data-ttu-id="60a46-108">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="60a46-108">PowerShell cmdlet</span></span> | <span data-ttu-id="60a46-109">PowerShell 别名</span><span class="sxs-lookup"><span data-stu-id="60a46-109">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="60a46-110">**cd**、**chdir**</span><span class="sxs-lookup"><span data-stu-id="60a46-110">**cd**, **chdir**</span></span>                     | <span data-ttu-id="60a46-111">**cd**</span><span class="sxs-lookup"><span data-stu-id="60a46-111">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="60a46-112">**cls**</span><span class="sxs-lookup"><span data-stu-id="60a46-112">**cls**</span></span>                               | <span data-ttu-id="60a46-113">**clear**</span><span class="sxs-lookup"><span data-stu-id="60a46-113">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="60a46-114">**copy**</span><span class="sxs-lookup"><span data-stu-id="60a46-114">**copy**</span></span>                              | <span data-ttu-id="60a46-115">**cp**</span><span class="sxs-lookup"><span data-stu-id="60a46-115">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="60a46-116">**del**、**erase**、**rd**、**rmdir**</span><span class="sxs-lookup"><span data-stu-id="60a46-116">**del**, **erase**, **rd**, **rmdir**</span></span> | <span data-ttu-id="60a46-117">**rm**</span><span class="sxs-lookup"><span data-stu-id="60a46-117">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="60a46-118">**dir**</span><span class="sxs-lookup"><span data-stu-id="60a46-118">**dir**</span></span>                               | <span data-ttu-id="60a46-119">**ls**</span><span class="sxs-lookup"><span data-stu-id="60a46-119">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="60a46-120">echo</span><span class="sxs-lookup"><span data-stu-id="60a46-120">**echo**</span></span>                              | <span data-ttu-id="60a46-121">echo</span><span class="sxs-lookup"><span data-stu-id="60a46-121">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="60a46-122">**md**</span><span class="sxs-lookup"><span data-stu-id="60a46-122">**md**</span></span>                                | <span data-ttu-id="60a46-123">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="60a46-123">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="60a46-124">**move**</span><span class="sxs-lookup"><span data-stu-id="60a46-124">**move**</span></span>                              | <span data-ttu-id="60a46-125">**mv**</span><span class="sxs-lookup"><span data-stu-id="60a46-125">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="60a46-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="60a46-126">**popd**</span></span>                              | <span data-ttu-id="60a46-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="60a46-127">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="60a46-128">**pushd**</span><span class="sxs-lookup"><span data-stu-id="60a46-128">**pushd**</span></span>                             | <span data-ttu-id="60a46-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="60a46-129">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="60a46-130">**ren**</span><span class="sxs-lookup"><span data-stu-id="60a46-130">**ren**</span></span>                               | <span data-ttu-id="60a46-131">**mv**</span><span class="sxs-lookup"><span data-stu-id="60a46-131">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="60a46-132">type</span><span class="sxs-lookup"><span data-stu-id="60a46-132">**type**</span></span>                              | <span data-ttu-id="60a46-133">**cat**</span><span class="sxs-lookup"><span data-stu-id="60a46-133">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="60a46-134">若要查找 PowerShell 别名，请使用 [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60a46-134">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="60a46-135">若要显示 cmdlet 的别名，请使用 Definition\*\*\*\* 参数并指定 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="60a46-135">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="60a46-136">或者，要查找别名的 cmdlet 名称，请使用 name\*\*\*\* 参数并指定别名。</span><span class="sxs-lookup"><span data-stu-id="60a46-136">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
