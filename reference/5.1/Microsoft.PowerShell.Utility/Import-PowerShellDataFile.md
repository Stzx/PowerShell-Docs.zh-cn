---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: 61e3a7f941155ccf3db84a7e9ec8d2c48b4cceea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197895"
---
# <span data-ttu-id="a1cc3-103">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="a1cc3-103">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="a1cc3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a1cc3-104">SYNOPSIS</span></span>
<span data-ttu-id="a1cc3-105">从文件中导入值 `.PSD1` ，而不调用其内容。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-105">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="a1cc3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1cc3-106">SYNTAX</span></span>

### <span data-ttu-id="a1cc3-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="a1cc3-107">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [[-Path] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a1cc3-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="a1cc3-108">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a1cc3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1cc3-109">DESCRIPTION</span></span>

<span data-ttu-id="a1cc3-110">`Import-PowerShellDataFile`Cmdlet 从文件中定义的哈希表中安全地导入键值对 `.PSD1` 。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-110">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="a1cc3-111">可以使用文件内容导入这些值 `Invoke-Expression` 。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-111">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="a1cc3-112">但会 `Invoke-Expression` 运行文件中包含的任何代码。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-112">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="a1cc3-113">这可能会产生不需要的结果或执行不安全的代码。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-113">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="a1cc3-114">`Import-PowerShellDataFile` 导入数据而不调用代码。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-114">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span>

## <span data-ttu-id="a1cc3-115">示例</span><span class="sxs-lookup"><span data-stu-id="a1cc3-115">EXAMPLES</span></span>

### <span data-ttu-id="a1cc3-116">示例1：从 PSD1 检索值</span><span class="sxs-lookup"><span data-stu-id="a1cc3-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="a1cc3-117">此示例检索存储在存储在文件中的哈希表中的键/值对 `Configuration.psd1` 。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="a1cc3-118">`Get-Content` 用于显示文件的内容 `Configuration.psd1` 。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## <span data-ttu-id="a1cc3-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1cc3-119">PARAMETERS</span></span>

### <span data-ttu-id="a1cc3-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a1cc3-120">-LiteralPath</span></span>

<span data-ttu-id="a1cc3-121">要导入的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-121">The path to the file being imported.</span></span> <span data-ttu-id="a1cc3-122">路径中的所有字符都被视为文本值。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="a1cc3-123">不处理通配符。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-123">Wildcard characters are not processed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a1cc3-124">-Path</span><span class="sxs-lookup"><span data-stu-id="a1cc3-124">-Path</span></span>

<span data-ttu-id="a1cc3-125">要导入的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-125">The path to the file being imported.</span></span> <span data-ttu-id="a1cc3-126">允许使用通配符，但只导入第一个匹配文件。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-126">Wildcards are allowed but only the first matching file is imported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a1cc3-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a1cc3-127">CommonParameters</span></span>

<span data-ttu-id="a1cc3-128">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a1cc3-129">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a1cc3-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a1cc3-130">输入</span><span class="sxs-lookup"><span data-stu-id="a1cc3-130">INPUTS</span></span>

## <span data-ttu-id="a1cc3-131">输出</span><span class="sxs-lookup"><span data-stu-id="a1cc3-131">OUTPUTS</span></span>

### <span data-ttu-id="a1cc3-132">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="a1cc3-132">System.Collections.Hashtable</span></span>

## <span data-ttu-id="a1cc3-133">注释</span><span class="sxs-lookup"><span data-stu-id="a1cc3-133">NOTES</span></span>

## <span data-ttu-id="a1cc3-134">相关链接</span><span class="sxs-lookup"><span data-stu-id="a1cc3-134">RELATED LINKS</span></span>

[<span data-ttu-id="a1cc3-135">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="a1cc3-135">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="a1cc3-136">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="a1cc3-136">Import-LocalizedData</span></span>](Import-LocalizedData.md)
