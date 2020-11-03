---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197625"
---
# <span data-ttu-id="a7990-103">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a7990-103">Remove-PSSnapin</span></span>

## <span data-ttu-id="a7990-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a7990-104">SYNOPSIS</span></span>
<span data-ttu-id="a7990-105">从当前会话中删除 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-105">Removes Windows PowerShell snap-ins from the current session.</span></span>

## <span data-ttu-id="a7990-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a7990-106">SYNTAX</span></span>

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a7990-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a7990-107">DESCRIPTION</span></span>
<span data-ttu-id="a7990-108">**Add-pssnapin** cmdlet 将从当前会话中删除 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-108">The **Remove-PSSnapin** cmdlet removes a Windows PowerShell snap-in from the current session.</span></span>
<span data-ttu-id="a7990-109">你可以使用它来删除已添加到 Windows PowerShell 的管理单元。无法使用此 cmdlet 删除随 Windows PowerShell 一起安装的管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-109">You can use it to remove snap-ins that you have added to Windows PowerShell You cannot use this cmdlet to remove the snap-ins that are installed with Windows PowerShell.</span></span>

<span data-ttu-id="a7990-110">从当前会话中删除管理单元后，仍将加载管理单元，但该管理单元中的 cmdlet 和提供程序在该会话中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a7990-110">After you remove a snap-in from the current session, the snap-in is still loaded, but the cmdlets and providers in the snap-in are no longer available in the session.</span></span>

## <span data-ttu-id="a7990-111">示例</span><span class="sxs-lookup"><span data-stu-id="a7990-111">EXAMPLES</span></span>

### <span data-ttu-id="a7990-112">示例1：删除管理单元</span><span class="sxs-lookup"><span data-stu-id="a7990-112">Example 1: Remove a snap-in</span></span>

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

<span data-ttu-id="a7990-113">此命令从当前会话中删除 **Microsoft. Exchange** 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-113">This command removes the **Microsoft.Exchange** snap-in from the current session.</span></span>
<span data-ttu-id="a7990-114">完成该命令后，该管理单元支持的 cmdlet 和提供程序在该会话中将不可用。</span><span class="sxs-lookup"><span data-stu-id="a7990-114">When the command is complete, the cmdlets and providers that the snap-in supported are not available in the session.</span></span>

### <span data-ttu-id="a7990-115">示例2：使用管道的名称删除管理单元</span><span class="sxs-lookup"><span data-stu-id="a7990-115">Example 2: Remove snap-ins by using names with the pipeline</span></span>

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

<span data-ttu-id="a7990-116">此命令从当前会话中删除名称以 smp 开头的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-116">This command removes the Windows PowerShell snap-ins that have names that start with smp from the current session.</span></span>

<span data-ttu-id="a7990-117">该命令使用 **add-pssnapin** cmdlet 来获取表示管理单元的对象。管道运算符 (|) 将结果发送到 **add-pssnapin** cmdlet，这会将其从会话中删除。</span><span class="sxs-lookup"><span data-stu-id="a7990-117">The command uses the **Get-PSSnapin** cmdlet to get objects that represent the snap-ins. The pipeline operator (|) sends the results to the **Remove-PSSnapin** cmdlet, which removes them from the session.</span></span>
<span data-ttu-id="a7990-118">此管理单元支持的 cmdlet 和提供程序在该会话中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a7990-118">The providers and cmdlets that this snap-in supports are no longer available in the session.</span></span>

<span data-ttu-id="a7990-119">当你通过管道将对象传递给 **add-pssnapin** 时，对象的名称将与 *name* 参数关联，该参数将接受具有 **name** 属性的管道中的对象。</span><span class="sxs-lookup"><span data-stu-id="a7990-119">When you pipe objects to **Remove-PSSnapin** , the names of the objects are associated with the *Name* parameter, which accepts objects from the pipeline that have a **Name** property.</span></span>

### <span data-ttu-id="a7990-120">示例3：使用名称删除管理单元</span><span class="sxs-lookup"><span data-stu-id="a7990-120">Example 3: Remove snap-ins by using names</span></span>

```
PS C:\> Remove-PSSnapin -Name *event*
```

