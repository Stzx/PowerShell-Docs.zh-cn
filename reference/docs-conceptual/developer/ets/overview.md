---
title: 扩展类型系统概述
ms.date: 07/09/2020
ms.openlocfilehash: 5c190f0d9b852a4b5658227085092f33d71453c9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786214"
---
# <a name="extended-type-system-overview"></a><span data-ttu-id="31eff-102">扩展类型系统概述</span><span class="sxs-lookup"><span data-stu-id="31eff-102">Extended Type System Overview</span></span>

<span data-ttu-id="31eff-103">PowerShell 使用其**PSObject**对象通过两种方式来扩展对象的类型。</span><span class="sxs-lookup"><span data-stu-id="31eff-103">PowerShell uses its **PSObject** object to extend the types of objects in two ways.</span></span> <span data-ttu-id="31eff-104">首先， **PSObject**对象提供一种方法来显示特定对象类型的不同视图。</span><span class="sxs-lookup"><span data-stu-id="31eff-104">First, the **PSObject** object provides a way to show different views of specific object types.</span></span> <span data-ttu-id="31eff-105">这称为 "显示对象的改编视图"。</span><span class="sxs-lookup"><span data-stu-id="31eff-105">This is referred to as showing an adapted view of an object.</span></span> <span data-ttu-id="31eff-106">其次， **PSObject**对象提供将成员添加到现有对象的方法。</span><span class="sxs-lookup"><span data-stu-id="31eff-106">Second, the **PSObject** object provides a way to add members to existing object.</span></span> <span data-ttu-id="31eff-107">通过包装现有对象（称为基对象）， **PSObject**对象提供扩展类型系统 (ETS) ，脚本和 cmdlet 开发人员可以使用该系统在 shell 中操作 .net 对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-107">Together, by wrapping an existing object, referred to as the base object, the **PSObject** object provides an extended type system (ETS) that script and cmdlet developers can use to manipulate .NET objects within the shell.</span></span>

## <a name="cmdlet-and-script-development-issues"></a><span data-ttu-id="31eff-108">Cmdlet 和脚本开发问题</span><span class="sxs-lookup"><span data-stu-id="31eff-108">Cmdlet and Script Development Issues</span></span>

<span data-ttu-id="31eff-109">ETS 解决了两个基本问题：</span><span class="sxs-lookup"><span data-stu-id="31eff-109">ETS resolves two fundamental issues:</span></span>

<span data-ttu-id="31eff-110">首先，某些 .NET 对象没有在 cmdlet 之间充当数据所必需的默认行为。</span><span class="sxs-lookup"><span data-stu-id="31eff-110">First, some .NET Objects do not have the necessary default behavior for acting as the data between cmdlets.</span></span>

- <span data-ttu-id="31eff-111">某些 .NET 对象是 "meta" 对象 (例如： WMI 对象、ADO 对象和 XML 对象) 其成员描述它们所包含的数据。</span><span class="sxs-lookup"><span data-stu-id="31eff-111">Some .NET objects are "meta" objects (for example: WMI Objects, ADO objects, and XML objects) whose members describe the data they contain.</span></span> <span data-ttu-id="31eff-112">但是，在脚本环境中，它是最值得注意的包含数据，而不是包含数据的说明。</span><span class="sxs-lookup"><span data-stu-id="31eff-112">However, in a scripting environment it is the contained data that is most interesting, not the description of the contained data.</span></span> <span data-ttu-id="31eff-113">ETS 通过引入用于使基础 .NET 对象适应所需默认语义的适配器的概念来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="31eff-113">ETS resolves this issue by introducing the notion of Adapters that adapt the underlying .NET object to have the expected default semantics.</span></span>
- <span data-ttu-id="31eff-114">某些 .NET 对象成员的名称不一致，提供的公共成员集不足，或提供的功能不足。</span><span class="sxs-lookup"><span data-stu-id="31eff-114">Some .NET Object members are inconsistently named, provide an insufficient set of public members, or provide insufficient capability.</span></span> <span data-ttu-id="31eff-115">ETS 通过引入使用其他成员扩展 .NET 对象的功能来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="31eff-115">ETS resolves this issue by introducing the ability to extend the .NET object with additional members.</span></span>

