---
title: 扩展类型系统类方法
ms.date: 07/09/2020
ms.openlocfilehash: bd03b873893f8aa9cb92eda33538c1703ead9773
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786231"
---
# <a name="ets-class-methods"></a><span data-ttu-id="d74ab-102">ETS 类方法</span><span class="sxs-lookup"><span data-stu-id="d74ab-102">ETS class methods</span></span>

<span data-ttu-id="d74ab-103">ETS 方法是可以采用参数的成员，可能返回结果，并且不能出现在表达式的左侧。</span><span class="sxs-lookup"><span data-stu-id="d74ab-103">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="d74ab-104">ETS 中的可用方法包括代码、Windows PowerShell 和脚本方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-104">The methods that are available within ETS include code, Windows PowerShell, and script methods.</span></span>

> [!NOTE]
> <span data-ttu-id="d74ab-105">在脚本中，使用与其他成员相同的语法访问方法，并在方法名称末尾添加括号。</span><span class="sxs-lookup"><span data-stu-id="d74ab-105">From scripts, methods are accessed using the same syntax as other members with the addition of parenthesis at the end of the method name.</span></span>

## <a name="code-methods"></a><span data-ttu-id="d74ab-106">代码方法</span><span class="sxs-lookup"><span data-stu-id="d74ab-106">Code Methods</span></span>

<span data-ttu-id="d74ab-107">代码方法是在 CLR 语言中定义的扩展成员。</span><span class="sxs-lookup"><span data-stu-id="d74ab-107">A code method is an extended member that is defined in a CLR language.</span></span> <span data-ttu-id="d74ab-108">它为基本对象上定义的方法提供了类似的功能;但是，可以将代码方法动态添加到**PSObject**对象。</span><span class="sxs-lookup"><span data-stu-id="d74ab-108">It provides similar functionality to a method defined on a base object; however, a code method may be added dynamically to an **PSObject** object.</span></span> <span data-ttu-id="d74ab-109">为了使代码方法变得可用，开发人员必须以某种 CLR 语言编写该属性，然后编译并交付生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="d74ab-109">In order for a code method to become available, a developer must write the property in some CLR language, compile, and ship the resultant assembly.</span></span> <span data-ttu-id="d74ab-110">此程序集必须在需要代码方法的运行空间中可用。</span><span class="sxs-lookup"><span data-stu-id="d74ab-110">This assembly must be available in the runspace where the code method is desired.</span></span> <span data-ttu-id="d74ab-111">请注意，代码方法的实现必须是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="d74ab-111">Be aware that a code method implementation must be thread safe.</span></span> <span data-ttu-id="d74ab-112">可以通过提供以下公共方法和属性的[PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)对象来访问这些方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-112">Access to these methods is done through [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) objects that provides the following public methods and properties.</span></span>

- <span data-ttu-id="d74ab-113">`PSCodeMethod.Copy`方法：创建**PSCodeMethod**对象的精确副本。</span><span class="sxs-lookup"><span data-stu-id="d74ab-113">`PSCodeMethod.Copy` method: Makes an exact copy of the **PSCodeMethod** object.</span></span>
- <span data-ttu-id="d74ab-114">`PSCodeMethod.Invoke(System.Object[])`方法：调用基础代码方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-114">`PSCodeMethod.Invoke(System.Object[])` method: Invokes the underlying code method.</span></span>
- <span data-ttu-id="d74ab-115">`PSCodeMethod.ToString`方法：将**PSCodeMethod**对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="d74ab-115">`PSCodeMethod.ToString` method: Converts the **PSCodeMethod** object to a string.</span></span>
- <span data-ttu-id="d74ab-116">`PSCodeMethod.CodeReference`属性：获取代码方法所基于的基础方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-116">`PSCodeMethod.CodeReference` property: Gets the underlying method that the code method is based on.</span></span>
- <span data-ttu-id="d74ab-117">**PSMemberInfo. IsInstance**属性：获取指示成员源的**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="d74ab-117">**PSMemberInfo.IsInstance** property: Gets a **Boolean** value that indicates the source of the member.</span></span>
- <span data-ttu-id="d74ab-118">**PSCodeMethod. MemberType**属性：获取将此方法标识为代码方法的**PSMemberTypes。**</span><span class="sxs-lookup"><span data-stu-id="d74ab-118">**PSCodeMethod.MemberType** property: Gets an **PSMemberTypes.CodeMethod** enumeration constant that identifies this method as a code method.</span></span>
- <span data-ttu-id="d74ab-119">**PSMemberInfo.Name**属性：获取基础代码方法的名称。</span><span class="sxs-lookup"><span data-stu-id="d74ab-119">**PSMemberInfo.Name** property: Gets the name of the underlying code method.</span></span>
- <span data-ttu-id="d74ab-120">**PSCodeMethod. OverloadDefinitions**属性：获取基础代码方法的所有重载的定义。</span><span class="sxs-lookup"><span data-stu-id="d74ab-120">**PSCodeMethod.OverloadDefinitions** property: Gets a definition of all the overloads of the underlying code method.</span></span>
- <span data-ttu-id="d74ab-121">**PSCodeMethod. TypeNameOfValue**属性：获取代码方法的完整名称。</span><span class="sxs-lookup"><span data-stu-id="d74ab-121">**PSCodeMethod.TypeNameOfValue** property: Gets the full name of the code method.</span></span>
- <span data-ttu-id="d74ab-122">**PSMemberInfo**属性：获取**PSCodeMethod**对象。</span><span class="sxs-lookup"><span data-stu-id="d74ab-122">**PSMemberInfo.Value** property: Gets the **PSCodeMethod** object.</span></span>

