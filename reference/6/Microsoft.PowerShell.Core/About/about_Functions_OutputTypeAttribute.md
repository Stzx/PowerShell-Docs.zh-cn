---
description: 介绍报告函数返回的对象类型的属性。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 94e6ab9926f8d31e6b7602792f836fa5eadd3b50
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199829"
---
# <a name="about-functions-outputtypeattribute"></a><span data-ttu-id="edb3f-104">关于函数 OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="edb3f-104">About Functions OutputTypeAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="edb3f-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="edb3f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="edb3f-106">介绍报告函数返回的对象类型的属性。</span><span class="sxs-lookup"><span data-stu-id="edb3f-106">Describes an attribute that reports the type of object that the function returns.</span></span>

## <a name="long-description"></a><span data-ttu-id="edb3f-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="edb3f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="edb3f-108">OutputType 属性列出函数返回的对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="edb3f-108">The OutputType attribute lists the .NET types of objects that the functions returns.</span></span> <span data-ttu-id="edb3f-109">可以使用其可选的 ParameterSetName 参数为每个参数集列出不同的输出类型。</span><span class="sxs-lookup"><span data-stu-id="edb3f-109">You can use its optional ParameterSetName parameter to list different output types for each parameter set.</span></span>

<span data-ttu-id="edb3f-110">简单函数和高级函数支持 OutputType 特性。</span><span class="sxs-lookup"><span data-stu-id="edb3f-110">The OutputType attribute is supported on simple and advanced functions.</span></span> <span data-ttu-id="edb3f-111">它独立于 CmdletBinding 属性。</span><span class="sxs-lookup"><span data-stu-id="edb3f-111">It is independent of the CmdletBinding attribute.</span></span>

<span data-ttu-id="edb3f-112">OutputType 属性提供该 cmdlet 返回的 **FunctionInfo** 对象的 outputtype 属性的值的值 `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="edb3f-112">The OutputType attribute provides the value of the OutputType property of the **System.Management.Automation.FunctionInfo** object that the `Get-Command` cmdlet returns.</span></span>

<span data-ttu-id="edb3f-113">OutputType 属性值只是一个文档说明。</span><span class="sxs-lookup"><span data-stu-id="edb3f-113">The OutputType attribute value is only a documentation note.</span></span> <span data-ttu-id="edb3f-114">它不是从函数代码派生或与实际函数输出进行比较。</span><span class="sxs-lookup"><span data-stu-id="edb3f-114">It is not derived from the function code or compared to the actual function output.</span></span> <span data-ttu-id="edb3f-115">因此，值可能不准确。</span><span class="sxs-lookup"><span data-stu-id="edb3f-115">As such, the value might be inaccurate.</span></span>

## <a name="syntax"></a><span data-ttu-id="edb3f-116">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="edb3f-116">SYNTAX</span></span>

<span data-ttu-id="edb3f-117">函数的 OutputType 特性具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="edb3f-117">The OutputType attribute of functions has the following syntax:</span></span>

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

<span data-ttu-id="edb3f-118">**ParameterSetName** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="edb3f-118">The **ParameterSetName** parameter is optional.</span></span>

<span data-ttu-id="edb3f-119">可以列出 OutputType 属性中的多个类型。</span><span class="sxs-lookup"><span data-stu-id="edb3f-119">You can list multiple types in the OutputType attribute.</span></span>

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

<span data-ttu-id="edb3f-120">您可以使用 **ParameterSetName** 参数来指示不同的参数集返回不同的类型。</span><span class="sxs-lookup"><span data-stu-id="edb3f-120">You can use the **ParameterSetName** parameter to indicate that different parameter sets return different types.</span></span>

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

<span data-ttu-id="edb3f-121">将 OutputType 属性语句放在语句之前的属性列表中 `Param` 。</span><span class="sxs-lookup"><span data-stu-id="edb3f-121">Place the OutputType attribute statements in the attributes list that precedes the `Param` statement.</span></span>

<span data-ttu-id="edb3f-122">下面的示例演示了一个简单函数中 OutputType 特性的位置。</span><span class="sxs-lookup"><span data-stu-id="edb3f-122">The following example shows the placement of the OutputType attribute in a simple function.</span></span>

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

<span data-ttu-id="edb3f-123">下面的示例演示了在高级函数中放置 OutputType 属性的情况。</span><span class="sxs-lookup"><span data-stu-id="edb3f-123">The following example shows the placement of the OutputType attribute in advanced functions.</span></span>

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a><span data-ttu-id="edb3f-124">示例</span><span class="sxs-lookup"><span data-stu-id="edb3f-124">EXAMPLES</span></span>

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a><span data-ttu-id="edb3f-125">示例1：创建具有字符串 OutputType 的函数</span><span class="sxs-lookup"><span data-stu-id="edb3f-125">Example 1: Create a function that has the OutputType of String</span></span>

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

<span data-ttu-id="edb3f-126">若要查看生成的输出类型属性，请使用 `Get-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="edb3f-126">To see the resulting output type property, use the `Get-Command` cmdlet.</span></span>

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a><span data-ttu-id="edb3f-127">示例2：使用 Output 特性指示动态输出类型</span><span class="sxs-lookup"><span data-stu-id="edb3f-127">Example 2: Use the Output attribute to indicate dynamic output types</span></span>

