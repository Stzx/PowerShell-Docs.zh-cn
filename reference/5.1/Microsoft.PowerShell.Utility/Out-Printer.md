---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-printer
ms.openlocfilehash: ec8d080da133310270d022b00f7f92d08ea3ca41
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197875"
---
# <span data-ttu-id="72dfe-103">Out-printer</span><span class="sxs-lookup"><span data-stu-id="72dfe-103">Out-Printer</span></span>

## <span data-ttu-id="72dfe-104">摘要</span><span class="sxs-lookup"><span data-stu-id="72dfe-104">SYNOPSIS</span></span>
<span data-ttu-id="72dfe-105">将输出发送到打印机。</span><span class="sxs-lookup"><span data-stu-id="72dfe-105">Sends output to a printer.</span></span>

## <span data-ttu-id="72dfe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="72dfe-106">SYNTAX</span></span>

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="72dfe-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="72dfe-107">DESCRIPTION</span></span>

<span data-ttu-id="72dfe-108">`Out-Printer`Cmdlet 将输出发送到默认打印机或备用打印机（如果已指定）。</span><span class="sxs-lookup"><span data-stu-id="72dfe-108">The `Out-Printer` cmdlet sends output to the default printer or to an alternate printer, if one is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="72dfe-109">此 cmdlet 已在 PowerShell 7 中引入。</span><span class="sxs-lookup"><span data-stu-id="72dfe-109">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="72dfe-110">此 cmdlet 仅适用于支持 Windows 桌面的 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="72dfe-110">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="72dfe-111">示例</span><span class="sxs-lookup"><span data-stu-id="72dfe-111">EXAMPLES</span></span>

### <span data-ttu-id="72dfe-112">示例 1-发送要在默认打印机上打印的文件</span><span class="sxs-lookup"><span data-stu-id="72dfe-112">Example 1 - Send a file to be printed on the default printer</span></span>

<span data-ttu-id="72dfe-113">此示例演示如何打印文件，即使没有 `Out-Printer` **路径** 参数。</span><span class="sxs-lookup"><span data-stu-id="72dfe-113">This example shows how to print a file, even though `Out-Printer` does not have a **Path** parameter.</span></span>

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

<span data-ttu-id="72dfe-114">`Get-Content`获取 `readme.txt` 当前目录中文件的内容，并将其传递给 `Out-Printer` 默认打印机。</span><span class="sxs-lookup"><span data-stu-id="72dfe-114">`Get-Content`gets the contents of the `readme.txt` file in the current directory and pipes it to `Out-Printer`, which sends it to the default printer.</span></span>

### <span data-ttu-id="72dfe-115">示例2：将字符串打印到远程打印机</span><span class="sxs-lookup"><span data-stu-id="72dfe-115">Example 2: Print a string to a remote printer</span></span>

<span data-ttu-id="72dfe-116">此示例将打印 `Hello, World` 到 Server01 上的 **Prt-6b 彩色** 打印机。</span><span class="sxs-lookup"><span data-stu-id="72dfe-116">This example prints `Hello, World` to the **Prt-6B Color** printer on Server01.</span></span>

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

<span data-ttu-id="72dfe-117">**Name** 参数选择特定打印机，而不是默认打印机。</span><span class="sxs-lookup"><span data-stu-id="72dfe-117">The **Name** parameter selects a specific printer, rather than the default.</span></span>

### <span data-ttu-id="72dfe-118">示例 3-将帮助主题打印到默认打印机</span><span class="sxs-lookup"><span data-stu-id="72dfe-118">Example 3 - Print a help topic to the default printer</span></span>

