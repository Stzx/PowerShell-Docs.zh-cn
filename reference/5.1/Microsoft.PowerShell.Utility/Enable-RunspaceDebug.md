---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 54fb9500a924d2e5de98489fa4fb391accb23d0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197948"
---
# <span data-ttu-id="f74f3-103">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f74f3-103">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="f74f3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f74f3-104">SYNOPSIS</span></span>
<span data-ttu-id="f74f3-105">启用对运行空间的调试，其中任何断点都将保留，直到附加调试器。</span><span class="sxs-lookup"><span data-stu-id="f74f3-105">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="f74f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f74f3-106">SYNTAX</span></span>

### <span data-ttu-id="f74f3-107">RunspaceNameParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="f74f3-107">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f74f3-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="f74f3-108">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="f74f3-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="f74f3-109">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="f74f3-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="f74f3-110">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="f74f3-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="f74f3-111">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f74f3-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f74f3-112">DESCRIPTION</span></span>

<span data-ttu-id="f74f3-113">`Enable-RunspaceDebug`Cmdlet 在附加了调试器的情况下，允许在保留了任何断点的运行空间上进行调试。</span><span class="sxs-lookup"><span data-stu-id="f74f3-113">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="f74f3-114">示例</span><span class="sxs-lookup"><span data-stu-id="f74f3-114">EXAMPLES</span></span>

### <span data-ttu-id="f74f3-115">1：启用默认的运行空间调试器</span><span class="sxs-lookup"><span data-stu-id="f74f3-115">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="f74f3-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f74f3-116">PARAMETERS</span></span>

### <span data-ttu-id="f74f3-117">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="f74f3-117">-AppDomainName</span></span>

<span data-ttu-id="f74f3-118">承载 PowerShell 运行空间的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="f74f3-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="f74f3-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="f74f3-119">-BreakAll</span></span>

<span data-ttu-id="f74f3-120">使运行空间中任何正在运行的命令或脚本在步骤模式下停止，无论当前是否附加调试器。</span><span class="sxs-lookup"><span data-stu-id="f74f3-120">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="f74f3-121">脚本或命令将保持停止状态，直到附加调试器来调试当前的停止点。</span><span class="sxs-lookup"><span data-stu-id="f74f3-121">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RunspaceNameParameterSet, RunspaceParameterSet, RunspaceIdParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f74f3-122">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="f74f3-122">-ProcessName</span></span>

<span data-ttu-id="f74f3-123">承载 PowerShell 运行空间的进程的名称。</span><span class="sxs-lookup"><span data-stu-id="f74f3-123">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="f74f3-124">-运行空间</span><span class="sxs-lookup"><span data-stu-id="f74f3-124">-Runspace</span></span>

<span data-ttu-id="f74f3-125">要禁用的一个或多个 **运行空间** 对象。</span><span class="sxs-lookup"><span data-stu-id="f74f3-125">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="f74f3-126">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="f74f3-126">-RunspaceId</span></span>

<span data-ttu-id="f74f3-127">要禁用的一个或多个 **运行空间** Id 号。</span><span class="sxs-lookup"><span data-stu-id="f74f3-127">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="f74f3-128">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="f74f3-128">-RunspaceInstanceId</span></span>

<span data-ttu-id="f74f3-129">要禁用的一个或多个 **运行空间** guid。</span><span class="sxs-lookup"><span data-stu-id="f74f3-129">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="f74f3-130">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="f74f3-130">-RunspaceName</span></span>

<span data-ttu-id="f74f3-131">要禁用的一个或多个 **运行空间** 名称。</span><span class="sxs-lookup"><span data-stu-id="f74f3-131">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="f74f3-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f74f3-132">CommonParameters</span></span>

<span data-ttu-id="f74f3-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f74f3-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f74f3-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f74f3-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f74f3-135">输入</span><span class="sxs-lookup"><span data-stu-id="f74f3-135">INPUTS</span></span>

## <span data-ttu-id="f74f3-136">输出</span><span class="sxs-lookup"><span data-stu-id="f74f3-136">OUTPUTS</span></span>

## <span data-ttu-id="f74f3-137">注释</span><span class="sxs-lookup"><span data-stu-id="f74f3-137">NOTES</span></span>

## <span data-ttu-id="f74f3-138">相关链接</span><span class="sxs-lookup"><span data-stu-id="f74f3-138">RELATED LINKS</span></span>

[<span data-ttu-id="f74f3-139">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f74f3-139">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="f74f3-140">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f74f3-140">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
