---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce5dd31170bc47edaa04ca3c31deab62dc4ec354
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200679"
---
# <span data-ttu-id="32b2f-103">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="32b2f-103">Import-BinaryMiLog</span></span>

## <span data-ttu-id="32b2f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="32b2f-104">SYNOPSIS</span></span>
<span data-ttu-id="32b2f-105">用于根据导出文件的内容重新创建已保存的对象。</span><span class="sxs-lookup"><span data-stu-id="32b2f-105">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="32b2f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32b2f-106">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="32b2f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32b2f-107">DESCRIPTION</span></span>

<span data-ttu-id="32b2f-108">使用此 cmdlet 可根据创建的导出文件的内容重新创建已保存的对象 `Export-BinaryMILog` 。</span><span class="sxs-lookup"><span data-stu-id="32b2f-108">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="32b2f-109">此 cmdlet 类似于 `Import-Clixml` ，不同之处在于将 `Export-BinaryMILog` 生成的对象存储在二进制编码的文件中。</span><span class="sxs-lookup"><span data-stu-id="32b2f-109">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="32b2f-110">示例</span><span class="sxs-lookup"><span data-stu-id="32b2f-110">EXAMPLES</span></span>

### <span data-ttu-id="32b2f-111">示例 1-还原导出到文件的对象</span><span class="sxs-lookup"><span data-stu-id="32b2f-111">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="32b2f-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32b2f-112">PARAMETERS</span></span>

### <span data-ttu-id="32b2f-113">-Path</span><span class="sxs-lookup"><span data-stu-id="32b2f-113">-Path</span></span>

<span data-ttu-id="32b2f-114">指定要在其中存储对象的二进制表示形式的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="32b2f-114">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="32b2f-115">**Path** 参数支持通配符和相对路径。</span><span class="sxs-lookup"><span data-stu-id="32b2f-115">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="32b2f-116">如果路径解析为多个文件，则此 cmdlet 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="32b2f-116">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="32b2f-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32b2f-117">CommonParameters</span></span>
<span data-ttu-id="32b2f-118">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="32b2f-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32b2f-119">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="32b2f-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32b2f-120">输入</span><span class="sxs-lookup"><span data-stu-id="32b2f-120">INPUTS</span></span>

### <span data-ttu-id="32b2f-121">无</span><span class="sxs-lookup"><span data-stu-id="32b2f-121">None</span></span>

## <span data-ttu-id="32b2f-122">输出</span><span class="sxs-lookup"><span data-stu-id="32b2f-122">OUTPUTS</span></span>

### <span data-ttu-id="32b2f-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="32b2f-123">System.Object</span></span>

## <span data-ttu-id="32b2f-124">注释</span><span class="sxs-lookup"><span data-stu-id="32b2f-124">NOTES</span></span>

## <span data-ttu-id="32b2f-125">相关链接</span><span class="sxs-lookup"><span data-stu-id="32b2f-125">RELATED LINKS</span></span>
