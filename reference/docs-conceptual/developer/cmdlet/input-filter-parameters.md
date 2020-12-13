---
ms.date: 09/13/2016
ms.topic: reference
title: 输入筛选参数
description: 输入筛选参数
ms.openlocfilehash: 419ffea2afb4aa534a3e19ecdfce6d6af1da46a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648531"
---
# <a name="input-filter-parameters"></a><span data-ttu-id="a1dff-103">输入筛选参数</span><span class="sxs-lookup"><span data-stu-id="a1dff-103">Input Filter Parameters</span></span>

<span data-ttu-id="a1dff-104">Cmdlet 可以定义 `Filter` 、 `Include` 和参数， `Exclude` 以筛选该 cmdlet 影响的输入对象集。</span><span class="sxs-lookup"><span data-stu-id="a1dff-104">A cmdlet can define `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

<span data-ttu-id="a1dff-105">通常，输入对象集由 `InputObject` 、 `Path` 或 `Name` 参数指定。</span><span class="sxs-lookup"><span data-stu-id="a1dff-105">Typically, the set of input objects is specified by an `InputObject`, `Path`, or `Name` parameter.</span></span> <span data-ttu-id="a1dff-106">例如，一个 cmdlet 可以有一个 `Path` 参数，该参数使用通配符来接受多个路径，并且每个路径指向一个输入对象。</span><span class="sxs-lookup"><span data-stu-id="a1dff-106">For example, a cmdlet can have a `Path` parameter that accepts multiple paths by using wildcard characters, and each path points to an input object.</span></span> <span data-ttu-id="a1dff-107">一起使用时， `Filter` 、 `Include` 和 `Exclude` 参数会进一步限定 cmdlet 在每次调用时所使用的路径。</span><span class="sxs-lookup"><span data-stu-id="a1dff-107">Used together, the `Filter`, `Include`, and `Exclude` parameters further qualify the paths the cmdlet works on each time it is invoked.</span></span>

## <a name="include-and-exclude-parameters"></a><span data-ttu-id="a1dff-108">包括和排除参数</span><span class="sxs-lookup"><span data-stu-id="a1dff-108">Include and Exclude Parameters</span></span>

<span data-ttu-id="a1dff-109">`Include`和 `Exclude` 参数标识传递到 cmdlet 的输入对象集中包含或排除的对象。</span><span class="sxs-lookup"><span data-stu-id="a1dff-109">The `Include` and `Exclude` parameters identify the objects that are included or excluded from the set of input objects passed to the cmdlet.</span></span> <span data-ttu-id="a1dff-110">如果筛选器可以用标准通配符语言表示，请使用这些参数。</span><span class="sxs-lookup"><span data-stu-id="a1dff-110">Use these parameters when the filter can be expressed in the standard wildcard language.</span></span> <span data-ttu-id="a1dff-111"> (有关通配符的详细信息，请参阅 [在 Cmdlet 参数中支持通配符](./supporting-wildcard-characters-in-cmdlet-parameters.md)。 ) `Include` 参数包括名称与包含筛选器匹配的所有对象。</span><span class="sxs-lookup"><span data-stu-id="a1dff-111">(For more information about wildcard characters, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).) The `Include` parameter includes all the objects whose names match the inclusion filter.</span></span> <span data-ttu-id="a1dff-112">`Exclude`参数会排除名称与筛选器匹配的所有对象。</span><span class="sxs-lookup"><span data-stu-id="a1dff-112">The `Exclude` parameter excludes all the objects whose names match the filter.</span></span>

## <a name="filter-parameter"></a><span data-ttu-id="a1dff-113">筛选器参数</span><span class="sxs-lookup"><span data-stu-id="a1dff-113">Filter Parameter</span></span>

<span data-ttu-id="a1dff-114">`Filter`参数指定了不以标准通配符语言表示的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a1dff-114">The `Filter` parameter specifies a filter that is not expressed in the standard wildcard language.</span></span> <span data-ttu-id="a1dff-115">例如，Active Directory 服务接口 (ADSI) 或 SQL 筛选器都可以通过其参数传递给 cmdlet `Filter` 。</span><span class="sxs-lookup"><span data-stu-id="a1dff-115">For example, Active Directory Service Interfaces (ADSI) or SQL filters might be passed to the cmdlet through its `Filter` parameter.</span></span> <span data-ttu-id="a1dff-116">在 Windows PowerShell 提供的 cmdlet 中，这些筛选器由使用 cmdlet 访问数据存储的 Windows PowerShell 提供程序指定。</span><span class="sxs-lookup"><span data-stu-id="a1dff-116">In the cmdlets provided by Windows PowerShell, these filters are specified by the Windows PowerShell providers that use the cmdlet to access a data store.</span></span> <span data-ttu-id="a1dff-117">每个提供程序通常定义自己的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a1dff-117">Each provider typically defines its own filter.</span></span>

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a><span data-ttu-id="a1dff-118">如果未指定任何输入对象集，则进行筛选</span><span class="sxs-lookup"><span data-stu-id="a1dff-118">Filtering If No Set of Input Objects Is Specified</span></span>

<span data-ttu-id="a1dff-119">如果未指定任何输入对象集，这通常意味着要针对所有对象进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a1dff-119">If no set of input objects is specified, this typically means to filter against all objects.</span></span> <span data-ttu-id="a1dff-120">有关详细信息，请参阅[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)。</span><span class="sxs-lookup"><span data-stu-id="a1dff-120">For more information, see[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1dff-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1dff-121">See Also</span></span>

[<span data-ttu-id="a1dff-122">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a1dff-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
