---
title: 数量参数 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781811"
---
# <a name="quantity-parameters"></a><span data-ttu-id="ce24f-102">数量参数</span><span class="sxs-lookup"><span data-stu-id="ce24f-102">Quantity Parameters</span></span>

<span data-ttu-id="ce24f-103">下表列出了用于数量参数的建议名称和功能。</span><span class="sxs-lookup"><span data-stu-id="ce24f-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="ce24f-104">参数</span><span class="sxs-lookup"><span data-stu-id="ce24f-104">Parameter</span></span>|<span data-ttu-id="ce24f-105">功能</span><span class="sxs-lookup"><span data-stu-id="ce24f-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="ce24f-106">**全部**</span><span class="sxs-lookup"><span data-stu-id="ce24f-106">**All**</span></span><br><span data-ttu-id="ce24f-107">数据类型：布尔值</span><span class="sxs-lookup"><span data-stu-id="ce24f-107">Data type: Boolean</span></span>|<span data-ttu-id="ce24f-108">实现此参数，以 `true` 指示应对所有资源，而不是默认的资源子集。</span><span class="sxs-lookup"><span data-stu-id="ce24f-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="ce24f-109">实现此参数以 `false` 指示资源的子集。</span><span class="sxs-lookup"><span data-stu-id="ce24f-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="ce24f-110">Allocation\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ce24f-110">**Allocation**</span></span><br><span data-ttu-id="ce24f-111">数据类型： Int32</span><span class="sxs-lookup"><span data-stu-id="ce24f-111">Data type: Int32</span></span>|<span data-ttu-id="ce24f-112">实现此参数，以便用户可以指定要分配的项数。</span><span class="sxs-lookup"><span data-stu-id="ce24f-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="ce24f-113">**BlockCount**</span><span class="sxs-lookup"><span data-stu-id="ce24f-113">**BlockCount**</span></span><br><span data-ttu-id="ce24f-114">数据类型： Int64</span><span class="sxs-lookup"><span data-stu-id="ce24f-114">Data type: Int64</span></span>|<span data-ttu-id="ce24f-115">实现此参数，以便用户可以指定块计数。</span><span class="sxs-lookup"><span data-stu-id="ce24f-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="ce24f-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="ce24f-116">**Count**</span></span><br><span data-ttu-id="ce24f-117">数据类型： Int64</span><span class="sxs-lookup"><span data-stu-id="ce24f-117">Data type: Int64</span></span>|<span data-ttu-id="ce24f-118">实现此参数，以便用户可以指定计数。</span><span class="sxs-lookup"><span data-stu-id="ce24f-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="ce24f-119">**范围**</span><span class="sxs-lookup"><span data-stu-id="ce24f-119">**Scope**</span></span><br><span data-ttu-id="ce24f-120">数据类型：关键字</span><span class="sxs-lookup"><span data-stu-id="ce24f-120">Data type: Keyword</span></span>|<span data-ttu-id="ce24f-121">实现此参数，以便用户可以指定要操作的范围。</span><span class="sxs-lookup"><span data-stu-id="ce24f-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ce24f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce24f-122">See Also</span></span>

[<span data-ttu-id="ce24f-123">Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="ce24f-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="ce24f-124">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ce24f-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="ce24f-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="ce24f-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
