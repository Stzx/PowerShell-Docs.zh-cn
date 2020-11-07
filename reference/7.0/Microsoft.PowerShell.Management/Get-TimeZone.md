---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 44740fff5b8cef989d4c6391379741d1882f4734
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345606"
---
# <span data-ttu-id="854d8-103">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="854d8-103">Get-TimeZone</span></span>

## <span data-ttu-id="854d8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="854d8-104">SYNOPSIS</span></span>
<span data-ttu-id="854d8-105">获取当前时区或可用时区的列表。</span><span class="sxs-lookup"><span data-stu-id="854d8-105">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="854d8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="854d8-106">SYNTAX</span></span>

### <span data-ttu-id="854d8-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="854d8-107">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="854d8-108">ID</span><span class="sxs-lookup"><span data-stu-id="854d8-108">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="854d8-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="854d8-109">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="854d8-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="854d8-110">DESCRIPTION</span></span>

<span data-ttu-id="854d8-111">**获取时区** cmdlet 获取当前时区或可用时区的列表。</span><span class="sxs-lookup"><span data-stu-id="854d8-111">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="854d8-112">示例</span><span class="sxs-lookup"><span data-stu-id="854d8-112">EXAMPLES</span></span>

### <span data-ttu-id="854d8-113">示例1：获取当前时区</span><span class="sxs-lookup"><span data-stu-id="854d8-113">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="854d8-114">此命令获取当前时区。</span><span class="sxs-lookup"><span data-stu-id="854d8-114">This command gets the current time zone.</span></span>

### <span data-ttu-id="854d8-115">示例2：获取与指定的字符串匹配的时区</span><span class="sxs-lookup"><span data-stu-id="854d8-115">Example 2: Get time zones that match a specified string</span></span>

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

<span data-ttu-id="854d8-116">此命令将获取与指定的通配符匹配的所有时区。</span><span class="sxs-lookup"><span data-stu-id="854d8-116">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="854d8-117">示例3：获取所有可用时区</span><span class="sxs-lookup"><span data-stu-id="854d8-117">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="854d8-118">此命令将获取所有可用时区。</span><span class="sxs-lookup"><span data-stu-id="854d8-118">This command gets all available time zones.</span></span>

## <span data-ttu-id="854d8-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="854d8-119">PARAMETERS</span></span>

### <span data-ttu-id="854d8-120">-Id</span><span class="sxs-lookup"><span data-stu-id="854d8-120">-Id</span></span>

<span data-ttu-id="854d8-121">指定为字符串数组，此 cmdlet 获取的时区的 ID 或 id。</span><span class="sxs-lookup"><span data-stu-id="854d8-121">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="854d8-122">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="854d8-122">-ListAvailable</span></span>

<span data-ttu-id="854d8-123">指示此 cmdlet 获取所有可用时区。</span><span class="sxs-lookup"><span data-stu-id="854d8-123">Indicates that this cmdlet gets all available time zones.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="854d8-124">-Name</span><span class="sxs-lookup"><span data-stu-id="854d8-124">-Name</span></span>

<span data-ttu-id="854d8-125">以字符串数组的形式指定此 cmdlet 获取的时区的名称。</span><span class="sxs-lookup"><span data-stu-id="854d8-125">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="854d8-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="854d8-126">CommonParameters</span></span>

<span data-ttu-id="854d8-127">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="854d8-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="854d8-128">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="854d8-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="854d8-129">输入</span><span class="sxs-lookup"><span data-stu-id="854d8-129">INPUTS</span></span>

### <span data-ttu-id="854d8-130">System.String[]</span><span class="sxs-lookup"><span data-stu-id="854d8-130">System.String[]</span></span>

## <span data-ttu-id="854d8-131">输出</span><span class="sxs-lookup"><span data-stu-id="854d8-131">OUTPUTS</span></span>

### <span data-ttu-id="854d8-132">TimeZoneInfo []</span><span class="sxs-lookup"><span data-stu-id="854d8-132">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="854d8-133">注释</span><span class="sxs-lookup"><span data-stu-id="854d8-133">NOTES</span></span>

<span data-ttu-id="854d8-134">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="854d8-134">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="854d8-135">相关链接</span><span class="sxs-lookup"><span data-stu-id="854d8-135">RELATED LINKS</span></span>

[<span data-ttu-id="854d8-136">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="854d8-136">Set-TimeZone</span></span>](Set-TimeZone.md)