<span data-ttu-id="edb3f-128">以下高级函数使用 OutputType 属性来指示函数返回不同的类型，具体取决于 function 命令中使用的参数集。</span><span class="sxs-lookup"><span data-stu-id="edb3f-128">The following advanced function uses the OutputType attribute to indicate that the function returns different types depending on the parameter set used in the function command.</span></span>

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a><span data-ttu-id="edb3f-129">示例3：显示实际输出不同于 OutputType 的情况</span><span class="sxs-lookup"><span data-stu-id="edb3f-129">Example 3: Shows when an actual output differs from the OutputType</span></span>

<span data-ttu-id="edb3f-130">下面的示例演示 output type 属性值显示 OutputType 属性的值，即使它不准确。</span><span class="sxs-lookup"><span data-stu-id="edb3f-130">The following example demonstrates that the output type property value displays the value of the OutputType attribute, even when it is inaccurate.</span></span>

<span data-ttu-id="edb3f-131">`Get-Time`函数返回一个字符串，该字符串包含任何 DateTime 对象中的时间的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="edb3f-131">The `Get-Time` function returns a string that contains the short form of the time in any DateTime object.</span></span> <span data-ttu-id="edb3f-132">但是，OutputType 属性会报告它 **返回了 system.string 对象。**</span><span class="sxs-lookup"><span data-stu-id="edb3f-132">However, the OutputType attribute reports that it returns a **System.DateTime** object.</span></span>

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

<span data-ttu-id="edb3f-133">`GetType()`方法确认函数返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="edb3f-133">The `GetType()` method confirms that the function returns a string.</span></span>

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

<span data-ttu-id="edb3f-134">但是，OutputType 属性从 OutputType 特性获取其值，它报告该函数返回 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="edb3f-134">However, the OutputType property, which gets its value from the OutputType attribute, reports that the function returns a **DateTime** object.</span></span>

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a><span data-ttu-id="edb3f-135">示例4：不应具有输出的函数</span><span class="sxs-lookup"><span data-stu-id="edb3f-135">Example 4: A function  that shouldn't have output</span></span>

<span data-ttu-id="edb3f-136">下面的示例演示了应执行和操作但不返回任何内容的自定义函数。</span><span class="sxs-lookup"><span data-stu-id="edb3f-136">The following example shows a custom function that should perform and action but not return anything.</span></span>

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a><span data-ttu-id="edb3f-137">注释</span><span class="sxs-lookup"><span data-stu-id="edb3f-137">NOTES</span></span>

<span data-ttu-id="edb3f-138">**FunctionInfo** 对象的 OutputType 属性的值是 **PSTypeName** 对象的数组，其中每个对象都具有 Name 和 Type 属性。</span><span class="sxs-lookup"><span data-stu-id="edb3f-138">The value of the OutputType property of a **FunctionInfo** object is an array of **System.Management.Automation.PSTypeName** objects, each of which have Name and Type properties.</span></span>

<span data-ttu-id="edb3f-139">若要仅获取每个输出类型的名称，请使用具有以下格式的命令。</span><span class="sxs-lookup"><span data-stu-id="edb3f-139">To get only the name of each output type, use a command with the following format.</span></span>

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

<span data-ttu-id="edb3f-140">OutputType 属性的值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="edb3f-140">The value of the OutputType property can be null.</span></span> <span data-ttu-id="edb3f-141">当输出不是 .NET 类型（如 **WMI** 对象或对象的格式化视图）时，请使用 null 值。</span><span class="sxs-lookup"><span data-stu-id="edb3f-141">Use a null value when the output is a not a .NET type, such as a **WMI** object or a formatted view of an object.</span></span>

## <a name="see-also"></a><span data-ttu-id="edb3f-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edb3f-142">SEE ALSO</span></span>

[<span data-ttu-id="edb3f-143">about_Functions</span><span class="sxs-lookup"><span data-stu-id="edb3f-143">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="edb3f-144">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="edb3f-144">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="edb3f-145">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="edb3f-145">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="edb3f-146">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="edb3f-146">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="edb3f-147">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="edb3f-147">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)
