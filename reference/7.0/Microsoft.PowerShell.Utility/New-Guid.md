---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 0356b0f9a0792cd75828bf735e7806b5cca0daa3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93194626"
---
# <span data-ttu-id="fbe4f-103">New-Guid</span><span class="sxs-lookup"><span data-stu-id="fbe4f-103">New-Guid</span></span>

## <span data-ttu-id="fbe4f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fbe4f-104">SYNOPSIS</span></span>
<span data-ttu-id="fbe4f-105">创建 GUID。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-105">Creates a GUID.</span></span>

## <span data-ttu-id="fbe4f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbe4f-106">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="fbe4f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbe4f-107">DESCRIPTION</span></span>

<span data-ttu-id="fbe4f-108">Guid **)** (guid 创建随机全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-108">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="fbe4f-109">如果需要在脚本中使用唯一的 ID，可以根据需要创建一个 GUID。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-109">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="fbe4f-110">示例</span><span class="sxs-lookup"><span data-stu-id="fbe4f-110">EXAMPLES</span></span>

### <span data-ttu-id="fbe4f-111">示例1：创建 GUID</span><span class="sxs-lookup"><span data-stu-id="fbe4f-111">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="fbe4f-112">此命令创建随机 GUID。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-112">This command creates a random GUID.</span></span>
<span data-ttu-id="fbe4f-113">或者，你可以将此 cmdlet 的输出存储在一个变量中，以在脚本中的其他位置使用。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-113">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="fbe4f-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbe4f-114">PARAMETERS</span></span>

### <span data-ttu-id="fbe4f-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fbe4f-115">CommonParameters</span></span>

<span data-ttu-id="fbe4f-116">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbe4f-117">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbe4f-118">输入</span><span class="sxs-lookup"><span data-stu-id="fbe4f-118">INPUTS</span></span>

## <span data-ttu-id="fbe4f-119">输出</span><span class="sxs-lookup"><span data-stu-id="fbe4f-119">OUTPUTS</span></span>

### <span data-ttu-id="fbe4f-120">System.Guid</span><span class="sxs-lookup"><span data-stu-id="fbe4f-120">System.Guid</span></span>

<span data-ttu-id="fbe4f-121">此 cmdlet 将返回 GUID。</span><span class="sxs-lookup"><span data-stu-id="fbe4f-121">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="fbe4f-122">注释</span><span class="sxs-lookup"><span data-stu-id="fbe4f-122">NOTES</span></span>

## <span data-ttu-id="fbe4f-123">相关链接</span><span class="sxs-lookup"><span data-stu-id="fbe4f-123">RELATED LINKS</span></span>
