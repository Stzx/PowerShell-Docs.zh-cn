---
title: 扩展类型系统成员集
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: 11e1e7819efecc1f1d8164ef32fb97cda978e748
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217923"
---
# <a name="ets-member-sets"></a><span data-ttu-id="4c957-102">ETS 成员集</span><span class="sxs-lookup"><span data-stu-id="4c957-102">ETS member sets</span></span>

<span data-ttu-id="4c957-103">成员集允许您将**PSObject**对象的成员分区为两个子集，以便可以通过其子集名称同时引用子集的成员。</span><span class="sxs-lookup"><span data-stu-id="4c957-103">Member sets allow you to partition the members of the **PSObject** object into two subsets so that the members of the subsets can be referenced together by their subset name.</span></span> <span data-ttu-id="4c957-104">这两种类型的子集包括属性集和成员集。</span><span class="sxs-lookup"><span data-stu-id="4c957-104">The two types of subsets include property sets and member sets.</span></span> <span data-ttu-id="4c957-105">例如，如果 PowerShell 使用成员集，则存在一个名为**使用 defaultdisplaypropertyset**的特定属性集，用于在运行时确定要为给定**PSObject**对象显示哪些属性。</span><span class="sxs-lookup"><span data-stu-id="4c957-105">For example of how PowerShell uses member sets, there is a specific property set named **DefaultDisplayPropertySet** that is used to determine, at runtime, which properties to display for a given **PSObject** object.</span></span>

## <a name="property-sets"></a><span data-ttu-id="4c957-106">属性集</span><span class="sxs-lookup"><span data-stu-id="4c957-106">Property Sets</span></span>

