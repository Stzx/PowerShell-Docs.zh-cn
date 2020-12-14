---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 1ee55dfaf4ecd3e46bedd8f356b1f677180c9c62
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564548"
---
# <span data-ttu-id="2073c-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="2073c-103">Set-Clipboard</span></span>

## <span data-ttu-id="2073c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2073c-104">SYNOPSIS</span></span>
<span data-ttu-id="2073c-105">设置剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="2073c-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="2073c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2073c-106">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2073c-107">说明</span><span class="sxs-lookup"><span data-stu-id="2073c-107">DESCRIPTION</span></span>

<span data-ttu-id="2073c-108">`Set-Clipboard`Cmdlet 设置剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="2073c-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="2073c-109">在 Linux 上，此 cmdlet 要求 `xclip` 实用工具在路径中。</span><span class="sxs-lookup"><span data-stu-id="2073c-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="2073c-110">示例</span><span class="sxs-lookup"><span data-stu-id="2073c-110">EXAMPLES</span></span>

### <span data-ttu-id="2073c-111">示例1：将文本复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="2073c-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="2073c-112">示例2：将文件的内容复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="2073c-112">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="2073c-113">此示例将文件的内容传输到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="2073c-113">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="2073c-114">在此示例中，我们将获得一个公共 ssh 密钥，以便可以将其粘贴到其他应用程序（例如 GitHub）中。</span><span class="sxs-lookup"><span data-stu-id="2073c-114">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="2073c-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2073c-115">PARAMETERS</span></span>

### <span data-ttu-id="2073c-116">-Append</span><span class="sxs-lookup"><span data-stu-id="2073c-116">-Append</span></span>

<span data-ttu-id="2073c-117">指示 cmdlet 不清除剪贴板，并向其追加内容。</span><span class="sxs-lookup"><span data-stu-id="2073c-117">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="2073c-118">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2073c-118">-Confirm</span></span>

<span data-ttu-id="2073c-119">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="2073c-119">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2073c-120">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2073c-120">-WhatIf</span></span>

<span data-ttu-id="2073c-121">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="2073c-121">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2073c-122">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2073c-122">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2073c-123">-Value</span><span class="sxs-lookup"><span data-stu-id="2073c-123">-Value</span></span>

<span data-ttu-id="2073c-124">要添加到剪贴板中的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2073c-124">The string values to be added to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2073c-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2073c-125">CommonParameters</span></span>

<span data-ttu-id="2073c-126">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2073c-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2073c-127">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2073c-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2073c-128">输入</span><span class="sxs-lookup"><span data-stu-id="2073c-128">INPUTS</span></span>

### <span data-ttu-id="2073c-129">System.String[]</span><span class="sxs-lookup"><span data-stu-id="2073c-129">System.String[]</span></span>

## <span data-ttu-id="2073c-130">输出</span><span class="sxs-lookup"><span data-stu-id="2073c-130">OUTPUTS</span></span>

## <span data-ttu-id="2073c-131">注释</span><span class="sxs-lookup"><span data-stu-id="2073c-131">NOTES</span></span>

<span data-ttu-id="2073c-132">在极少数情况下 `Set-Clipboard` ，当快速连续使用具有大量值的情况（例如在循环中）时，可能偶尔会从剪贴板获取空白值。</span><span class="sxs-lookup"><span data-stu-id="2073c-132">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="2073c-133">可以通过在循环中使用来解决此情况 `Start-Sleep -Milliseconds 1` 。</span><span class="sxs-lookup"><span data-stu-id="2073c-133">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="2073c-134">相关链接</span><span class="sxs-lookup"><span data-stu-id="2073c-134">RELATED LINKS</span></span>

[<span data-ttu-id="2073c-135">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="2073c-135">Get-Clipboard</span></span>](Get-Clipboard.md)