<span data-ttu-id="72dfe-119">此示例将打印的帮助主题的完整版本 `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="72dfe-119">This example prints the full version of the Help topic for `Get-CimInstance`.</span></span>

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

<span data-ttu-id="72dfe-120">`Get-Help` 获取帮助主题的完整版本 `Get-CimInstance` ，并将其存储在变量中 `$H` 。</span><span class="sxs-lookup"><span data-stu-id="72dfe-120">`Get-Help` gets the full version of the Help topic for `Get-CimInstance` and stores it in the `$H` variable.</span></span> <span data-ttu-id="72dfe-121">**InputObject** 参数将值传递 `$H` 给 `Out-Printer` 。</span><span class="sxs-lookup"><span data-stu-id="72dfe-121">The **InputObject** parameter passes the value of `$H` to `Out-Printer`.</span></span>

## <span data-ttu-id="72dfe-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="72dfe-122">PARAMETERS</span></span>

### <span data-ttu-id="72dfe-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="72dfe-123">-InputObject</span></span>

<span data-ttu-id="72dfe-124">指定要发送到打印机的对象。</span><span class="sxs-lookup"><span data-stu-id="72dfe-124">Specifies the objects to be sent to the printer.</span></span> <span data-ttu-id="72dfe-125">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="72dfe-125">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="72dfe-126">-Name</span><span class="sxs-lookup"><span data-stu-id="72dfe-126">-Name</span></span>

<span data-ttu-id="72dfe-127">将输出发送到指定打印机。</span><span class="sxs-lookup"><span data-stu-id="72dfe-127">Sends the output to the specified printer.</span></span> <span data-ttu-id="72dfe-128">参数名称 **名称** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="72dfe-128">The parameter name **Name** is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="72dfe-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="72dfe-129">CommonParameters</span></span>

<span data-ttu-id="72dfe-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="72dfe-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="72dfe-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="72dfe-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="72dfe-132">输入</span><span class="sxs-lookup"><span data-stu-id="72dfe-132">INPUTS</span></span>

### <span data-ttu-id="72dfe-133">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="72dfe-133">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="72dfe-134">可以通过管道将任何对象传递给 `Out-Printer` 。</span><span class="sxs-lookup"><span data-stu-id="72dfe-134">You can pipe any object to `Out-Printer`.</span></span>

## <span data-ttu-id="72dfe-135">输出</span><span class="sxs-lookup"><span data-stu-id="72dfe-135">OUTPUTS</span></span>

### <span data-ttu-id="72dfe-136">无</span><span class="sxs-lookup"><span data-stu-id="72dfe-136">None</span></span>

<span data-ttu-id="72dfe-137">`Out-Printer` 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="72dfe-137">`Out-Printer` does not return any objects.</span></span>

## <span data-ttu-id="72dfe-138">注释</span><span class="sxs-lookup"><span data-stu-id="72dfe-138">NOTES</span></span>

<span data-ttu-id="72dfe-139">包含谓词的 cmdlet `Out` 不对对象进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="72dfe-139">The cmdlets that contain the `Out` verb do not format objects.</span></span> <span data-ttu-id="72dfe-140">它们只是渲染它们并将其发送到指定的显示目标。</span><span class="sxs-lookup"><span data-stu-id="72dfe-140">They just render them and send them to the specified display destination.</span></span> <span data-ttu-id="72dfe-141">如果将无格式对象发送到 `Out` cmdlet，则该 cmdlet 会在呈现该对象之前将其发送到格式设置 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72dfe-141">If you send an unformatted object to an `Out` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="72dfe-142">`Out-Printer` 将数据发送到打印机，但不向管道发出任何输出对象。</span><span class="sxs-lookup"><span data-stu-id="72dfe-142">`Out-Printer` sends data to the printer, but does not emit any output objects to the pipeline.</span></span> <span data-ttu-id="72dfe-143">如果通过管道将输出传递 `Out-Printer` 给 `Get-Member` ，则会 `Get-Member` 报告未指定任何对象。</span><span class="sxs-lookup"><span data-stu-id="72dfe-143">If you pipe the output of `Out-Printer` to `Get-Member`, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="72dfe-144">相关链接</span><span class="sxs-lookup"><span data-stu-id="72dfe-144">RELATED LINKS</span></span>

[<span data-ttu-id="72dfe-145">Out-File</span><span class="sxs-lookup"><span data-stu-id="72dfe-145">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="72dfe-146">Out-String</span><span class="sxs-lookup"><span data-stu-id="72dfe-146">Out-String</span></span>](Out-String.md)
