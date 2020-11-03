---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 80d30b5c3b33c3e4f8125db3a158166a00f7e816
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196738"
---
# <span data-ttu-id="b0abd-103">New-Guid</span><span class="sxs-lookup"><span data-stu-id="b0abd-103">New-Guid</span></span>

## <span data-ttu-id="b0abd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b0abd-104">SYNOPSIS</span></span>
<span data-ttu-id="b0abd-105">创建 GUID。</span><span class="sxs-lookup"><span data-stu-id="b0abd-105">Creates a GUID.</span></span>

## <span data-ttu-id="b0abd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0abd-106">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="b0abd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0abd-107">DESCRIPTION</span></span>

<span data-ttu-id="b0abd-108">Guid **)** (guid 创建随机全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b0abd-108">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="b0abd-109">如果需要在脚本中使用唯一的 ID，可以根据需要创建一个 GUID。</span><span class="sxs-lookup"><span data-stu-id="b0abd-109">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="b0abd-110">示例</span><span class="sxs-lookup"><span data-stu-id="b0abd-110">EXAMPLES</span></span>

### <span data-ttu-id="b0abd-111">示例1：创建 GUID</span><span class="sxs-lookup"><span data-stu-id="b0abd-111">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="b0abd-112">此命令创建随机 GUID。</span><span class="sxs-lookup"><span data-stu-id="b0abd-112">This command creates a random GUID.</span></span>
<span data-ttu-id="b0abd-113">或者，你可以将此 cmdlet 的输出存储在一个变量中，以在脚本中的其他位置使用。</span><span class="sxs-lookup"><span data-stu-id="b0abd-113">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="b0abd-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0abd-114">PARAMETERS</span></span>

### <span data-ttu-id="b0abd-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b0abd-115">CommonParameters</span></span>

<span data-ttu-id="b0abd-116">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b0abd-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0abd-117">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b0abd-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0abd-118">输入</span><span class="sxs-lookup"><span data-stu-id="b0abd-118">INPUTS</span></span>

## <span data-ttu-id="b0abd-119">输出</span><span class="sxs-lookup"><span data-stu-id="b0abd-119">OUTPUTS</span></span>

### <span data-ttu-id="b0abd-120">System.Guid</span><span class="sxs-lookup"><span data-stu-id="b0abd-120">System.Guid</span></span>

<span data-ttu-id="b0abd-121">此 cmdlet 将返回 GUID。</span><span class="sxs-lookup"><span data-stu-id="b0abd-121">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="b0abd-122">注释</span><span class="sxs-lookup"><span data-stu-id="b0abd-122">NOTES</span></span>

## <span data-ttu-id="b0abd-123">相关链接</span><span class="sxs-lookup"><span data-stu-id="b0abd-123">RELATED LINKS</span></span>
