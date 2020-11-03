---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 1dd2da57792cb3ad10453d9d0adc3ef51cf2305e
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196740"
---
# <span data-ttu-id="29a7e-103">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="29a7e-103">Get-UICulture</span></span>

## <span data-ttu-id="29a7e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="29a7e-104">SYNOPSIS</span></span>
<span data-ttu-id="29a7e-105">获取操作系统中的当前 UI 区域性设置。</span><span class="sxs-lookup"><span data-stu-id="29a7e-105">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="29a7e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29a7e-106">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="29a7e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29a7e-107">DESCRIPTION</span></span>

<span data-ttu-id="29a7e-108">`Get-UICulture`Cmdlet 将获取有关 Windows (UI) 区域性设置的当前用户界面的信息。</span><span class="sxs-lookup"><span data-stu-id="29a7e-108">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="29a7e-109">UI 区域性确定哪些文本字符串用于用户界面元素，例如菜单和消息。</span><span class="sxs-lookup"><span data-stu-id="29a7e-109">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="29a7e-110">你还可以使用 `Get-Culture` cmdlet 来获取系统上的当前区域性。</span><span class="sxs-lookup"><span data-stu-id="29a7e-110">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="29a7e-111">区域性确定项的显示格式，例如数字、货币和日期。</span><span class="sxs-lookup"><span data-stu-id="29a7e-111">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="29a7e-112">示例</span><span class="sxs-lookup"><span data-stu-id="29a7e-112">EXAMPLES</span></span>

### <span data-ttu-id="29a7e-113">示例1：获取 UI 区域性</span><span class="sxs-lookup"><span data-stu-id="29a7e-113">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="29a7e-114">此命令获取当前 UI 区域性信息。</span><span class="sxs-lookup"><span data-stu-id="29a7e-114">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="29a7e-115">示例2：获取 UI 区域性并设置结果格式</span><span class="sxs-lookup"><span data-stu-id="29a7e-115">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="29a7e-116">此命令在列表中显示当前 UI 区域性的所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="29a7e-116">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="29a7e-117">示例3：获取 Calendar 属性的值</span><span class="sxs-lookup"><span data-stu-id="29a7e-117">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="29a7e-118">此命令显示当前 UI 区域性的 **Calendar** 属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="29a7e-118">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="29a7e-119">Calendar 只是 UI 区域性的一个属性。</span><span class="sxs-lookup"><span data-stu-id="29a7e-119">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="29a7e-120">若要查看所有属性，请键入 `Get-UICulture | Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="29a7e-120">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="29a7e-121">示例4：获取短日期模式</span><span class="sxs-lookup"><span data-stu-id="29a7e-121">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="29a7e-122">此命令显示当前 UI 区域性的短日期模式。</span><span class="sxs-lookup"><span data-stu-id="29a7e-122">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="29a7e-123">若要查看 UI 区域性的 **DateTimeFormat** 属性的所有子属性，请键入 `(Get-UICulture).DateTimeFormat | gm` 。</span><span class="sxs-lookup"><span data-stu-id="29a7e-123">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="29a7e-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29a7e-124">PARAMETERS</span></span>

### <span data-ttu-id="29a7e-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="29a7e-125">CommonParameters</span></span>

<span data-ttu-id="29a7e-126">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="29a7e-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29a7e-127">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="29a7e-127">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="29a7e-128">输入</span><span class="sxs-lookup"><span data-stu-id="29a7e-128">INPUTS</span></span>

### <span data-ttu-id="29a7e-129">无</span><span class="sxs-lookup"><span data-stu-id="29a7e-129">None</span></span>

<span data-ttu-id="29a7e-130">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="29a7e-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="29a7e-131">输出</span><span class="sxs-lookup"><span data-stu-id="29a7e-131">OUTPUTS</span></span>

### <span data-ttu-id="29a7e-132">System.Globalization.CultureInfo、Microsoft.PowerShell.VistaCultureInfo</span><span class="sxs-lookup"><span data-stu-id="29a7e-132">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="29a7e-133">`Get-UICulture` 返回表示当前 UI 区域性的对象。</span><span class="sxs-lookup"><span data-stu-id="29a7e-133">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="29a7e-134">在 Windows PowerShell 3.0 中，它返回 **CultureInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="29a7e-134">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="29a7e-135">在 Windows PowerShell 2.0 中，它返回 **VistaCultureInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="29a7e-135">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="29a7e-136">注释</span><span class="sxs-lookup"><span data-stu-id="29a7e-136">NOTES</span></span>

- <span data-ttu-id="29a7e-137">你还可以使用 `$PsCulture` 和 `$PsUICulture` 变量。</span><span class="sxs-lookup"><span data-stu-id="29a7e-137">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="29a7e-138">`$PsCulture`变量存储当前区域性的名称， `$PsUICulture` 变量存储当前 UI 区域性的名称。</span><span class="sxs-lookup"><span data-stu-id="29a7e-138">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="29a7e-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="29a7e-139">RELATED LINKS</span></span>