<span data-ttu-id="31eff-116">其次，PowerShell 脚本_语言是无类型的，_ 因为无需声明特定类型的变量。</span><span class="sxs-lookup"><span data-stu-id="31eff-116">Second, the PowerShell scripting language is _typeless_ in that a variable does not need to be declared of a particular type.</span></span> <span data-ttu-id="31eff-117">也就是说，脚本开发人员创建的变量_是本质上_无类型。</span><span class="sxs-lookup"><span data-stu-id="31eff-117">That is, the variables a script developer creates are by nature _typeless_.</span></span> <span data-ttu-id="31eff-118">但是，PowerShell 系统是 "类型驱动的"，因为它依赖于对基本操作（如输出结果或排序）进行操作时所使用的类型名称。</span><span class="sxs-lookup"><span data-stu-id="31eff-118">However, the PowerShell system is "type-driven" in that it depends on having a type name to operate against for basic operations such as outputting results or sorting.</span></span>

<span data-ttu-id="31eff-119">因此，脚本开发人员必须能够声明其中一个变量的类型，并构建自己的一组动态类型化 "对象"，其中包含属性和方法，并可参与到类型驱动的系统中。</span><span class="sxs-lookup"><span data-stu-id="31eff-119">Therefore a script developer must have the ability to state the type of one of their variables and build up their own set of dynamically typed "objects" that contain properties and methods and can participate in the type-driven system.</span></span> <span data-ttu-id="31eff-120">ETS 解决了此问题的方法是，提供一种脚本语言的通用对象，使其能够动态地声明其类型并动态添加成员。</span><span class="sxs-lookup"><span data-stu-id="31eff-120">ETS solves this problem by providing a common object for the scripting language that has the ability to state its type dynamically and to add members dynamically.</span></span>

<span data-ttu-id="31eff-121">从根本上讲，ETS 通过提供**PSObject**对象来解决前面提到的问题，该对象用作脚本语言的所有对象访问的基础，并为 cmdlet 开发人员提供标准抽象。</span><span class="sxs-lookup"><span data-stu-id="31eff-121">Fundamentally, ETS resolves the issue mentioned previously by providing the **PSObject** object, which acts as the basis of all object access from the scripting language and provides a standard abstraction for the cmdlet developer.</span></span>

### <a name="cmdlet-developers"></a><span data-ttu-id="31eff-122">Cmdlet 开发人员</span><span class="sxs-lookup"><span data-stu-id="31eff-122">Cmdlet Developers</span></span>

<span data-ttu-id="31eff-123">对于 cmdlet 开发人员，ETS 提供了以下支持：</span><span class="sxs-lookup"><span data-stu-id="31eff-123">For the cmdlet developers, ETS provides the following support:</span></span>

- <span data-ttu-id="31eff-124">使用**PSObject**对象，以一般方式使用对象的抽象。</span><span class="sxs-lookup"><span data-stu-id="31eff-124">The abstractions to work against objects in a generic way using the **PSObject** object.</span></span> <span data-ttu-id="31eff-125">ETS 还提供了在需要时钻取这些抽象的功能。</span><span class="sxs-lookup"><span data-stu-id="31eff-125">ETS also provides the ability to drill past these abstractions if required.</span></span>
- <span data-ttu-id="31eff-126">使用一组已知的扩展成员为其对象类型创建格式设置、排序、序列化和其他系统操作的机制。</span><span class="sxs-lookup"><span data-stu-id="31eff-126">The mechanisms to create a default behavior for formatting, sorting, serialization, and other system manipulations of their object type using a well-known set of extended members.</span></span>
- <span data-ttu-id="31eff-127">对任何使用与使用 Languageprimitives.physicalequality 对象的脚本语言相同的语义的对象操作的方法。</span><span class="sxs-lookup"><span data-stu-id="31eff-127">The means to operate against any object using the same semantics as the script language using a LanguagePrimitives object.</span></span>
- <span data-ttu-id="31eff-128">这种方法动态 "键入" 哈希表，以便系统的其余部分能够有效地执行操作。</span><span class="sxs-lookup"><span data-stu-id="31eff-128">The means to dynamically "type" a hash table so that the rest of the system can operate against it effectively.</span></span>

### <a name="script-developers"></a><span data-ttu-id="31eff-129">编写开发人员脚本</span><span class="sxs-lookup"><span data-stu-id="31eff-129">Script Developers</span></span>