## <a name="windows-powershell-methods"></a><span data-ttu-id="d74ab-123">Windows PowerShell 方法</span><span class="sxs-lookup"><span data-stu-id="d74ab-123">Windows PowerShell Methods</span></span>

<span data-ttu-id="d74ab-124">PowerShell 方法是在基对象上定义的或可通过适配器访问的 CLR 方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-124">A PowerShell method is a CLR method defined on the base object or is made accessible through an adapter.</span></span> <span data-ttu-id="d74ab-125">可以通过提供以下公共方法和属性的**PSMethod**对象来访问这些方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-125">Access to these methods is done through **PSMethod** objects that provides the following public methods and properties.</span></span>

- <span data-ttu-id="d74ab-126">`PSMethod.Copy`方法：创建**PSMethod**对象的精确副本。</span><span class="sxs-lookup"><span data-stu-id="d74ab-126">`PSMethod.Copy` method: Makes an exact copy of the **PSMethod** object.</span></span>
- <span data-ttu-id="d74ab-127">`PSMethod.Invoke(System.Object[])`方法：调用基础方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-127">`PSMethod.Invoke(System.Object[])` method: Invokes the underlying method.</span></span>
- <span data-ttu-id="d74ab-128">`PSMethod.ToString`方法：将**PSMethod**对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="d74ab-128">`PSMethod.ToString` method: Converts the **PSMethod** object to a string.</span></span>
- <span data-ttu-id="d74ab-129">**PSMemberInfo. IsInstance**属性：获取指示成员源的**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="d74ab-129">**PSMemberInfo.IsInstance** property: Gets a **Boolean** value that indicates the source of the member.</span></span>
- <span data-ttu-id="d74ab-130">**PSMethod. MemberType**属性：获取将此方法标识为 PowerShell 方法的**PSMemberTypes**枚举常数。</span><span class="sxs-lookup"><span data-stu-id="d74ab-130">**PSMethod.MemberType** property: Gets an **PSMemberTypes.Method** enumeration constant that identifies this method as a PowerShell method.</span></span>
- <span data-ttu-id="d74ab-131">**PSMemberInfo.Name**属性：获取基础方法的名称。</span><span class="sxs-lookup"><span data-stu-id="d74ab-131">**PSMemberInfo.Name** property: Gets the name of the underlying method.</span></span>
- <span data-ttu-id="d74ab-132">**PSMethod. OverloadDefinitions**属性：获取基础方法的所有重载的定义。</span><span class="sxs-lookup"><span data-stu-id="d74ab-132">**PSMethod.OverloadDefinitions** property: Gets the definitions of all the overloads of the underlying method.</span></span>
- <span data-ttu-id="d74ab-133">**PSMethod. TypeNameOfValue**属性：获取此方法的 ETS 类型。</span><span class="sxs-lookup"><span data-stu-id="d74ab-133">**PSMethod.TypeNameOfValue** property: Gets the ETS type of this method.</span></span>
- <span data-ttu-id="d74ab-134">**PSMemberInfo**属性：获取**PSMethod**对象。</span><span class="sxs-lookup"><span data-stu-id="d74ab-134">**PSMemberInfo.Value** property: Gets the **PSMethod** object.</span></span>

