---
ms.date: 09/13/2016
ms.topic: reference
title: 数量参数
description: 数量参数
ms.openlocfilehash: 3f7c23eec34a709b1f2d59f611c93909b20f4124
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650305"
---
# <a name="quantity-parameters"></a><span data-ttu-id="f33be-103">数量参数</span><span class="sxs-lookup"><span data-stu-id="f33be-103">Quantity Parameters</span></span>

<span data-ttu-id="f33be-104">下表列出了用于数量参数的建议名称和功能。</span><span class="sxs-lookup"><span data-stu-id="f33be-104">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="f33be-105">参数</span><span class="sxs-lookup"><span data-stu-id="f33be-105">Parameter</span></span>|<span data-ttu-id="f33be-106">功能</span><span class="sxs-lookup"><span data-stu-id="f33be-106">Functionality</span></span>|
|---|---|
|<span data-ttu-id="f33be-107">**All**</span><span class="sxs-lookup"><span data-stu-id="f33be-107">**All**</span></span><br><span data-ttu-id="f33be-108">数据类型：布尔值</span><span class="sxs-lookup"><span data-stu-id="f33be-108">Data type: Boolean</span></span>|<span data-ttu-id="f33be-109">实现此参数，以 `true` 指示应对所有资源，而不是默认的资源子集。</span><span class="sxs-lookup"><span data-stu-id="f33be-109">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="f33be-110">实现此参数以 `false` 指示资源的子集。</span><span class="sxs-lookup"><span data-stu-id="f33be-110">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="f33be-111">Allocation</span><span class="sxs-lookup"><span data-stu-id="f33be-111">**Allocation**</span></span><br><span data-ttu-id="f33be-112">数据类型： Int32</span><span class="sxs-lookup"><span data-stu-id="f33be-112">Data type: Int32</span></span>|<span data-ttu-id="f33be-113">实现此参数，以便用户可以指定要分配的项数。</span><span class="sxs-lookup"><span data-stu-id="f33be-113">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="f33be-114">**BlockCount**</span><span class="sxs-lookup"><span data-stu-id="f33be-114">**BlockCount**</span></span><br><span data-ttu-id="f33be-115">数据类型： Int64</span><span class="sxs-lookup"><span data-stu-id="f33be-115">Data type: Int64</span></span>|<span data-ttu-id="f33be-116">实现此参数，以便用户可以指定块计数。</span><span class="sxs-lookup"><span data-stu-id="f33be-116">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="f33be-117">“计数”</span><span class="sxs-lookup"><span data-stu-id="f33be-117">**Count**</span></span><br><span data-ttu-id="f33be-118">数据类型： Int64</span><span class="sxs-lookup"><span data-stu-id="f33be-118">Data type: Int64</span></span>|<span data-ttu-id="f33be-119">实现此参数，以便用户可以指定计数。</span><span class="sxs-lookup"><span data-stu-id="f33be-119">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="f33be-120">**范围**</span><span class="sxs-lookup"><span data-stu-id="f33be-120">**Scope**</span></span><br><span data-ttu-id="f33be-121">数据类型：关键字</span><span class="sxs-lookup"><span data-stu-id="f33be-121">Data type: Keyword</span></span>|<span data-ttu-id="f33be-122">实现此参数，以便用户可以指定要操作的范围。</span><span class="sxs-lookup"><span data-stu-id="f33be-122">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f33be-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f33be-123">See Also</span></span>

[<span data-ttu-id="f33be-124">Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="f33be-124">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="f33be-125">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f33be-125">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="f33be-126">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f33be-126">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