<span data-ttu-id="31eff-130">对于脚本开发人员而言，ETS 提供了以下支持：</span><span class="sxs-lookup"><span data-stu-id="31eff-130">For the script developers, ETS provides the following support:</span></span>

- <span data-ttu-id="31eff-131">能够使用相同的语法 () 引用任何基础对象类型 `$a.x` 。</span><span class="sxs-lookup"><span data-stu-id="31eff-131">The ability to reference any underlying object type using the same syntax (`$a.x`).</span></span>
- <span data-ttu-id="31eff-132">访问**PSObject**对象提供的抽象之外的功能 (例如仅访问改编的成员或访问基对象本身) 。</span><span class="sxs-lookup"><span data-stu-id="31eff-132">The ability to access beyond the abstraction provided by the **PSObject** object (such as accessing only adapted members, or accessing the base object itself).</span></span>
- <span data-ttu-id="31eff-133">定义用于控制对象实例或类型的格式设置、排序、序列化和其他操作的已知成员的功能。</span><span class="sxs-lookup"><span data-stu-id="31eff-133">The ability to define well-known members that control the formatting, sorting, serialization, and other manipulations of an object instance or type.</span></span>
- <span data-ttu-id="31eff-134">指将对象命名为特定类型，从而控制其基于类型的成员的继承。</span><span class="sxs-lookup"><span data-stu-id="31eff-134">The means to name an object as a specific type and thus control the inheritance of its type-based members.</span></span>
- <span data-ttu-id="31eff-135">添加、删除和修改扩展成员的功能。</span><span class="sxs-lookup"><span data-stu-id="31eff-135">The ability to add, remove, and modify extended members.</span></span>
- <span data-ttu-id="31eff-136">如果需要，可以操作**PSObject**对象本身。</span><span class="sxs-lookup"><span data-stu-id="31eff-136">The ability to manipulate the **PSObject** object itself if required.</span></span>

## <a name="the-psobject-class"></a><span data-ttu-id="31eff-137">PSObject 类</span><span class="sxs-lookup"><span data-stu-id="31eff-137">The PSObject class</span></span>

<span data-ttu-id="31eff-138">**PSObject**对象是从脚本语言进行的所有对象访问的基础，并为 cmdlet 开发人员提供了标准抽象。</span><span class="sxs-lookup"><span data-stu-id="31eff-138">The **PSObject** object is the basis of all object access from the scripting language and provides a standard abstraction for the cmdlet developer.</span></span> <span data-ttu-id="31eff-139">它包含一个 (.NET 对象的基对象) ，以及在特定对象实例上存在的任何实例成员 (成员（尤其是扩展成员），而不一定在) 相同类型的其他对象上。</span><span class="sxs-lookup"><span data-stu-id="31eff-139">It contains a base-object (a .NET object) and any instance members (members, specifically extended members, that are present on a particular object instance while not necessarily on other objects of the same type).</span></span> <span data-ttu-id="31eff-140">根据基对象的类型， **PSObject**对象还可以提供对改编成员以及任何基于类型的扩展成员的隐式和显式访问。</span><span class="sxs-lookup"><span data-stu-id="31eff-140">Depending on the type of the base-object, the **PSObject** object might also provide implicit and explicit access to adapted members as well as any type-based extended members.</span></span>

<span data-ttu-id="31eff-141">**PSObject**对象提供以下机制：</span><span class="sxs-lookup"><span data-stu-id="31eff-141">The **PSObject** object provides the following mechanisms:</span></span>

- <span data-ttu-id="31eff-142">使用或不使用基对象构造**PSObject**的能力。</span><span class="sxs-lookup"><span data-stu-id="31eff-142">The ability to construct an **PSObject** with or without a base-object.</span></span>
- <span data-ttu-id="31eff-143">能够通过常见的查找算法访问每个构造的**PSObject**对象的所有成员，并在需要时重写该算法。</span><span class="sxs-lookup"><span data-stu-id="31eff-143">The ability to access of all members of each constructed **PSObject** object through a common lookup algorithm and the ability to override that algorithm when required.</span></span>
- <span data-ttu-id="31eff-144">获取和设置构造的**PSObject**对象的类型名称的功能，使脚本和 cmdlet 可以通过相同的类型名称引用类似的**PSObject**对象，而不考虑其基对象的类型。</span><span class="sxs-lookup"><span data-stu-id="31eff-144">The ability to get and set the type-names of the constructed **PSObject** objects so that scripts and cmdlets can reference similar **PSObject** objects by the same type-name, regardless of the type of their base-object.</span></span>

