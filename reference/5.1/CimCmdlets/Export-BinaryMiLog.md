---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197544"
---
# <span data-ttu-id="4950c-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="4950c-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="4950c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4950c-104">SYNOPSIS</span></span>
<span data-ttu-id="4950c-105">创建对象或对象的二进制编码表示形式，并将其存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="4950c-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="4950c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4950c-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="4950c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4950c-107">DESCRIPTION</span></span>

<span data-ttu-id="4950c-108">`Export-BinaryMILog`Cmdlet 创建对象或对象的基于二进制的表示形式，并将其存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="4950c-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="4950c-109">然后，可以使用 `Import-BinaryMiLog` cmdlet 基于该文件的内容重新创建已保存的对象。</span><span class="sxs-lookup"><span data-stu-id="4950c-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="4950c-110">此 cmdlet 类似于 `Import-Clixml` ，不同之处在于将 `Export-BinaryMILog` 生成的对象存储在二进制编码的文件中。</span><span class="sxs-lookup"><span data-stu-id="4950c-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="4950c-111">示例</span><span class="sxs-lookup"><span data-stu-id="4950c-111">EXAMPLES</span></span>

### <span data-ttu-id="4950c-112">示例 1-创建 CimInstances 的二进制表示形式</span><span class="sxs-lookup"><span data-stu-id="4950c-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="4950c-113">此命令将 **CimInstances** 导出到 Path 参数所指定的二进制 MI 日志文件。</span><span class="sxs-lookup"><span data-stu-id="4950c-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="4950c-114">请参阅 Import-BinaryMiLog 的示例，了解如何通过导入此文件来重新创建 **CimInstances** 。</span><span class="sxs-lookup"><span data-stu-id="4950c-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="4950c-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4950c-115">PARAMETERS</span></span>

### <span data-ttu-id="4950c-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4950c-116">-InputObject</span></span>

<span data-ttu-id="4950c-117">指定此 cmdlet 的输入。</span><span class="sxs-lookup"><span data-stu-id="4950c-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="4950c-118">可以使用此参数，也可以通过管道传送此 cmdlet 的输入。</span><span class="sxs-lookup"><span data-stu-id="4950c-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4950c-119">-Path</span><span class="sxs-lookup"><span data-stu-id="4950c-119">-Path</span></span>

<span data-ttu-id="4950c-120">指定要在其中存储对象的二进制表示形式的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4950c-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="4950c-121">**Path** 参数支持通配符和相对路径。</span><span class="sxs-lookup"><span data-stu-id="4950c-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="4950c-122">如果路径解析为多个文件，则此 cmdlet 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="4950c-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4950c-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4950c-123">CommonParameters</span></span>

<span data-ttu-id="4950c-124">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4950c-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4950c-125">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4950c-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4950c-126">输入</span><span class="sxs-lookup"><span data-stu-id="4950c-126">INPUTS</span></span>

### <span data-ttu-id="4950c-127">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="4950c-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="4950c-128">输出</span><span class="sxs-lookup"><span data-stu-id="4950c-128">OUTPUTS</span></span>

### <span data-ttu-id="4950c-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="4950c-129">System.Object</span></span>

## <span data-ttu-id="4950c-130">注释</span><span class="sxs-lookup"><span data-stu-id="4950c-130">NOTES</span></span>

## <span data-ttu-id="4950c-131">相关链接</span><span class="sxs-lookup"><span data-stu-id="4950c-131">RELATED LINKS</span></span>

[<span data-ttu-id="4950c-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="4950c-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="4950c-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="4950c-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="4950c-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="4950c-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
