---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 618f2ceca435e836a0c733f98533b62dfc86290b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198896"
---
# <span data-ttu-id="e20dc-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="e20dc-103">Set-TimeZone</span></span>

## <span data-ttu-id="e20dc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e20dc-104">SYNOPSIS</span></span>
<span data-ttu-id="e20dc-105">将系统时区设置为指定的时区。</span><span class="sxs-lookup"><span data-stu-id="e20dc-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="e20dc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e20dc-106">SYNTAX</span></span>

### <span data-ttu-id="e20dc-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="e20dc-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e20dc-108">ID</span><span class="sxs-lookup"><span data-stu-id="e20dc-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e20dc-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="e20dc-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e20dc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e20dc-110">DESCRIPTION</span></span>

<span data-ttu-id="e20dc-111">`Set-TimeZone`Cmdlet 将系统时区设置为指定的时区。</span><span class="sxs-lookup"><span data-stu-id="e20dc-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="e20dc-112">示例</span><span class="sxs-lookup"><span data-stu-id="e20dc-112">EXAMPLES</span></span>

### <span data-ttu-id="e20dc-113">示例1：按 Id 设置时区</span><span class="sxs-lookup"><span data-stu-id="e20dc-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="e20dc-114">此示例将本地计算机上的时区设置为俄罗斯标准时间。</span><span class="sxs-lookup"><span data-stu-id="e20dc-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### <span data-ttu-id="e20dc-115">示例2：按名称设置时区</span><span class="sxs-lookup"><span data-stu-id="e20dc-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="e20dc-116">此示例将本地计算机上的时区设置为俄罗斯标准时间。</span><span class="sxs-lookup"><span data-stu-id="e20dc-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="e20dc-117">如前面的示例所示，时区的 **Id** 和 **名称** 不一定总是匹配。</span><span class="sxs-lookup"><span data-stu-id="e20dc-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="e20dc-118">**Name** 参数必须匹配 **TimeZoneInfo** 对象的 **StandardName** 或 **DaylightName** 属性。</span><span class="sxs-lookup"><span data-stu-id="e20dc-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="e20dc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e20dc-119">PARAMETERS</span></span>

### <span data-ttu-id="e20dc-120">-Id</span><span class="sxs-lookup"><span data-stu-id="e20dc-120">-Id</span></span>

<span data-ttu-id="e20dc-121">指定此 cmdlet 设置的时区的 ID。</span><span class="sxs-lookup"><span data-stu-id="e20dc-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="e20dc-122">可以通过运行以下命令获取时区 Id 的完整列表： `Get-TimeZone -ListAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="e20dc-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e20dc-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e20dc-123">-InputObject</span></span>

<span data-ttu-id="e20dc-124">指定要用作输入的 **TimeZoneInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="e20dc-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e20dc-125">-Name</span><span class="sxs-lookup"><span data-stu-id="e20dc-125">-Name</span></span>

<span data-ttu-id="e20dc-126">指定此 cmdlet 设置的时区的名称。</span><span class="sxs-lookup"><span data-stu-id="e20dc-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="e20dc-127">可以通过运行以下命令来获取时区名称的完整列表： `Get-TimeZone -ListAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="e20dc-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e20dc-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e20dc-128">-PassThru</span></span>

<span data-ttu-id="e20dc-129">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="e20dc-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="e20dc-130">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="e20dc-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e20dc-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e20dc-131">-Confirm</span></span>

<span data-ttu-id="e20dc-132">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e20dc-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e20dc-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e20dc-133">-WhatIf</span></span>

<span data-ttu-id="e20dc-134">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e20dc-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e20dc-135">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e20dc-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e20dc-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e20dc-136">CommonParameters</span></span>

<span data-ttu-id="e20dc-137">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e20dc-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e20dc-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e20dc-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e20dc-139">输入</span><span class="sxs-lookup"><span data-stu-id="e20dc-139">INPUTS</span></span>

### <span data-ttu-id="e20dc-140">System.string、TimeZoneInfo、System.string</span><span class="sxs-lookup"><span data-stu-id="e20dc-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="e20dc-141">输出</span><span class="sxs-lookup"><span data-stu-id="e20dc-141">OUTPUTS</span></span>

## <span data-ttu-id="e20dc-142">注释</span><span class="sxs-lookup"><span data-stu-id="e20dc-142">NOTES</span></span>

## <span data-ttu-id="e20dc-143">相关链接</span><span class="sxs-lookup"><span data-stu-id="e20dc-143">RELATED LINKS</span></span>

[<span data-ttu-id="e20dc-144">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="e20dc-144">Get-TimeZone</span></span>](Get-TimeZone.md)