<span data-ttu-id="4c957-107">属性集可以包含**PSObject**类型的任意数量的属性。</span><span class="sxs-lookup"><span data-stu-id="4c957-107">Property sets can include any number of properties of an **PSObject** type.</span></span> <span data-ttu-id="4c957-108">通常情况下，只要需要同一类型)  (属性集，就可以使用属性集。</span><span class="sxs-lookup"><span data-stu-id="4c957-108">In general, a property set can be used whenever a collection of properties (of the same type) is needed.</span></span> <span data-ttu-id="4c957-109">通过 `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` 使用属性集的名称和引用属性的名称调用构造函数来创建属性集。</span><span class="sxs-lookup"><span data-stu-id="4c957-109">The property set is created by calling the `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` constructor with the name of the property set and the names of the referenced properties.</span></span> <span data-ttu-id="4c957-110">然后，创建的**PSPropertySet**对象可用作指向集中属性的别名。</span><span class="sxs-lookup"><span data-stu-id="4c957-110">The created **PSPropertySet** object can then be used as an alias that points to the properties in the set.</span></span> <span data-ttu-id="4c957-111">[PSPropertySet](/dotnet/api/system.management.automation.pspropertyset)类具有以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="4c957-111">The [PSPropertySet](/dotnet/api/system.management.automation.pspropertyset) class has the following properties and methods.</span></span>

- <span data-ttu-id="4c957-112">**IsInstance**属性：获取一个**布尔**值，该值指示属性的源。</span><span class="sxs-lookup"><span data-stu-id="4c957-112">**IsInstance** property: Gets a **Boolean** value that indicates the source of the property.</span></span>
- <span data-ttu-id="4c957-113">**MemberType**属性：获取属性集中的属性类型。</span><span class="sxs-lookup"><span data-stu-id="4c957-113">**MemberType** property: Gets the type of properties in the property set.</span></span>
- <span data-ttu-id="4c957-114">**Name**属性：获取属性集的名称。</span><span class="sxs-lookup"><span data-stu-id="4c957-114">**Name** property: Gets the name of the property set.</span></span>
- <span data-ttu-id="4c957-115">**ReferencedPropertyNames**属性：获取属性集中属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4c957-115">**ReferencedPropertyNames** property: Gets the names of the properties in the property set.</span></span>
- <span data-ttu-id="4c957-116">**TypeNameOfValue**属性：获取用于将此集定义为属性集的**PropertySet**枚举常数。</span><span class="sxs-lookup"><span data-stu-id="4c957-116">**TypeNameOfValue** property: Gets a **PropertySet** enumeration constant that defines this set as a property set.</span></span>
- <span data-ttu-id="4c957-117">**Value**属性：获取或设置**PSPropertySet**对象。</span><span class="sxs-lookup"><span data-stu-id="4c957-117">**Value** property: Gets or sets the **PSPropertySet** object.</span></span>
- <span data-ttu-id="4c957-118">`PSPropertySet.Copy`方法：创建**PSPropertySet**对象的精确副本。</span><span class="sxs-lookup"><span data-stu-id="4c957-118">`PSPropertySet.Copy` method: Makes an exact copy of the **PSPropertySet** object.</span></span>
- <span data-ttu-id="4c957-119">`PSMemberSet.ToString`方法：将**PSPropertySet**对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="4c957-119">`PSMemberSet.ToString` method: Converts the **PSPropertySet** object to a string.</span></span>

## <a name="member-sets"></a><span data-ttu-id="4c957-120">成员集</span><span class="sxs-lookup"><span data-stu-id="4c957-120">Member Sets</span></span>

<span data-ttu-id="4c957-121">成员集可以包含任意数量的任意类型的扩展成员。</span><span class="sxs-lookup"><span data-stu-id="4c957-121">Member sets can include any number of extended members of any type.</span></span> <span data-ttu-id="4c957-122">成员集是通过调用`PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`</span><span class="sxs-lookup"><span data-stu-id="4c957-122">The member set is created by calling the `PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`</span></span>
<span data-ttu-id="4c957-123">带有成员集名称和引用成员名称的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4c957-123">constructor with the name of the member set and the names of the referenced members.</span></span> <span data-ttu-id="4c957-124">然后，创建的**PSPropertySet**对象可用作指向集中成员的别名。</span><span class="sxs-lookup"><span data-stu-id="4c957-124">The created **PSPropertySet** object can then be used as an alias that points to the members in the set.</span></span> <span data-ttu-id="4c957-125">[PSMemberSet](/dotnet/api/system.management.automation.psmemberset)类具有以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="4c957-125">The [PSMemberSet](/dotnet/api/system.management.automation.psmemberset) class has the following properties and methods.</span></span>

- <span data-ttu-id="4c957-126">**IsInstance**属性：获取指示成员源的**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="4c957-126">**IsInstance** property: Gets a **Boolean** value that indicates the source of the member.</span></span>
- <span data-ttu-id="4c957-127">**Members**属性：获取成员集的所有成员。</span><span class="sxs-lookup"><span data-stu-id="4c957-127">**Members** property: Gets all the members of the member set.</span></span>
- <span data-ttu-id="4c957-128">**MemberType**属性：获取将此集定义为成员集**的成员集枚举常数**。</span><span class="sxs-lookup"><span data-stu-id="4c957-128">**MemberType** property: Gets a **MemberSet** enumeration constant that defines this set as a member set.</span></span>
- <span data-ttu-id="4c957-129">**方法**属性：获取成员集中包含的方法。</span><span class="sxs-lookup"><span data-stu-id="4c957-129">**Methods** property: Gets the methods included in the member set.</span></span>
- <span data-ttu-id="4c957-130">**Properties**属性：获取成员集中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="4c957-130">**Properties** property: Gets the properties included in the member set.</span></span>
- <span data-ttu-id="4c957-131">**TypeNameOfValue**属性：获取将此集定义为成员集**的成员集枚举常数**。</span><span class="sxs-lookup"><span data-stu-id="4c957-131">**TypeNameOfValue** property: Gets a **MemberSet** enumeration constant that defines this set as a member set.</span></span>
- <span data-ttu-id="4c957-132">**Value**属性：获取**PSMemberSet**对象。</span><span class="sxs-lookup"><span data-stu-id="4c957-132">**Value** property: Gets the **PSMemberSet** object.</span></span>
- <span data-ttu-id="4c957-133">`PSMemberSet.Copy`方法：创建**PSMemberSet**对象的精确副本。</span><span class="sxs-lookup"><span data-stu-id="4c957-133">`PSMemberSet.Copy` method: Makes an exact copy of the **PSMemberSet** object.</span></span>
- <span data-ttu-id="4c957-134">`PSMemberSet.ToString`方法：将**PSMemberSet**对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="4c957-134">`PSMemberSet.ToString` method: Converts the **PSMemberSet** object to a string.</span></span>
