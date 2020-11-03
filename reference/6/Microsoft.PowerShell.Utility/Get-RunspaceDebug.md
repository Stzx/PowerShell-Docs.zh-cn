---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: dbe78dd81641786b0079ef5326c849c2bde008dc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198590"
---
# <span data-ttu-id="264a3-103">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="264a3-103">Get-RunspaceDebug</span></span>

## <span data-ttu-id="264a3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="264a3-104">SYNOPSIS</span></span>
<span data-ttu-id="264a3-105">显示运行空间调试选项。</span><span class="sxs-lookup"><span data-stu-id="264a3-105">Shows runspace debugging options.</span></span>

## <span data-ttu-id="264a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="264a3-106">SYNTAX</span></span>

### <span data-ttu-id="264a3-107">RunspaceNameParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="264a3-107">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="264a3-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="264a3-108">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="264a3-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="264a3-109">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="264a3-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="264a3-110">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="264a3-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="264a3-111">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="264a3-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="264a3-112">DESCRIPTION</span></span>

<span data-ttu-id="264a3-113">`Get-RunspaceDebug`Cmdlet 显示运行空间调试选项。</span><span class="sxs-lookup"><span data-stu-id="264a3-113">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="264a3-114">示例</span><span class="sxs-lookup"><span data-stu-id="264a3-114">EXAMPLES</span></span>

### <span data-ttu-id="264a3-115">1：显示默认运行空间调试程序的状态</span><span class="sxs-lookup"><span data-stu-id="264a3-115">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="264a3-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="264a3-116">PARAMETERS</span></span>

### <span data-ttu-id="264a3-117">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="264a3-117">-AppDomainName</span></span>

<span data-ttu-id="264a3-118">承载 PowerShell 运行空间的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="264a3-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="264a3-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="264a3-119">-ProcessName</span></span>

<span data-ttu-id="264a3-120">承载 PowerShell 运行空间的进程的名称。</span><span class="sxs-lookup"><span data-stu-id="264a3-120">The name of the process that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="264a3-121">-运行空间</span><span class="sxs-lookup"><span data-stu-id="264a3-121">-Runspace</span></span>

<span data-ttu-id="264a3-122">要禁用的一个或多个 **运行空间** 对象。</span><span class="sxs-lookup"><span data-stu-id="264a3-122">One or more **Runspace** objects to be disabled.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="264a3-123">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="264a3-123">-RunspaceId</span></span>

<span data-ttu-id="264a3-124">要禁用的一个或多个 **运行空间** Id 号。</span><span class="sxs-lookup"><span data-stu-id="264a3-124">One or more **Runspace** Id numbers to be disabled.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="264a3-125">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="264a3-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="264a3-126">要禁用的一个或多个 **运行空间** guid。</span><span class="sxs-lookup"><span data-stu-id="264a3-126">One or more **Runspace** GUIDs to be disabled.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="264a3-127">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="264a3-127">-RunspaceName</span></span>

<span data-ttu-id="264a3-128">要禁用的一个或多个 **运行空间** 名称。</span><span class="sxs-lookup"><span data-stu-id="264a3-128">One or more **Runspace** names to be disabled.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="264a3-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="264a3-129">CommonParameters</span></span>

<span data-ttu-id="264a3-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="264a3-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="264a3-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="264a3-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="264a3-132">输入</span><span class="sxs-lookup"><span data-stu-id="264a3-132">INPUTS</span></span>

## <span data-ttu-id="264a3-133">输出</span><span class="sxs-lookup"><span data-stu-id="264a3-133">OUTPUTS</span></span>

## <span data-ttu-id="264a3-134">注释</span><span class="sxs-lookup"><span data-stu-id="264a3-134">NOTES</span></span>

## <span data-ttu-id="264a3-135">相关链接</span><span class="sxs-lookup"><span data-stu-id="264a3-135">RELATED LINKS</span></span>

[<span data-ttu-id="264a3-136">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="264a3-136">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="264a3-137">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="264a3-137">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)