### <a name="how-to-construct-a-psobject"></a><span data-ttu-id="31eff-145">如何构造 PSObject</span><span class="sxs-lookup"><span data-stu-id="31eff-145">How to Construct a PSObject</span></span>

<span data-ttu-id="31eff-146">以下列表描述了创建**PSObject**对象的方法：</span><span class="sxs-lookup"><span data-stu-id="31eff-146">The following list describes ways to create a **PSObject** object:</span></span>

- <span data-ttu-id="31eff-147">调用**PSObject** . #ctor 构造函数将创建一个新的**PSObject**对象，该对象具有 PSCustomObject 的基对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-147">Calling the **PSObject** .#ctor constructor creates a new **PSObject** object with a base-object of PSCustomObject.</span></span> <span data-ttu-id="31eff-148">此类型的基对象指示**PSObject**对象没有有意义的基对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-148">A base-object of this type indicates that the **PSObject** object has no meaningful base-object.</span></span> <span data-ttu-id="31eff-149">但是，具有这种类型的基对象的**PSObject**对象的确提供了一个属性包，该属性包由 cmdlet 开发人员通过添加扩展成员来找到帮助。</span><span class="sxs-lookup"><span data-stu-id="31eff-149">However, a **PSObject** object with this type of base-object does provide a property bag that cmdlet developers can find helpful by adding extended-members.</span></span>

<span data-ttu-id="31eff-150">开发人员还可以指定对象类型名称，该名称允许此对象与具有相同类型名称的其他**PSObject**对象共享其扩展成员。</span><span class="sxs-lookup"><span data-stu-id="31eff-150">Developers can also specify the object type-name, which allows this object to share its extended-members with other **PSObject** objects of the same type-name.</span></span>