## <a name="script-methods"></a><span data-ttu-id="d74ab-135">脚本方法</span><span class="sxs-lookup"><span data-stu-id="d74ab-135">Script Methods</span></span>

<span data-ttu-id="d74ab-136">脚本方法是在 PowerShell 语言中定义的扩展成员。</span><span class="sxs-lookup"><span data-stu-id="d74ab-136">A script method is an extended member that is defined in the PowerShell language.</span></span> <span data-ttu-id="d74ab-137">它为基本对象上定义的方法提供了类似的功能;但是，可以将脚本方法动态添加到**PSObject**对象。</span><span class="sxs-lookup"><span data-stu-id="d74ab-137">It provides similar functionality to a method defined on a base object; however, a script method may be added dynamically to an **PSObject** object.</span></span> <span data-ttu-id="d74ab-138">可以通过提供以下公共方法和属性的[PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod)对象来访问这些方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-138">Access to these methods is done through [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) objects that provides the following public methods and properties.</span></span>

- <span data-ttu-id="d74ab-139">`PSScriptMethod.Copy`方法：创建**PSScriptMethod**对象的精确副本。</span><span class="sxs-lookup"><span data-stu-id="d74ab-139">`PSScriptMethod.Copy` method: Makes an exact copy of the **PSScriptMethod** object.</span></span>
- <span data-ttu-id="d74ab-140">`PSScriptMethod.Invoke(System.Object[])`方法：调用基础脚本方法。</span><span class="sxs-lookup"><span data-stu-id="d74ab-140">`PSScriptMethod.Invoke(System.Object[])` method: Invokes the underlying script method.</span></span>
- <span data-ttu-id="d74ab-141">`PSScriptMethod.ToString`方法：将**PSScriptMethod**对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="d74ab-141">`PSScriptMethod.ToString` method: Converts the **PSScriptMethod** object to a string.</span></span>
- <span data-ttu-id="d74ab-142">**PSMemberInfo. IsInstance**属性：获取指示成员源的**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="d74ab-142">**PSMemberInfo.IsInstance** property: Gets a **Boolean** value that indicates the source of the member.</span></span>
- <span data-ttu-id="d74ab-143">**PSScriptMethod. MemberType**属性：获取用于将此方法标识为脚本方法的**PSMemberTypes。**</span><span class="sxs-lookup"><span data-stu-id="d74ab-143">**PSScriptMethod.MemberType** property: Gets a **PSMemberTypes.ScriptMethod** enumeration constant that identifies this method as a script method.</span></span>
- <span data-ttu-id="d74ab-144">**PSMemberInfo.Name**属性：获取基础代码方法的名称。</span><span class="sxs-lookup"><span data-stu-id="d74ab-144">**PSMemberInfo.Name** property: Gets the name of the underlying code method.</span></span>
- <span data-ttu-id="d74ab-145">**PSScriptMethod. OverloadDefinitions**属性：获取基础脚本方法的所有重载的定义。</span><span class="sxs-lookup"><span data-stu-id="d74ab-145">**PSScriptMethod.OverloadDefinitions** property: Gets the definitions of all the overloads of the underlying script method.</span></span>
- <span data-ttu-id="d74ab-146">**PSScriptMethod. TypeNameOfValue**属性：获取此方法的 ETS 类型。</span><span class="sxs-lookup"><span data-stu-id="d74ab-146">**PSScriptMethod.TypeNameOfValue** property: Gets the ETS type of this method.</span></span>
- <span data-ttu-id="d74ab-147">**PSScriptMethod**属性：获取用于调用方法的脚本。</span><span class="sxs-lookup"><span data-stu-id="d74ab-147">**PSScriptMethod.Script** property: Gets the script used to invoke the method.</span></span>
- <span data-ttu-id="d74ab-148">**PSMemberInfo**属性：获取**PSScriptMethod**对象。</span><span class="sxs-lookup"><span data-stu-id="d74ab-148">**PSMemberInfo.Value** property: Gets the **PSScriptMethod** object.</span></span>
