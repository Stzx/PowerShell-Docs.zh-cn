---
title: 扩展类型系统中的错误和异常
ms.date: 07/09/2020
ms.openlocfilehash: f60c53e33c031168eda53726e0d296bf91139fda
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786282"
---
# <a name="errors-and-exceptions-in-the-extended-type-system"></a><span data-ttu-id="9c335-102">扩展类型系统中的错误和异常</span><span class="sxs-lookup"><span data-stu-id="9c335-102">Errors and exceptions in the Extended Type System</span></span>

<span data-ttu-id="9c335-103">在 ETS 类型数据和访问**PSObject**对象的成员或使用**languageprimitives.physicalequality**等实用工具类之一时，可能会出现错误。</span><span class="sxs-lookup"><span data-stu-id="9c335-103">Errors can occur in ETS during the initialization of type data and when accessing a member of an **PSObject** object or using one of the utility classes such as **LanguagePrimitives**.</span></span>

## <a name="runtime-errors"></a><span data-ttu-id="9c335-104">运行时错误</span><span class="sxs-lookup"><span data-stu-id="9c335-104">Runtime errors</span></span>

<span data-ttu-id="9c335-105">有一个例外，在强制转换时，在运行时从 ETS 引发的所有异常都是**ExtendedTypeSystemException**异常或从**ExtendedTypeSystemException**类派生的异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-105">With one exception, when casting, all exceptions thrown from ETS during runtime are either an **ExtendedTypeSystemException** exception or an exception derived from the **ExtendedTypeSystemException** class.</span></span> <span data-ttu-id="9c335-106">这样脚本开发人员就可以使用脚本中的语句来捕获这些异常 `Trap` 。</span><span class="sxs-lookup"><span data-stu-id="9c335-106">This allows script developers to trap these exceptions using the `Trap` statement in their script.</span></span>

## <a name="errors-getting-member-values"></a><span data-ttu-id="9c335-107">获取成员值时出错</span><span class="sxs-lookup"><span data-stu-id="9c335-107">Errors getting member values</span></span>

<span data-ttu-id="9c335-108">获取 ETS 成员的值 (属性、方法或参数化属性) 导致引发**GetValueException**或**GetValueInvocationException**异常时所发生的所有错误。</span><span class="sxs-lookup"><span data-stu-id="9c335-108">All errors that occur when getting the value of an ETS member (property, method, or parameterized property) cause a **GetValueException** or **GetValueInvocationException** exception to be thrown.</span></span>
<span data-ttu-id="9c335-109">当 ETS 识别到发生错误时，将引发**GetValueException**异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-109">When ETS recognizes that an error occurred a **GetValueException** exception is thrown.</span></span> <span data-ttu-id="9c335-110">当被引用成员的基础 getter 识别到错误时，将引发**GetValueInvocationException**异常，该异常可能包含或可能不包含导致 get 调用错误的内部异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-110">When the underlying getter of a referenced member recognizes that an error occurred, a **GetValueInvocationException** exception is thrown that may or may not include the inner exception that caused the get invocation error.</span></span>

## <a name="errors-setting-member-values"></a><span data-ttu-id="9c335-111">设置成员值时出错</span><span class="sxs-lookup"><span data-stu-id="9c335-111">Errors setting member values</span></span>

<span data-ttu-id="9c335-112">设置 ETS 属性的值时发生的所有错误都将导致引发**SetValueException**或**SetValueInvocationException**异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-112">All errors that occur when setting the value of an ETS property cause a **SetValueException** or **SetValueInvocationException** exception to be thrown.</span></span> <span data-ttu-id="9c335-113">当 ETS 识别到发生错误时，将引发**SetValueException**异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-113">When ETS recognizes that an error occurred a **SetValueException** exception is thrown.</span></span> <span data-ttu-id="9c335-114">当所引用属性的基础 setter 识别到发生错误时，将引发**SetValueInvocationException**异常，该异常可能包含或可能不包含导致集调用错误的内部异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-114">When the underlying setter of a referenced property recognizes that an error occurred, a **SetValueInvocationException** exception is thrown that may or may not include the inner exception that caused the set invocation error.</span></span>