- <span data-ttu-id="31eff-151"> (System.object #ctor 调用**psobject**) 构造函数将创建一个新的**PSObject**对象，其中包含类型为 system.object 的基对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-151">Calling the **PSObject** .#ctor(System.Object) constructor creates a new **PSObject** object with a base-object of type System.Object.</span></span>

  <span data-ttu-id="31eff-152">在这种情况下，所创建的对象的类型名称是基对象的派生层次结构的集合。</span><span class="sxs-lookup"><span data-stu-id="31eff-152">In this case, the type-name for the created object is a collection of the derivation hierarchy of the base-object.</span></span> <span data-ttu-id="31eff-153">例如，包含 ProcessInfo 基对象的**PSObject**的类型名称将包含以下名称：</span><span class="sxs-lookup"><span data-stu-id="31eff-153">For example, the type-name for the **PSObject** that contains a ProcessInfo base-object would include the following names:</span></span>

  - <span data-ttu-id="31eff-154">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="31eff-154">System.Diagnostics.Process</span></span>
  - <span data-ttu-id="31eff-155">System.componentmodel</span><span class="sxs-lookup"><span data-stu-id="31eff-155">System.ComponentModel.Component</span></span>
  - <span data-ttu-id="31eff-156">System.MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="31eff-156">System.MarshalByRefObject</span></span>
  - <span data-ttu-id="31eff-157">System.Object</span><span class="sxs-lookup"><span data-stu-id="31eff-157">System.Object</span></span>

- <span data-ttu-id="31eff-158">调用**PSObject** 。AsPSObject (System.object) 方法基于提供的对象创建新的**PSObject**对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-158">Calling the **PSObject** .AsPSObject(System.Object) method creates a new **PSObject** object based on a supplied object.</span></span>

  <span data-ttu-id="31eff-159">如果提供的对象的类型为 System.object，则提供的对象将用作新**PSObject**对象的基对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-159">If the supplied object is of type System.Object, the supplied object is used as the base-object for the new **PSObject** object.</span></span> <span data-ttu-id="31eff-160">如果提供的对象已是**PSObject**对象，则提供的对象将按原样返回。</span><span class="sxs-lookup"><span data-stu-id="31eff-160">If the supplied object is already an **PSObject** object, the supplied object is returned as is.</span></span>

### <a name="base-adapted-and-extended-members"></a><span data-ttu-id="31eff-161">基本、改编和扩展成员</span><span class="sxs-lookup"><span data-stu-id="31eff-161">Base, adapted, and extended members</span></span>

<span data-ttu-id="31eff-162">从概念上讲，ETS 使用以下术语来显示基本对象的原始成员与 PowerShell 添加的成员之间的关系。</span><span class="sxs-lookup"><span data-stu-id="31eff-162">Conceptually, ETS uses the following terms to show the relationship between the original members of the base-object and those members added by PowerShell.</span></span> <span data-ttu-id="31eff-163">有关**psobject**对象使用的特定成员类型的详细信息，请参阅[psobject class](/dotnet/api/system.management.automation.psobject)。</span><span class="sxs-lookup"><span data-stu-id="31eff-163">For more information about the specific types of members that are used by the **PSObject** object, see [PSObject class](/dotnet/api/system.management.automation.psobject).</span></span>

#### <a name="base-object-members"></a><span data-ttu-id="31eff-164">基对象成员</span><span class="sxs-lookup"><span data-stu-id="31eff-164">Base-object members</span></span>

<span data-ttu-id="31eff-165">如果在构造**PSObject**对象时指定了基对象，则可以通过 members 属性使用基对象的成员。</span><span class="sxs-lookup"><span data-stu-id="31eff-165">If the base-object is specified when constructing the **PSObject** objects, then the members of the base-object are made available through the Members property.</span></span>

#### <a name="adapted-members"></a><span data-ttu-id="31eff-166">改编成员</span><span class="sxs-lookup"><span data-stu-id="31eff-166">Adapted members</span></span>

<span data-ttu-id="31eff-167">当基对象是一个元对象时，其中一个对象的属性 "描述" 其包含数据的一般方式中包含数据，ETS 将这些对象调整为一个视图，该视图允许通过已改编的**PSObject**对象成员直接访问数据。</span><span class="sxs-lookup"><span data-stu-id="31eff-167">When a base-object is a meta-object, one that contains data in a generic fashion whose properties "describe" their contained data, ETS adapts those objects to a view that allows for direct access to the data through adapted members of the **PSObject** object.</span></span> <span data-ttu-id="31eff-168">可通过 Members 属性访问改编成员和基对象成员。</span><span class="sxs-lookup"><span data-stu-id="31eff-168">Adapted members and base-object members are accessed through the Members property.</span></span>

#### <a name="extended-members"></a><span data-ttu-id="31eff-169">扩展成员</span><span class="sxs-lookup"><span data-stu-id="31eff-169">Extended members</span></span>

<span data-ttu-id="31eff-170">除了通过基对象或 PowerShell 创建的那些改编成员提供的成员以外， **PSObject**还可以定义扩展成员，这些扩展成员用脚本环境中有用的附加信息来扩展原始的基本对象。</span><span class="sxs-lookup"><span data-stu-id="31eff-170">In addition to the members made available from the base-object or those adapted members created by PowerShell, an **PSObject** may also define extended members that extend the original base-object with additional information that is useful in the scripting environment.</span></span>

<span data-ttu-id="31eff-171">例如，PowerShell 提供的所有核心 cmdlet，例如获取内容和集内容 cmdlet，都采用 path 参数。</span><span class="sxs-lookup"><span data-stu-id="31eff-171">For example, all the core cmdlets provided by PowerShell, such as the Get-Content and Set-Content cmdlets, take a path parameter.</span></span> <span data-ttu-id="31eff-172">若要确保这些 cmdlet 以及其他 cmdlet 可对不同类型的对象进行操作，可以将路径成员添加到这些对象，以便它们都以常见方式为其信息。</span><span class="sxs-lookup"><span data-stu-id="31eff-172">To ensure that these cmdlets, and others, can work against objects of different types, a Path member can be added to those objects so that they all state their information in a common way.</span></span> <span data-ttu-id="31eff-173">此扩展路径成员可确保 cmdlet 可对所有这些类型进行操作，即使基类可能不具有路径成员也是如此。</span><span class="sxs-lookup"><span data-stu-id="31eff-173">This extended Path member ensures that the cmdlets can work against all those types even though there base class might not have a Path member.</span></span>

<span data-ttu-id="31eff-174">扩展成员、改编成员和基本对象成员均通过 Members 属性进行访问。</span><span class="sxs-lookup"><span data-stu-id="31eff-174">Extended members, adapted members, and base-object members are all accessed through the Members property.</span></span>