<span data-ttu-id="a7990-121">此命令将删除名称中包含 "event" 的所有 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-121">This command removes all Windows PowerShell snap-ins that have names that include event.</span></span>

## <span data-ttu-id="a7990-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a7990-122">PARAMETERS</span></span>

### <span data-ttu-id="a7990-123">-Name</span><span class="sxs-lookup"><span data-stu-id="a7990-123">-Name</span></span>
<span data-ttu-id="a7990-124">指定要从当前会话中删除的 Windows PowerShell 管理单元的名称。</span><span class="sxs-lookup"><span data-stu-id="a7990-124">Specifies the names of Windows PowerShell snap-ins to remove from the current session.</span></span>
<span data-ttu-id="a7990-125">允许使用通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="a7990-125">Wildcard characters (\*) are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a7990-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a7990-126">-PassThru</span></span>
<span data-ttu-id="a7990-127">返回一个表示管理单元的对象。</span><span class="sxs-lookup"><span data-stu-id="a7990-127">Returns an object that represents the snap-in.</span></span>
<span data-ttu-id="a7990-128">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="a7990-128">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a7990-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a7990-129">-Confirm</span></span>
<span data-ttu-id="a7990-130">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="a7990-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a7990-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a7990-131">-WhatIf</span></span>
<span data-ttu-id="a7990-132">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a7990-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a7990-133">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="a7990-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a7990-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a7990-134">CommonParameters</span></span>
<span data-ttu-id="a7990-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a7990-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a7990-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a7990-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a7990-137">输入</span><span class="sxs-lookup"><span data-stu-id="a7990-137">INPUTS</span></span>

### <span data-ttu-id="a7990-138">System.Management.Automation.PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="a7990-138">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="a7990-139">可以通过管道将管理单元对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7990-139">You can pipe a snap-in object to this cmdlet.</span></span>

## <span data-ttu-id="a7990-140">输出</span><span class="sxs-lookup"><span data-stu-id="a7990-140">OUTPUTS</span></span>

### <span data-ttu-id="a7990-141">PSSnapInInfo （无）</span><span class="sxs-lookup"><span data-stu-id="a7990-141">None, System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="a7990-142">如果指定 *PassThru* 参数，则此 cmdlet 将生成表示该管理单元的 **PSSnapInInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="a7990-142">This cmdlet generates a **System.Management.Automation.PSSnapInInfo** object that represents the snap-in, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="a7990-143">默认情况下， **add-pssnapin** 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="a7990-143">By default, **Remove-PSSnapin** does not generate any output.</span></span>

## <span data-ttu-id="a7990-144">注释</span><span class="sxs-lookup"><span data-stu-id="a7990-144">NOTES</span></span>

* <span data-ttu-id="a7990-145">**Add-pssnapin** 在从会话中删除管理单元之前，不会检查 Windows PowerShell 的版本。</span><span class="sxs-lookup"><span data-stu-id="a7990-145">**Remove-PSSnapin** does not check the version of Windows PowerShell before removing a snap-in from the session.</span></span> <span data-ttu-id="a7990-146">如果无法删除某个管理单元，则会出现一条警告，并且该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="a7990-146">If a snap-in cannot be removed, a warning appears and the command fails.</span></span>
* <span data-ttu-id="a7990-147">**Add-pssnapin** 仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="a7990-147">**Remove-PSSnapin** affects only the current session.</span></span> <span data-ttu-id="a7990-148">如果你已将 Add-pssnapin 命令添加到你的 Windows PowerShell 配置文件中，则应删除该命令，以从以后的会话中删除管理单元。</span><span class="sxs-lookup"><span data-stu-id="a7990-148">If you have added an Add-PSSnapin command to your Windows PowerShell profile, you should delete the command to remove the snap-in from future sessions.</span></span> <span data-ttu-id="a7990-149">有关说明，请键入 `Get-Help about_Profiles` 。</span><span class="sxs-lookup"><span data-stu-id="a7990-149">For instructions, type `Get-Help about_Profiles`.</span></span>

## <span data-ttu-id="a7990-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="a7990-150">RELATED LINKS</span></span>

[<span data-ttu-id="a7990-151">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a7990-151">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="a7990-152">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a7990-152">Get-PSSnapin</span></span>](Get-PSSnapin.md)
