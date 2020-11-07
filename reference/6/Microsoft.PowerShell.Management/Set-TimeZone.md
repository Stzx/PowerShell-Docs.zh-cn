---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 3738ac6202fa7a46c9a742e48edaeb1b82b5d749
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345113"
---
# <span data-ttu-id="02ee0-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="02ee0-103">Set-TimeZone</span></span>

## <span data-ttu-id="02ee0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="02ee0-104">SYNOPSIS</span></span>
<span data-ttu-id="02ee0-105">将系统时区设置为指定的时区。</span><span class="sxs-lookup"><span data-stu-id="02ee0-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="02ee0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="02ee0-106">SYNTAX</span></span>

### <span data-ttu-id="02ee0-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="02ee0-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ee0-108">ID</span><span class="sxs-lookup"><span data-stu-id="02ee0-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="02ee0-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="02ee0-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="02ee0-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="02ee0-110">DESCRIPTION</span></span>

<span data-ttu-id="02ee0-111">`Set-TimeZone`Cmdlet 将系统时区设置为指定的时区。</span><span class="sxs-lookup"><span data-stu-id="02ee0-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="02ee0-112">示例</span><span class="sxs-lookup"><span data-stu-id="02ee0-112">EXAMPLES</span></span>

### <span data-ttu-id="02ee0-113">示例1：按 Id 设置时区</span><span class="sxs-lookup"><span data-stu-id="02ee0-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="02ee0-114">此示例将本地计算机上的时区设置为俄罗斯标准时间。</span><span class="sxs-lookup"><span data-stu-id="02ee0-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

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

### <span data-ttu-id="02ee0-115">示例2：按名称设置时区</span><span class="sxs-lookup"><span data-stu-id="02ee0-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="02ee0-116">此示例将本地计算机上的时区设置为俄罗斯标准时间。</span><span class="sxs-lookup"><span data-stu-id="02ee0-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="02ee0-117">如前面的示例所示，时区的 **Id** 和 **名称** 不一定总是匹配。</span><span class="sxs-lookup"><span data-stu-id="02ee0-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="02ee0-118">**Name** 参数必须匹配 **TimeZoneInfo** 对象的 **StandardName** 或 **DaylightName** 属性。</span><span class="sxs-lookup"><span data-stu-id="02ee0-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="02ee0-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="02ee0-119">PARAMETERS</span></span>

### <span data-ttu-id="02ee0-120">-Id</span><span class="sxs-lookup"><span data-stu-id="02ee0-120">-Id</span></span>

<span data-ttu-id="02ee0-121">指定此 cmdlet 设置的时区的 ID。</span><span class="sxs-lookup"><span data-stu-id="02ee0-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="02ee0-122">可以通过运行以下命令获取时区 Id 的完整列表： `Get-TimeZone -ListAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="02ee0-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="02ee0-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="02ee0-123">-InputObject</span></span>

<span data-ttu-id="02ee0-124">指定要用作输入的 **TimeZoneInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="02ee0-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

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

### <span data-ttu-id="02ee0-125">-Name</span><span class="sxs-lookup"><span data-stu-id="02ee0-125">-Name</span></span>

<span data-ttu-id="02ee0-126">指定此 cmdlet 设置的时区的名称。</span><span class="sxs-lookup"><span data-stu-id="02ee0-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="02ee0-127">可以通过运行以下命令来获取时区名称的完整列表： `Get-TimeZone -ListAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="02ee0-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="02ee0-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="02ee0-128">-PassThru</span></span>

<span data-ttu-id="02ee0-129">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="02ee0-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="02ee0-130">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="02ee0-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="02ee0-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="02ee0-131">-Confirm</span></span>

<span data-ttu-id="02ee0-132">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="02ee0-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="02ee0-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="02ee0-133">-WhatIf</span></span>

<span data-ttu-id="02ee0-134">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="02ee0-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="02ee0-135">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="02ee0-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="02ee0-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="02ee0-136">CommonParameters</span></span>

<span data-ttu-id="02ee0-137">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="02ee0-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="02ee0-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="02ee0-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="02ee0-139">输入</span><span class="sxs-lookup"><span data-stu-id="02ee0-139">INPUTS</span></span>

### <span data-ttu-id="02ee0-140">System.string、TimeZoneInfo、System.string</span><span class="sxs-lookup"><span data-stu-id="02ee0-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="02ee0-141">输出</span><span class="sxs-lookup"><span data-stu-id="02ee0-141">OUTPUTS</span></span>

## <span data-ttu-id="02ee0-142">注释</span><span class="sxs-lookup"><span data-stu-id="02ee0-142">NOTES</span></span>

<span data-ttu-id="02ee0-143">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="02ee0-143">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="02ee0-144">相关链接</span><span class="sxs-lookup"><span data-stu-id="02ee0-144">RELATED LINKS</span></span>

[<span data-ttu-id="02ee0-145">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="02ee0-145">Get-TimeZone</span></span>](Get-TimeZone.md)
