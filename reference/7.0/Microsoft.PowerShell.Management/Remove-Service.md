---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: 13ef4d483ad91b38c175f850da9cd4d1da771935
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196868"
---
# <span data-ttu-id="54d5c-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-103">Remove-Service</span></span>

## <span data-ttu-id="54d5c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="54d5c-104">SYNOPSIS</span></span>
<span data-ttu-id="54d5c-105">删除 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="54d5c-105">Removes a Windows service.</span></span>

## <span data-ttu-id="54d5c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54d5c-106">SYNTAX</span></span>

### <span data-ttu-id="54d5c-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="54d5c-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="54d5c-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="54d5c-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="54d5c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54d5c-109">DESCRIPTION</span></span>

<span data-ttu-id="54d5c-110">`Remove-Service`Cmdlet 将在注册表和服务数据库中删除 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="54d5c-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="54d5c-111">`Remove-Service`Cmdlet 是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="54d5c-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="54d5c-112">示例</span><span class="sxs-lookup"><span data-stu-id="54d5c-112">EXAMPLES</span></span>

### <span data-ttu-id="54d5c-113">示例1：删除服务</span><span class="sxs-lookup"><span data-stu-id="54d5c-113">Example 1: Remove a service</span></span>

<span data-ttu-id="54d5c-114">这会删除名为 TestService 的服务。</span><span class="sxs-lookup"><span data-stu-id="54d5c-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="54d5c-115">示例2：使用显示名称删除服务</span><span class="sxs-lookup"><span data-stu-id="54d5c-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="54d5c-116">此示例删除名为 TestService 的服务。</span><span class="sxs-lookup"><span data-stu-id="54d5c-116">This example removes a service named TestService.</span></span> <span data-ttu-id="54d5c-117">该命令使用 `Get-Service` 来获取使用显示名称表示 TestService 服务的对象。</span><span class="sxs-lookup"><span data-stu-id="54d5c-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="54d5c-118">管道运算符 (将 `|` 对象) 管道 `Remove-Service` ，这将删除服务。</span><span class="sxs-lookup"><span data-stu-id="54d5c-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="54d5c-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54d5c-119">PARAMETERS</span></span>

### <span data-ttu-id="54d5c-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="54d5c-120">-InputObject</span></span>

<span data-ttu-id="54d5c-121">指定表示要删除的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="54d5c-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="54d5c-122">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="54d5c-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="54d5c-123">-Name</span><span class="sxs-lookup"><span data-stu-id="54d5c-123">-Name</span></span>

<span data-ttu-id="54d5c-124">指定要删除的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="54d5c-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="54d5c-125">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="54d5c-125">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="54d5c-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="54d5c-126">-Confirm</span></span>

<span data-ttu-id="54d5c-127">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="54d5c-127">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54d5c-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="54d5c-128">-WhatIf</span></span>

<span data-ttu-id="54d5c-129">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="54d5c-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="54d5c-130">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="54d5c-130">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54d5c-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54d5c-131">CommonParameters</span></span>

<span data-ttu-id="54d5c-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="54d5c-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54d5c-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="54d5c-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54d5c-134">输入</span><span class="sxs-lookup"><span data-stu-id="54d5c-134">INPUTS</span></span>

### <span data-ttu-id="54d5c-135">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="54d5c-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="54d5c-136">可以通过管道将服务对象或包含服务名称的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54d5c-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="54d5c-137">输出</span><span class="sxs-lookup"><span data-stu-id="54d5c-137">OUTPUTS</span></span>

### <span data-ttu-id="54d5c-138">无</span><span class="sxs-lookup"><span data-stu-id="54d5c-138">None</span></span>

<span data-ttu-id="54d5c-139">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="54d5c-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="54d5c-140">注释</span><span class="sxs-lookup"><span data-stu-id="54d5c-140">NOTES</span></span>

<span data-ttu-id="54d5c-141">若要运行此 cmdlet，请使用 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54d5c-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="54d5c-142">相关链接</span><span class="sxs-lookup"><span data-stu-id="54d5c-142">RELATED LINKS</span></span>

[<span data-ttu-id="54d5c-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="54d5c-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="54d5c-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="54d5c-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="54d5c-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="54d5c-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="54d5c-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="54d5c-149">Suspend-Service</span></span>](Suspend-Service.md)