## <a name="errors-invoking-a-method"></a><span data-ttu-id="9c335-115">调用方法时出错</span><span class="sxs-lookup"><span data-stu-id="9c335-115">Errors invoking a method</span></span>

<span data-ttu-id="9c335-116">调用 ETS 方法时发生的所有错误都会导致引发**MethodException**或**MethodInvocationException**异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-116">All errors that occur when invoking an ETS method cause a **MethodException** or **MethodInvocationException** exception to be thrown.</span></span> <span data-ttu-id="9c335-117">当 ETS 识别到发生错误时，将引发**MethodException**异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-117">When ETS recognizes that an error occurred a **MethodException** exception is thrown.</span></span> <span data-ttu-id="9c335-118">当被引用的方法识别到发生错误时，将引发**MethodInvocationException**异常，该异常可能包含或可能不包含导致调用错误的内部异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-118">When the referenced method recognizes that an error occurred, a **MethodInvocationException** exception is thrown that may or may not include the inner exception that caused the invocation error.</span></span>

## <a name="casting-errors"></a><span data-ttu-id="9c335-119">转换错误</span><span class="sxs-lookup"><span data-stu-id="9c335-119">Casting errors</span></span>

<span data-ttu-id="9c335-120">尝试无效强制转换时，将引发**PSInvalidCastException** 。</span><span class="sxs-lookup"><span data-stu-id="9c335-120">When an invalid cast is attempted, an **PSInvalidCastException** is thrown.</span></span> <span data-ttu-id="9c335-121">由于此异常派生自**InvalidCastException**，因此无法直接从脚本中捕获该异常。</span><span class="sxs-lookup"><span data-stu-id="9c335-121">Because this exception derives from **System.InvalidCastException**, it is not able to be directly trapped from script.</span></span> <span data-ttu-id="9c335-122">请注意，尝试强制转换的实体需要将**PSInvalidCastException**中的**PSRuntimeException**包装起来，才能由脚本捕获。</span><span class="sxs-lookup"><span data-stu-id="9c335-122">Be aware that the entity attempting the cast would need to wrap **PSInvalidCastException** in an **PSRuntimeException** for this to be trappable by scripts.</span></span> <span data-ttu-id="9c335-123">如果尝试设置**PSPropertySet**、 **PSMemberSet**、 **PSMethodInfo**或**ReadOnlyPSMemberInfoCollection ' 1**的成员的值，则会引发**NotSupportedException** 。</span><span class="sxs-lookup"><span data-stu-id="9c335-123">If an attempt is made to set the value of an **PSPropertySet**, **PSMemberSet**, **PSMethodInfo**, or a member of the **ReadOnlyPSMemberInfoCollection\`1**, a **NotSupportedException** is thrown.</span></span>

## <a name="common-runtime-errors"></a><span data-ttu-id="9c335-124">常见运行时错误</span><span class="sxs-lookup"><span data-stu-id="9c335-124">Common runtime errors</span></span>

<span data-ttu-id="9c335-125">发生的任何其他常见运行时错误都属于类型**ExtendedTypeSystemException**异常，无其他特定异常类型。</span><span class="sxs-lookup"><span data-stu-id="9c335-125">Any other common runtime errors that occur are of type **ExtendedTypeSystemException** exception with no additional specific exception types.</span></span>

## <a name="initialization-errors"></a><span data-ttu-id="9c335-126">初始化错误</span><span class="sxs-lookup"><span data-stu-id="9c335-126">Initialization errors</span></span>

<span data-ttu-id="9c335-127">初始化时可能会发生错误 `types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="9c335-127">Errors may occur when initializing `types.ps1xml`.</span></span> <span data-ttu-id="9c335-128">通常，当 PowerShell 运行时启动时，将显示这些错误。</span><span class="sxs-lookup"><span data-stu-id="9c335-128">Typically, these errors are displayed when the PowerShell runtime starts.</span></span> <span data-ttu-id="9c335-129">不过，也可以在加载模块时显示它们。</span><span class="sxs-lookup"><span data-stu-id="9c335-129">However, they can also be displayed when a module is loaded.</span></span>
