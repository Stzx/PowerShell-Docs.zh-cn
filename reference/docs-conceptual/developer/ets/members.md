---
ms.date: 07/09/2020
ms.topic: reference
title: 扩展类型系统类成员
description: 扩展类型系统类成员
ms.openlocfilehash: 06488ce423f363a285ab53b21ab45989654346dc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666835"
---
# <a name="extended-type-system-class-members"></a><span data-ttu-id="f39b9-103">扩展类型系统类成员</span><span class="sxs-lookup"><span data-stu-id="f39b9-103">Extended Type System class members</span></span>

<span data-ttu-id="f39b9-104">ETS 是指若干不同类型的成员，这些成员的类型由 **PSMemberTypes** 枚举定义。</span><span class="sxs-lookup"><span data-stu-id="f39b9-104">ETS refers to a number of different kinds of members whose types are defined by the **PSMemberTypes** enumeration.</span></span> <span data-ttu-id="f39b9-105">这些成员类型包括属性、方法、成员和成员集，它们分别由其自己的 CLR 类型定义。</span><span class="sxs-lookup"><span data-stu-id="f39b9-105">These member types include properties, methods, members, and member sets that are each defined by their own CLR type.</span></span> <span data-ttu-id="f39b9-106">例如， **NoteProperty** 由其自己的 **PSNoteProperty** 类型定义。</span><span class="sxs-lookup"><span data-stu-id="f39b9-106">For example, a **NoteProperty** is defined by its own **PSNoteProperty** type.</span></span> <span data-ttu-id="f39b9-107">这些单独的 CLR 类型具有其自己的唯一属性和从 [PSMemberInfo 类](/dotnet/api/system.management.automation.psmemberinfo)继承的公共属性。</span><span class="sxs-lookup"><span data-stu-id="f39b9-107">These individual CLR types have both their own unique properties and common properties that are inherited from the [PSMemberInfo class](/dotnet/api/system.management.automation.psmemberinfo).</span></span>

## <a name="the-psmemberinfo-class"></a><span data-ttu-id="f39b9-108">PSMemberInfo 类</span><span class="sxs-lookup"><span data-stu-id="f39b9-108">The PSMemberInfo class</span></span>

<span data-ttu-id="f39b9-109">**PSMemberInfo** 类充当所有 ETS 成员类型的基类。</span><span class="sxs-lookup"><span data-stu-id="f39b9-109">The **PSMemberInfo** class serves as a base class for all ETS member types.</span></span> <span data-ttu-id="f39b9-110">此类为所有成员 CLR 类型提供以下基本属性。</span><span class="sxs-lookup"><span data-stu-id="f39b9-110">This class provides the following base properties to all member CLR types.</span></span>

- <span data-ttu-id="f39b9-111">**Name** 属性：成员的名称。</span><span class="sxs-lookup"><span data-stu-id="f39b9-111">**Name** property: The name of the member.</span></span> <span data-ttu-id="f39b9-112">此名称可由基本对象定义，或者在公开改编成员或扩展成员时由 PowerShell 定义。</span><span class="sxs-lookup"><span data-stu-id="f39b9-112">This name can be defined by the base-object or defined by PowerShell when adapted members or extended members are exposed.</span></span>
- <span data-ttu-id="f39b9-113">**值** 属性：从特定成员返回的值。</span><span class="sxs-lookup"><span data-stu-id="f39b9-113">**Value** property: The value returned from the particular member.</span></span> <span data-ttu-id="f39b9-114">每个成员类型定义它如何处理其成员值。</span><span class="sxs-lookup"><span data-stu-id="f39b9-114">Each member type defines how it handles its member value.</span></span>
- <span data-ttu-id="f39b9-115">**TypeNameOfValue** 属性：这是值属性返回的值的 CLR 类型的名称。</span><span class="sxs-lookup"><span data-stu-id="f39b9-115">**TypeNameOfValue** property: This is the name of the CLR type of the value that is returned by the Value property.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="f39b9-116">访问成员</span><span class="sxs-lookup"><span data-stu-id="f39b9-116">Accessing members</span></span>

<span data-ttu-id="f39b9-117">可以通过 **PSObject** 对象的 **成员**、**方法** 和 **属性** 属性访问成员的集合。</span><span class="sxs-lookup"><span data-stu-id="f39b9-117">Collections of members can be accessed through the **Members**, **Methods**, and **Properties** properties of the **PSObject** object.</span></span>

## <a name="ets-properties"></a><span data-ttu-id="f39b9-118">ETS 属性</span><span class="sxs-lookup"><span data-stu-id="f39b9-118">ETS properties</span></span>

<span data-ttu-id="f39b9-119">ETS 属性是可作为属性来处理的成员。</span><span class="sxs-lookup"><span data-stu-id="f39b9-119">ETS properties are members that can be treated as a property.</span></span> <span data-ttu-id="f39b9-120">实质上，它们可以出现在表达式的左侧。</span><span class="sxs-lookup"><span data-stu-id="f39b9-120">Essentially, they can appear on the left-hand side of an expression.</span></span> <span data-ttu-id="f39b9-121">它们包括别名属性、代码属性、PowerShell 属性、便笺属性和脚本属性。</span><span class="sxs-lookup"><span data-stu-id="f39b9-121">They include alias properties, code properties, PowerShell properties, note properties, and script properties.</span></span> <span data-ttu-id="f39b9-122">有关这些类型的属性的详细信息，请参阅 [ETS properties](properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f39b9-122">For more information about these types of properties, see [ETS properties](properties.md).</span></span>

## <a name="ets-methods"></a><span data-ttu-id="f39b9-123">ETS 方法</span><span class="sxs-lookup"><span data-stu-id="f39b9-123">ETS methods</span></span>

<span data-ttu-id="f39b9-124">ETS 方法是可以采用参数的成员，可能返回结果，并且不能出现在表达式的左侧。</span><span class="sxs-lookup"><span data-stu-id="f39b9-124">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="f39b9-125">它们包括代码方法、PowerShell 方法和脚本方法。</span><span class="sxs-lookup"><span data-stu-id="f39b9-125">They include code methods, PowerShell methods, and script methods.</span></span>
<span data-ttu-id="f39b9-126">有关这些类型的方法的详细信息，请参阅 [ETS 方法](methods.md)。</span><span class="sxs-lookup"><span data-stu-id="f39b9-126">For more information about these types of methods, see [ETS methods](methods.md).</span></span>
