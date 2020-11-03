---
description: 说明如何将参数添加到高级函数。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 4123d71392f8b32df8d04033d85476cb18b39736
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "93200743"
---
# <a name="about-functions-advanced-parameters"></a><span data-ttu-id="ab08e-104">关于函数高级参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-104">About Functions Advanced Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="ab08e-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ab08e-105">Short description</span></span>

<span data-ttu-id="ab08e-106">说明如何将参数添加到高级函数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-106">Explains how to add parameters to advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="ab08e-107">长说明</span><span class="sxs-lookup"><span data-stu-id="ab08e-107">Long description</span></span>

<span data-ttu-id="ab08e-108">你可以向你编写的高级函数添加参数，并使用参数特性和参数来限制函数用户使用参数提交的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-108">You can add parameters to the advanced functions that you write, and use parameter attributes and arguments to limit the parameter values that function users submit with the parameter.</span></span>

<span data-ttu-id="ab08e-109">除了 PowerShell 自动添加到所有 cmdlet 和高级函数的通用参数外，添加到函数的参数还可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="ab08e-109">The parameters that you add to your function are available to users in addition to the common parameters that PowerShell adds automatically to all cmdlets and advanced functions.</span></span> <span data-ttu-id="ab08e-110">有关 PowerShell 通用参数的详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-110">For more information about the PowerShell common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="ab08e-111">从 PowerShell 3.0 开始，可以将展开与结合使用 `@Args` 来表示命令中的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-111">Beginning in PowerShell 3.0, you can use splatting with `@Args` to represent the parameters in a command.</span></span> <span data-ttu-id="ab08e-112">展开在简单函数和高级函数中有效。</span><span class="sxs-lookup"><span data-stu-id="ab08e-112">Splatting is valid on simple and advanced functions.</span></span> <span data-ttu-id="ab08e-113">有关详细信息，请参阅 [about_Functions](about_Functions.md) 和 [about_Splatting](about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-113">For more information, see [about_Functions](about_Functions.md) and [about_Splatting](about_Splatting.md).</span></span>

## <a name="type-conversion-of-parameter-values"></a><span data-ttu-id="ab08e-114">参数值的类型转换</span><span class="sxs-lookup"><span data-stu-id="ab08e-114">Type conversion of parameter values</span></span>

<span data-ttu-id="ab08e-115">将字符串作为参数提供给需要不同类型的参数时，PowerShell 会将这些字符串隐式转换为参数目标类型。</span><span class="sxs-lookup"><span data-stu-id="ab08e-115">When you supply strings as arguments to parameters that expect a different type, PowerShell implicitly converts the strings to the parameter target type.</span></span>
<span data-ttu-id="ab08e-116">高级函数执行参数值的区域性固定分析。</span><span class="sxs-lookup"><span data-stu-id="ab08e-116">Advanced functions perform culture-invariant parsing of parameter values.</span></span>

<span data-ttu-id="ab08e-117">与此相反，在编译的 cmdlet 的参数绑定期间执行区分区域性的转换。</span><span class="sxs-lookup"><span data-stu-id="ab08e-117">By contrast, a culture-sensitive conversion is performed during parameter binding for compiled cmdlets.</span></span>

<span data-ttu-id="ab08e-118">在此示例中，我们将创建一个 cmdlet 和一个带有参数的脚本函数 `[datetime]` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-118">In this example, we create a cmdlet and a script function that take a `[datetime]` parameter.</span></span> <span data-ttu-id="ab08e-119">将当前区域性更改为使用德语设置。</span><span class="sxs-lookup"><span data-stu-id="ab08e-119">The current culture is changed to use German settings.</span></span>
<span data-ttu-id="ab08e-120">德语格式的日期将传递给参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-120">A German-formatted date is passed to the parameter.</span></span>

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

<span data-ttu-id="ab08e-121">如上所示，cmdlet 使用区分区域性的分析来转换字符串。</span><span class="sxs-lookup"><span data-stu-id="ab08e-121">As shown above, cmdlets use culture-sensitive parsing to convert the string.</span></span>

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

<span data-ttu-id="ab08e-122">高级函数使用区域性固定的分析，这会导致出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-122">Advanced functions use culture-invariant parsing, which results in the following error.</span></span>

```Output
Get-Date_Func : Cannot process argument transformation on parameter 'Date'. Cannot convert
 value "19-06-2018" to type "System.DateTime". Error: "String was not recognized as a valid
 DateTime."
At line:13 char:15
+ Get-Date_Func $dateStr
+               ~~~~~~~~
    + CategoryInfo          : InvalidData: (:) [Get-Date_Func], ParameterBindingArgumentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Get-Date_Func
```

## <a name="static-parameters"></a><span data-ttu-id="ab08e-123">静态参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-123">Static parameters</span></span>

<span data-ttu-id="ab08e-124">静态参数是函数中始终可用的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-124">Static parameters are parameters that are always available in the function.</span></span>
<span data-ttu-id="ab08e-125">PowerShell cmdlet 和脚本中的大多数参数均为静态参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-125">Most parameters in PowerShell cmdlets and scripts are static parameters.</span></span>

<span data-ttu-id="ab08e-126">下面的示例演示具有以下特征的 **ComputerName** 参数的声明：</span><span class="sxs-lookup"><span data-stu-id="ab08e-126">The following example shows the declaration of a **ComputerName** parameter that has the following characteristics:</span></span>

- <span data-ttu-id="ab08e-127">这是必需的)  (必需的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-127">It's mandatory (required).</span></span>
- <span data-ttu-id="ab08e-128">它从管道中获取输入。</span><span class="sxs-lookup"><span data-stu-id="ab08e-128">It takes input from the pipeline.</span></span>
- <span data-ttu-id="ab08e-129">它采用字符串数组作为输入。</span><span class="sxs-lookup"><span data-stu-id="ab08e-129">It takes an array of strings as input.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a><span data-ttu-id="ab08e-130">参数的特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-130">Attributes of parameters</span></span>

<span data-ttu-id="ab08e-131">本节介绍可添加到函数参数的属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-131">This section describes the attributes that you can add to function parameters.</span></span>

<span data-ttu-id="ab08e-132">所有特性都是可选的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-132">All attributes are optional.</span></span> <span data-ttu-id="ab08e-133">但是，如果省略了 **CmdletBinding** 属性，则将其识别为高级函数时，该函数必须包括 **Parameter** 属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-133">However, if you omit the **CmdletBinding** attribute, then to be recognized as an advanced function, the function must include the **Parameter** attribute.</span></span>

<span data-ttu-id="ab08e-134">可以在每个参数声明中添加一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-134">You can add one or multiple attributes in each parameter declaration.</span></span> <span data-ttu-id="ab08e-135">可以添加到参数声明中的属性数没有限制。</span><span class="sxs-lookup"><span data-stu-id="ab08e-135">There's no limit to the number of attributes that you can add to a parameter declaration.</span></span>

### <a name="parameter-attribute"></a><span data-ttu-id="ab08e-136">参数属性</span><span class="sxs-lookup"><span data-stu-id="ab08e-136">Parameter attribute</span></span>

<span data-ttu-id="ab08e-137">**参数** 属性用于声明函数参数的属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-137">The **Parameter** attribute is used to declare the attributes of function parameters.</span></span>

<span data-ttu-id="ab08e-138">**参数** 属性是可选的，如果函数的参数均不需要属性，则可以省略此属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-138">The **Parameter** attribute is optional, and you can omit it if none of the parameters of your functions need attributes.</span></span> <span data-ttu-id="ab08e-139">但是，若要被识别为高级函数而不是简单函数，函数必须有 **CmdletBinding** 特性或 **Parameter** 特性，或者两者都是。</span><span class="sxs-lookup"><span data-stu-id="ab08e-139">But, to be recognized as an advanced function, rather than a simple function, a function must have either the **CmdletBinding** attribute or the **Parameter** attribute, or both.</span></span>

<span data-ttu-id="ab08e-140">**参数** 特性具有定义参数特征的参数，如参数是必需还是可选的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-140">The **Parameter** attribute has arguments that define the characteristics of the parameter, such as whether the parameter is mandatory or optional.</span></span>

<span data-ttu-id="ab08e-141">使用以下语法声明 **参数** 属性、参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-141">Use the following syntax to declare the **Parameter** attribute, an argument, and an argument value.</span></span> <span data-ttu-id="ab08e-142">括住参数及其值的括号必须跟在不带空格的 **参数** 之后。</span><span class="sxs-lookup"><span data-stu-id="ab08e-142">The parentheses that enclose the argument and its value must follow **Parameter** with no intervening space.</span></span>

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

<span data-ttu-id="ab08e-143">使用逗号分隔括号内的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-143">Use commas to separate arguments within the parentheses.</span></span> <span data-ttu-id="ab08e-144">使用以下语法声明 **参数** 特性的两个参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-144">Use the following syntax to declare two arguments of the **Parameter** attribute.</span></span>

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

<span data-ttu-id="ab08e-145">**参数特性的** 布尔参数类型在从 **参数** 特性中省略时默认为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-145">The boolean argument types of the **Parameter** attribute default to **False** when omitted from the **Parameter** attribute.</span></span> <span data-ttu-id="ab08e-146">将参数值设置为 `$true` 或只按名称列出参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-146">Set the argument value to `$true` or just list the argument by name.</span></span> <span data-ttu-id="ab08e-147">例如，以下 **参数** 属性是等效的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-147">For example, the following **Parameter** attributes are equivalent.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

<span data-ttu-id="ab08e-148">如果使用不带参数的 **参数** 特性，作为使用 **CmdletBinding** 特性的替代方法，仍需使用特性名称后面的括号。</span><span class="sxs-lookup"><span data-stu-id="ab08e-148">If you use the **Parameter** attribute without arguments, as an alternative to using the **CmdletBinding** attribute, the parentheses that follow the attribute name are still required.</span></span>

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a><span data-ttu-id="ab08e-149">必需参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-149">Mandatory argument</span></span>

<span data-ttu-id="ab08e-150">`Mandatory`参数指示参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-150">The `Mandatory` argument indicates that the parameter is required.</span></span> <span data-ttu-id="ab08e-151">如果未指定此参数，则该参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-151">If this argument isn't specified, the parameter is optional.</span></span>

<span data-ttu-id="ab08e-152">下面的示例声明 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-152">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="ab08e-153">它使用 `Mandatory` 参数以使参数成为必需的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-153">It uses the `Mandatory` argument to make the parameter mandatory.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a><span data-ttu-id="ab08e-154">Position 参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-154">Position argument</span></span>

<span data-ttu-id="ab08e-155">参数 `Position` 确定在命令中使用参数时，参数名是否是必需的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-155">The `Position` argument determines whether the parameter name is required when the parameter is used in a command.</span></span> <span data-ttu-id="ab08e-156">如果参数声明包含 `Position` 参数，则可以省略参数名，并且 PowerShell 将通过命令中未命名的参数值列表中的位置或顺序来标识未命名的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-156">When a parameter declaration includes the `Position` argument, the parameter name can be omitted and PowerShell identifies the unnamed parameter value by its position, or order, in the list of unnamed parameter values in the command.</span></span>

<span data-ttu-id="ab08e-157">如果 `Position` 未指定参数，则每次在命令中使用参数时，参数名称或参数名别名或缩写都必须在参数值之前。</span><span class="sxs-lookup"><span data-stu-id="ab08e-157">If the `Position` argument isn't specified, the parameter name, or a parameter name alias or abbreviation, must precede the parameter value whenever the parameter is used in a command.</span></span>

<span data-ttu-id="ab08e-158">默认情况下，所有函数参数都是位置。</span><span class="sxs-lookup"><span data-stu-id="ab08e-158">By default, all function parameters are positional.</span></span> <span data-ttu-id="ab08e-159">PowerShell 将位置编号按参数在函数中的声明顺序分配给参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-159">PowerShell assigns position numbers to parameters in the order in which the parameters are declared in the function.</span></span> <span data-ttu-id="ab08e-160">若要禁用此功能，请将 `PositionalBinding` **CmdletBinding** 属性的参数值设置为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-160">To disable this feature, set the value of the `PositionalBinding` argument of the **CmdletBinding** attribute to `$False`.</span></span> <span data-ttu-id="ab08e-161">`Position`参数优先于 `PositionalBinding` **CmdletBinding** 属性的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-161">The `Position` argument takes precedence over the value of the `PositionalBinding` argument of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="ab08e-162">有关详细信息，请 `PositionalBinding` 参阅 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)中的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-162">For more information, see `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="ab08e-163">参数的值 `Position` 指定为整数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-163">The value of the `Position` argument is specified as an integer.</span></span> <span data-ttu-id="ab08e-164">位置值 **0** 表示命令中的第一个位置，位置值 **1** 表示命令中的第二个位置，依此类推。</span><span class="sxs-lookup"><span data-stu-id="ab08e-164">A position value of **0** represents the first position in the command, a position value of **1** represents the second position in the command, and so on.</span></span>

<span data-ttu-id="ab08e-165">如果函数没有位置参数，则 PowerShell 会根据参数的声明顺序将位置分配给每个参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-165">If a function has no positional parameters, PowerShell assigns positions to each parameter based on the order in which the parameters are declared.</span></span>
<span data-ttu-id="ab08e-166">但是，最佳做法是不要依赖于此分配。</span><span class="sxs-lookup"><span data-stu-id="ab08e-166">However, as a best practice, don't rely on this assignment.</span></span> <span data-ttu-id="ab08e-167">如果要将参数定位到位置，请使用 `Position` 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-167">When you want parameters to be positional, use the `Position` argument.</span></span>

<span data-ttu-id="ab08e-168">下面的示例声明 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-168">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="ab08e-169">它使用 `Position` 值为 **0** 的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-169">It uses the `Position` argument with a value of **0** .</span></span> <span data-ttu-id="ab08e-170">因此，当 `-ComputerName` 从命令中省略时，其值必须是命令中的第一个或唯一一个未命名的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-170">As a result, when `-ComputerName` is omitted from command, its value must be the first or only unnamed parameter value in the command.</span></span>

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a><span data-ttu-id="ab08e-171">ParameterSetName 参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-171">ParameterSetName argument</span></span>

<span data-ttu-id="ab08e-172">`ParameterSetName`参数指定参数所属的参数集。</span><span class="sxs-lookup"><span data-stu-id="ab08e-172">The `ParameterSetName` argument specifies the parameter set to which a parameter belongs.</span></span> <span data-ttu-id="ab08e-173">如果未指定参数集，则参数属于函数定义的所有参数集。</span><span class="sxs-lookup"><span data-stu-id="ab08e-173">If no parameter set is specified, the parameter belongs to all the parameter sets defined by the function.</span></span> <span data-ttu-id="ab08e-174">因此，若要为唯一，每个参数集必须至少具有一个不是任何其他参数集成员的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-174">Therefore, to be unique, each parameter set must have at least one parameter that isn't a member of any other parameter set.</span></span>

> [!NOTE]
> <span data-ttu-id="ab08e-175">对于 cmdlet 或函数，有32个参数集的限制。</span><span class="sxs-lookup"><span data-stu-id="ab08e-175">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

<span data-ttu-id="ab08e-176">下面的示例在 **ComputerName** `Computer` 参数集、参数集中的 **用户名** 参数以及 `User` 这两个参数集中的 **Summary** 参数中声明了 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-176">The following example declares a **ComputerName** parameter in the `Computer` parameter set, a **UserName** parameter in the `User` parameter set, and a **Summary** parameter in both parameter sets.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

<span data-ttu-id="ab08e-177">只能在 `ParameterSetName` 每个参数中指定一个值， `ParameterSetName` 每个 **参数** 特性中只能指定一个参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-177">You can specify only one `ParameterSetName` value in each argument and only one `ParameterSetName` argument in each **Parameter** attribute.</span></span> <span data-ttu-id="ab08e-178">若要指示参数出现在多个参数集中，请添加其他 **参数** 属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-178">To indicate that a parameter appears in more than one parameter set, add additional **Parameter** attributes.</span></span>

<span data-ttu-id="ab08e-179">下面的示例将 **Summary** 参数显式添加到 `Computer` 和 `User` 参数集。</span><span class="sxs-lookup"><span data-stu-id="ab08e-179">The following example explicitly adds the **Summary** parameter to the `Computer` and `User` parameter sets.</span></span> <span data-ttu-id="ab08e-180">**Summary** 参数在参数集中是可选的 `Computer` ，并且在参数集中是必需的 `User` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-180">The **Summary** parameter is optional in the `Computer` parameter set and mandatory in the `User` parameter set.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

<span data-ttu-id="ab08e-181">有关参数集的详细信息，请参阅 [关于参数集](about_parameter_sets.md)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-181">For more information about parameter sets, see [About Parameter Sets](about_parameter_sets.md).</span></span>

#### <a name="valuefrompipeline-argument"></a><span data-ttu-id="ab08e-182">ValueFromPipeline 参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-182">ValueFromPipeline argument</span></span>

<span data-ttu-id="ab08e-183">`ValueFromPipeline`参数指示参数接受来自管道对象的输入。</span><span class="sxs-lookup"><span data-stu-id="ab08e-183">The `ValueFromPipeline` argument indicates that the parameter accepts input from a pipeline object.</span></span> <span data-ttu-id="ab08e-184">如果函数接受整个对象，而不只是对象的属性，则指定此参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-184">Specify this argument if the function accepts the entire object, not just a property of the object.</span></span>

<span data-ttu-id="ab08e-185">下面的示例声明一个必需的 **ComputerName** 参数，并接受从管道传递到函数的对象。</span><span class="sxs-lookup"><span data-stu-id="ab08e-185">The following example declares a **ComputerName** parameter that's mandatory and accepts an object that's passed to the function from the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a><span data-ttu-id="ab08e-186">ValueFromPipelineByPropertyName 参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-186">ValueFromPipelineByPropertyName argument</span></span>

<span data-ttu-id="ab08e-187">`ValueFromPipelineByPropertyName`参数指示参数接受管道对象的属性输入。</span><span class="sxs-lookup"><span data-stu-id="ab08e-187">The `ValueFromPipelineByPropertyName` argument indicates that the parameter accepts input from a property of a pipeline object.</span></span> <span data-ttu-id="ab08e-188">对象属性必须与参数具有相同的名称或别名。</span><span class="sxs-lookup"><span data-stu-id="ab08e-188">The object property must have the same name or alias as the parameter.</span></span>

<span data-ttu-id="ab08e-189">例如，如果该函数具有 **computername** 参数，且该管道对象具有 **computername** 属性，则 **computername** 属性的值将分配给该函数的 **computername** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-189">For example, if the function has a **ComputerName** parameter, and the piped object has a **ComputerName** property, the value of the **ComputerName** property is assigned to the function's **ComputerName** parameter.</span></span>

<span data-ttu-id="ab08e-190">下面的示例声明一个必需的 **ComputerName** 参数，并接受通过管道传递给函数的对象 **computername** 属性中的输入。</span><span class="sxs-lookup"><span data-stu-id="ab08e-190">The following example declares a **ComputerName** parameter that's mandatory and accepts input from the object's **ComputerName** property that's passed to the function through the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> <span data-ttu-id="ab08e-191">一个类型化参数，该参数接受管道输入 (`by Value`) 或 (`by PropertyName`) 允许在参数上使用 _延迟绑定_ 脚本块。</span><span class="sxs-lookup"><span data-stu-id="ab08e-191">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of _delay-bind_ script blocks on the parameter.</span></span>
>
> <span data-ttu-id="ab08e-192">_延迟绑定_ 脚本块在 **ParameterBinding** 期间自动运行。</span><span class="sxs-lookup"><span data-stu-id="ab08e-192">The _delay-bind_ script block is run automatically during **ParameterBinding** .</span></span> <span data-ttu-id="ab08e-193">结果绑定到参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-193">The result is bound to the parameter.</span></span> <span data-ttu-id="ab08e-194">延迟绑定对于定义为类型或的参数不起作用 `ScriptBlock` `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-194">Delay binding does not work for parameters defined as type `ScriptBlock` or `System.Object`.</span></span> <span data-ttu-id="ab08e-195">_不_ 调用脚本块。</span><span class="sxs-lookup"><span data-stu-id="ab08e-195">The script block is passed through _without_ being invoked.</span></span>
>
> <span data-ttu-id="ab08e-196">可在此处阅读有关 _延迟绑定_ 脚本块的 [about_Script_Blocks。](about_Script_Blocks.md)</span><span class="sxs-lookup"><span data-stu-id="ab08e-196">You can read about _delay-bind_ script blocks here [about_Script_Blocks.md](about_Script_Blocks.md).</span></span>

#### <a name="valuefromremainingarguments-argument"></a><span data-ttu-id="ab08e-197">ValueFromRemainingArguments 参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-197">ValueFromRemainingArguments argument</span></span>

<span data-ttu-id="ab08e-198">`ValueFromRemainingArguments`参数指示参数接受命令中的所有参数值，这些值未分配给函数的其他参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-198">The `ValueFromRemainingArguments` argument indicates that the parameter accepts all the parameter's values in the command that aren't assigned to other parameters of the function.</span></span>

<span data-ttu-id="ab08e-199">使用带有 **ValueFromRemainingArguments** 的集合有一个已知问题，其中传入的集合被视为单个元素。</span><span class="sxs-lookup"><span data-stu-id="ab08e-199">There's a known issue for using collections with **ValueFromRemainingArguments** where the passed-in collection is treated as a single element.</span></span>

<span data-ttu-id="ab08e-200">下面的示例演示了此已知问题。</span><span class="sxs-lookup"><span data-stu-id="ab08e-200">The following example demonstrates this known issue.</span></span> <span data-ttu-id="ab08e-201">**剩余** 的参数应在索引 **0** 处包含 **一个** 参数，在 **索引 1** 处包含 **2 个** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-201">The **Remaining** parameter should contain **one** at **index 0** and **two** at **index 1** .</span></span>
<span data-ttu-id="ab08e-202">相反，这两个元素合并到一个实体中。</span><span class="sxs-lookup"><span data-stu-id="ab08e-202">Instead, both elements are combined into a single entity.</span></span>

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 1 elements
0: one two
```

> [!NOTE]
> <span data-ttu-id="ab08e-203">此问题已在 PowerShell 6.2 中解决。</span><span class="sxs-lookup"><span data-stu-id="ab08e-203">This issue is resolved in PowerShell 6.2.</span></span>

#### <a name="helpmessage-argument"></a><span data-ttu-id="ab08e-204">HelpMessage 参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-204">HelpMessage argument</span></span>

<span data-ttu-id="ab08e-205">`HelpMessage`参数指定一个字符串，其中包含参数或其值的简短说明。</span><span class="sxs-lookup"><span data-stu-id="ab08e-205">The `HelpMessage` argument specifies a string that contains a brief description of the parameter or its value.</span></span> <span data-ttu-id="ab08e-206">当命令中缺少必需的参数值时，PowerShell 将在出现的提示中显示此消息。</span><span class="sxs-lookup"><span data-stu-id="ab08e-206">PowerShell displays this message in the prompt that appears when a mandatory parameter value is missing from a command.</span></span> <span data-ttu-id="ab08e-207">此参数对可选参数无效。</span><span class="sxs-lookup"><span data-stu-id="ab08e-207">This argument has no effect on optional parameters.</span></span>

<span data-ttu-id="ab08e-208">下面的示例声明一个必需的 **ComputerName** 参数和一个帮助消息，用于说明所需的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-208">The following example declares a mandatory **ComputerName** parameter and a help message that explains the expected parameter value.</span></span>

<span data-ttu-id="ab08e-209">如果函数没有其他 [基于注释的帮助](./about_comment_based_help.md) 语法 (例如， `.SYNOPSIS`) 则此消息也会显示在 `Get-Help` 输出中。</span><span class="sxs-lookup"><span data-stu-id="ab08e-209">If there is no other [comment-based help](./about_comment_based_help.md) syntax for the function (for example, `.SYNOPSIS`) then this message also shows up in `Get-Help` output.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a><span data-ttu-id="ab08e-210">Alias 特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-210">Alias attribute</span></span>

<span data-ttu-id="ab08e-211">**Alias** 属性为参数建立替换名称。</span><span class="sxs-lookup"><span data-stu-id="ab08e-211">The **Alias** attribute establishes an alternate name for the parameter.</span></span>
<span data-ttu-id="ab08e-212">可以分配给参数的别名数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="ab08e-212">There's no limit to the number of aliases that you can assign to a parameter.</span></span>

<span data-ttu-id="ab08e-213">下面的示例演示了一个参数声明，该声明将 **CN** 和 **MachineName** 别名添加到必需的 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-213">The following example shows a parameter declaration that adds the **CN** and **MachineName** aliases to the mandatory **ComputerName** parameter.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a><span data-ttu-id="ab08e-214">SupportsWildcards 特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-214">SupportsWildcards attribute</span></span>

<span data-ttu-id="ab08e-215">**SupportsWildcards** 特性用于指示参数接受通配符值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-215">The **SupportsWildcards** attribute is used to indicate that the parameter accepts wildcard values.</span></span> <span data-ttu-id="ab08e-216">下面的示例演示了支持通配符值的强制 **路径** 参数的参数声明。</span><span class="sxs-lookup"><span data-stu-id="ab08e-216">The following example shows a parameter declaration for a mandatory **Path** parameter that supports wildcard values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

<span data-ttu-id="ab08e-217">使用此属性不会自动启用通配符支持。</span><span class="sxs-lookup"><span data-stu-id="ab08e-217">Using this attribute does not automatically enable wildcard support.</span></span> <span data-ttu-id="ab08e-218">Cmdlet 开发人员必须实现代码来处理通配符输入。</span><span class="sxs-lookup"><span data-stu-id="ab08e-218">The cmdlet developer must implement the code to handle the wildcard input.</span></span> <span data-ttu-id="ab08e-219">支持的通配符可能因基础 API 或 PowerShell 提供程序而异。</span><span class="sxs-lookup"><span data-stu-id="ab08e-219">The wildcards supported can vary according to the underlying API or PowerShell provider.</span></span> <span data-ttu-id="ab08e-220">有关详细信息，请参阅 [about_Wildcards](about_Wildcards.md)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-220">For more information, see [about_Wildcards](about_Wildcards.md).</span></span>

### <a name="parameter-and-variable-validation-attributes"></a><span data-ttu-id="ab08e-221">参数和变量验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-221">Parameter and variable validation attributes</span></span>

<span data-ttu-id="ab08e-222">验证特性直接 PowerShell 用于测试用户在调用 advanced 函数时提交的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-222">Validation attributes direct PowerShell to test the parameter values that users submit when they call the advanced function.</span></span> <span data-ttu-id="ab08e-223">如果参数值未通过测试，则会生成错误，并且不会调用函数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-223">If the parameter values fail the test, an error is generated and the function isn't called.</span></span> <span data-ttu-id="ab08e-224">参数验证仅适用于所提供的输入，并且不会验证任何其他值（如默认值）。</span><span class="sxs-lookup"><span data-stu-id="ab08e-224">Parameter validation is only applied to the input provided and any other values like default values are not validated.</span></span>

<span data-ttu-id="ab08e-225">你还可以使用验证属性来限制用户可以为变量指定的值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-225">You can also use the validation attributes to restrict the values that users can specify for variables.</span></span> <span data-ttu-id="ab08e-226">将类型转换器与验证特性一起使用时，必须在特性之前定义类型转换器。</span><span class="sxs-lookup"><span data-stu-id="ab08e-226">When you use a type converter along with a validation attribute, the type converter has to be defined before the attribute.</span></span>

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a><span data-ttu-id="ab08e-227">AllowNull 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-227">AllowNull validation attribute</span></span>

<span data-ttu-id="ab08e-228">**AllowNull** 属性允许必需参数的值为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-228">The **AllowNull** attribute allows the value of a mandatory parameter to be `$null`.</span></span> <span data-ttu-id="ab08e-229">下面的示例声明一个可以具有 **null** 值的哈希表 **ComputerInfo** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-229">The following example declares a hashtable **ComputerInfo** parameter that can have a **null** value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> <span data-ttu-id="ab08e-230">如果类型转换器设置为 string，则 **AllowNull** 属性不起作用，因为字符串类型不接受 null 值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-230">The **AllowNull** attribute doesn't work if the type converter is set to string as the string type will not accept a null value.</span></span> <span data-ttu-id="ab08e-231">对于此方案，可以使用 **AllowEmptyString** 属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-231">You can use the **AllowEmptyString** attribute for this scenario.</span></span>

### <a name="allowemptystring-validation-attribute"></a><span data-ttu-id="ab08e-232">AllowEmptyString 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-232">AllowEmptyString validation attribute</span></span>

<span data-ttu-id="ab08e-233">**AllowEmptyString** 属性允许必需参数的值为 () 的空字符串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-233">The **AllowEmptyString** attribute allows the value of a mandatory parameter to be an empty string (`""`).</span></span> <span data-ttu-id="ab08e-234">下面的示例声明一个可以具有空字符串值的 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-234">The following example declares a **ComputerName** parameter that can have an empty string value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a><span data-ttu-id="ab08e-235">AllowEmptyCollection 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-235">AllowEmptyCollection validation attribute</span></span>

<span data-ttu-id="ab08e-236">**AllowEmptyCollection** 属性允许必需参数的值为空集合 `@()` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-236">The **AllowEmptyCollection** attribute allows the value of a mandatory parameter to be an empty collection `@()`.</span></span> <span data-ttu-id="ab08e-237">下面的示例声明一个可以具有空集合值的 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-237">The following example declares a **ComputerName** parameter that can have an empty collection value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a><span data-ttu-id="ab08e-238">ValidateCount 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-238">ValidateCount validation attribute</span></span>

<span data-ttu-id="ab08e-239">**ValidateCount** 属性指定参数接受的参数值的最小值和最大数目。</span><span class="sxs-lookup"><span data-stu-id="ab08e-239">The **ValidateCount** attribute specifies the minimum and maximum number of parameter values that a parameter accepts.</span></span> <span data-ttu-id="ab08e-240">如果调用函数的命令中的参数值数目不在此范围内，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-240">PowerShell generates an error if the number of parameter values in the command that calls the function is outside that range.</span></span>

<span data-ttu-id="ab08e-241">以下参数声明创建一个 **ComputerName** 参数，该参数采用一个到五个参数值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-241">The following parameter declaration creates a **ComputerName** parameter that takes one to five parameter values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a><span data-ttu-id="ab08e-242">ValidateLength 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-242">ValidateLength validation attribute</span></span>

<span data-ttu-id="ab08e-243">**ValidateLength** 属性指定参数或变量值中的最小和最大字符数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-243">The **ValidateLength** attribute specifies the minimum and maximum number of characters in a parameter or variable value.</span></span> <span data-ttu-id="ab08e-244">如果为参数或变量指定的值的长度超出范围，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-244">PowerShell generates an error if the length of a value specified for a parameter or a variable is outside of the range.</span></span>

<span data-ttu-id="ab08e-245">在下面的示例中，每个计算机名必须包含一到十个字符。</span><span class="sxs-lookup"><span data-stu-id="ab08e-245">In the following example, each computer name must have one to ten characters.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="ab08e-246">在下面的示例中，变量的值的 `$number` 长度必须至少为1个字符，最多只能有10个字符。</span><span class="sxs-lookup"><span data-stu-id="ab08e-246">In the following example, the value of the variable `$number` must be a minimum of one character in length, and a maximum of ten characters.</span></span>

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> <span data-ttu-id="ab08e-247">在此示例中，的值 `01` 以单引号括起来。</span><span class="sxs-lookup"><span data-stu-id="ab08e-247">In this example, the value of `01` is wrapped in single quotes.</span></span> <span data-ttu-id="ab08e-248">**ValidateLength** 属性不接受数字，而不会将其包装在引号内。</span><span class="sxs-lookup"><span data-stu-id="ab08e-248">The **ValidateLength** attribute won't accept a number without being wrapped in quotes.</span></span>

### <a name="validatepattern-validation-attribute"></a><span data-ttu-id="ab08e-249">ValidatePattern 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-249">ValidatePattern validation attribute</span></span>

<span data-ttu-id="ab08e-250">**ValidatePattern** 属性指定与参数或变量值进行比较的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="ab08e-250">The **ValidatePattern** attribute specifies a regular expression that's compared to the parameter or variable value.</span></span> <span data-ttu-id="ab08e-251">如果值与正则表达式模式不匹配，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-251">PowerShell generates an error if the value doesn't match the regular expression pattern.</span></span>

<span data-ttu-id="ab08e-252">在下面的示例中，参数值必须包含一个四位数字，并且每个数字必须是从0到9的数字。</span><span class="sxs-lookup"><span data-stu-id="ab08e-252">In the following example, the parameter value must contain a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="ab08e-253">在下面的示例中，变量的值 `$number` 必须是一个四位数字，并且每个数字必须是从0到9的数字。</span><span class="sxs-lookup"><span data-stu-id="ab08e-253">In the following example, the value of the variable `$number` must be exactly a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a><span data-ttu-id="ab08e-254">ValidateRange 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-254">ValidateRange validation attribute</span></span>

<span data-ttu-id="ab08e-255">**ValidateRange** 属性指定每个参数或变量值的数值范围。</span><span class="sxs-lookup"><span data-stu-id="ab08e-255">The **ValidateRange** attribute specifies a numeric range for each parameter or variable value.</span></span> <span data-ttu-id="ab08e-256">如果任何值超出此范围，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-256">PowerShell generates an error if any value is outside that range.</span></span> <span data-ttu-id="ab08e-257">在下面的示例中，" **尝试** " 参数的值必须介于0和10之间。</span><span class="sxs-lookup"><span data-stu-id="ab08e-257">In the following example, the value of the **Attempts** parameter must be between zero and ten.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

<span data-ttu-id="ab08e-258">在下面的示例中，变量的值 `$number` 必须介于0和10之间。</span><span class="sxs-lookup"><span data-stu-id="ab08e-258">In the following example, the value of the variable `$number` must be between zero and ten.</span></span>

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

### <a name="validatescript-validation-attribute"></a><span data-ttu-id="ab08e-259">ValidateScript 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-259">ValidateScript validation attribute</span></span>

<span data-ttu-id="ab08e-260">**ValidateScript** 属性指定用于验证参数或变量值的脚本。</span><span class="sxs-lookup"><span data-stu-id="ab08e-260">The **ValidateScript** attribute specifies a script that is used to validate a parameter or variable value.</span></span> <span data-ttu-id="ab08e-261">PowerShell 将值传递给脚本，如果脚本返回 `$false` 或脚本引发异常，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-261">PowerShell pipes the value to the script, and generates an error if the script returns `$false` or if the script throws an exception.</span></span>

<span data-ttu-id="ab08e-262">使用 **ValidateScript** 属性时，所验证的值将映射到 `$_` 变量。</span><span class="sxs-lookup"><span data-stu-id="ab08e-262">When you use the **ValidateScript** attribute, the value that's being validated is mapped to the `$_` variable.</span></span> <span data-ttu-id="ab08e-263">您可以使用 `$_` 变量来引用脚本中的值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-263">You can use the `$_` variable to refer to the value in the script.</span></span>

<span data-ttu-id="ab08e-264">在下面的示例中， **EventDate** 参数的值必须大于或等于当前日期。</span><span class="sxs-lookup"><span data-stu-id="ab08e-264">In the following example, the value of the **EventDate** parameter must be greater than or equal to the current date.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

<span data-ttu-id="ab08e-265">在下面的示例中，变量的值 `$date` 必须大于或等于当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ab08e-265">In the following example, the value of the variable `$date` must be greater than or equal to the current date and time.</span></span>

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> <span data-ttu-id="ab08e-266">如果使用 **ValidateScript** ，则不能将 `$null` 值传递给参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-266">If you use **ValidateScript** , you cannot pass a `$null` value to the parameter.</span></span> <span data-ttu-id="ab08e-267">传递 null 值时， **ValidateScript** 无法验证参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-267">When you pass a null value **ValidateScript** can't validate the argument.</span></span>

### <a name="validateset-attribute"></a><span data-ttu-id="ab08e-268">ValidateSet 特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-268">ValidateSet attribute</span></span>

<span data-ttu-id="ab08e-269">**ValidateSet** 特性为参数或变量指定一组有效值，并启用 tab 自动补全。</span><span class="sxs-lookup"><span data-stu-id="ab08e-269">The **ValidateSet** attribute specifies a set of valid values for a parameter or variable and enables tab completion.</span></span> <span data-ttu-id="ab08e-270">如果参数或变量值与集中的值不匹配，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-270">PowerShell generates an error if a parameter or variable value doesn't match a value in the set.</span></span> <span data-ttu-id="ab08e-271">在下面的示例中， **Detail** 参数的值只能是 Low、Average 或 High。</span><span class="sxs-lookup"><span data-stu-id="ab08e-271">In the following example, the value of the **Detail** parameter can only be Low, Average, or High.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

<span data-ttu-id="ab08e-272">在下面的示例中，变量的值 `$flavor` 必须是巧克力、草莓或 Vanilla。</span><span class="sxs-lookup"><span data-stu-id="ab08e-272">In the following example, the value of the variable `$flavor` must be either Chocolate, Strawberry, or Vanilla.</span></span>

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

<span data-ttu-id="ab08e-273">只要在脚本内分配了该变量，就会进行验证。</span><span class="sxs-lookup"><span data-stu-id="ab08e-273">The validation occurs whenever that variable is assigned even within the script.</span></span> <span data-ttu-id="ab08e-274">例如，以下错误会导致运行时错误：</span><span class="sxs-lookup"><span data-stu-id="ab08e-274">For example, the following results in an error at runtime:</span></span>

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

### <a name="validatenotnull-validation-attribute"></a><span data-ttu-id="ab08e-275">ValidateNotNull 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-275">ValidateNotNull validation attribute</span></span>

<span data-ttu-id="ab08e-276">**ValidateNotNull** 特性指定参数值不能为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-276">The **ValidateNotNull** attribute specifies that the parameter value can't be `$null`.</span></span> <span data-ttu-id="ab08e-277">如果参数值为，则 PowerShell 会生成错误 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-277">PowerShell generates an error if the parameter value is `$null`.</span></span>

<span data-ttu-id="ab08e-278">当参数为可选且类型为 undefined 或具有不能隐式转换 null 值（如 **对象** ）的类型转换器时，将使用 **ValidateNotNull** 特性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-278">The **ValidateNotNull** attribute is designed to be used when the parameter is optional and the type is undefined or has a type converter that can't implicitly convert a null value like **object** .</span></span> <span data-ttu-id="ab08e-279">如果指定一个将隐式转换为 null 值（如 **字符串** ）的类型，则即使使用 **ValidateNotNull** 属性，也会将空值转换为空字符串。</span><span class="sxs-lookup"><span data-stu-id="ab08e-279">If you specify a type that that will implicitly convert a null value such as a **string** , the null value is converted to an empty string even when using the **ValidateNotNull** attribute.</span></span> <span data-ttu-id="ab08e-280">对于此方案，请使用 **ValidateNotNullOrEmpty**</span><span class="sxs-lookup"><span data-stu-id="ab08e-280">For this scenario use the **ValidateNotNullOrEmpty**</span></span>

<span data-ttu-id="ab08e-281">在下面的示例中， **ID** 参数的值不能为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-281">In the following example, the value of the **ID** parameter can't be `$null`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a><span data-ttu-id="ab08e-282">ValidateNotNullOrEmpty 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-282">ValidateNotNullOrEmpty validation attribute</span></span>

<span data-ttu-id="ab08e-283">**ValidateNotNullOrEmpty** 属性指定 () 参数值不能为 `$null` 空字符串，也不能为空字符串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-283">The **ValidateNotNullOrEmpty** attribute specifies that the parameter value can't be `$null` and can't be an empty string (`""`).</span></span> <span data-ttu-id="ab08e-284">如果在函数调用中使用参数，但其值为 `$null` 、空字符串 (`""`) 或空数组，则 PowerShell 会生成错误 `@()` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-284">PowerShell generates an error if the parameter is used in a function call, but its value is `$null`, an empty string (`""`), or an empty array `@()`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a><span data-ttu-id="ab08e-285">ValidateDrive 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-285">ValidateDrive validation attribute</span></span>

<span data-ttu-id="ab08e-286">**ValidateDrive** 属性指定参数值必须代表路径，该路径仅引用允许的驱动器。</span><span class="sxs-lookup"><span data-stu-id="ab08e-286">The **ValidateDrive** attribute specifies that the parameter value must represent the path, that's referring to allowed drives only.</span></span> <span data-ttu-id="ab08e-287">如果参数值是指除 "允许" 之外的驱动器，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-287">PowerShell generates an error if the parameter value refers to drives other than the allowed.</span></span> <span data-ttu-id="ab08e-288">存在路径（驱动器本身除外），则不会进行验证。</span><span class="sxs-lookup"><span data-stu-id="ab08e-288">Existence of the path, except for the drive itself, isn't verified.</span></span>

<span data-ttu-id="ab08e-289">如果使用相对路径，则当前驱动器必须位于允许的驱动器列表中。</span><span class="sxs-lookup"><span data-stu-id="ab08e-289">If you use relative path, the current drive must be in the allowed drive list.</span></span>

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a><span data-ttu-id="ab08e-290">ValidateUserDrive 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-290">ValidateUserDrive validation attribute</span></span>

<span data-ttu-id="ab08e-291">**ValidateUserDrive** 属性指定参数值必须表示引用驱动器的路径 `User` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-291">The **ValidateUserDrive** attribute specifies that the parameter value must represent the path, that is referring to `User` drive.</span></span> <span data-ttu-id="ab08e-292">如果路径引用其他驱动器，则 PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ab08e-292">PowerShell generates an error if the path refers to a different drive.</span></span> <span data-ttu-id="ab08e-293">验证特性仅测试路径的驱动器部分是否存在。</span><span class="sxs-lookup"><span data-stu-id="ab08e-293">The validation attribute only tests for the existence of the drive portion of the path.</span></span>

<span data-ttu-id="ab08e-294">如果使用相对路径，则当前驱动器必须是 `User` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-294">If you use relative path, the current drive must be `User`.</span></span>

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

<span data-ttu-id="ab08e-295">`User`只需 (JEA) 会话配置中的管理即可定义驱动器。</span><span class="sxs-lookup"><span data-stu-id="ab08e-295">You can define `User` drive in Just Enough Administration (JEA) session configurations.</span></span> <span data-ttu-id="ab08e-296">在此示例中，我们创建了 User：驱动器。</span><span class="sxs-lookup"><span data-stu-id="ab08e-296">For this example, we create the User: drive.</span></span>

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a><span data-ttu-id="ab08e-297">ValidateTrustedData 验证特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-297">ValidateTrustedData validation attribute</span></span>

<span data-ttu-id="ab08e-298">此属性是在 PowerShell 6.1.1 中添加的。</span><span class="sxs-lookup"><span data-stu-id="ab08e-298">This attribute was added in PowerShell 6.1.1.</span></span>

<span data-ttu-id="ab08e-299">此时，属性由 PowerShell 本身在内部使用，不用于外部使用。</span><span class="sxs-lookup"><span data-stu-id="ab08e-299">At this time, the attribute is used internally by PowerShell itself and is not intended for external usage.</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="ab08e-300">动态参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-300">Dynamic parameters</span></span>

<span data-ttu-id="ab08e-301">动态参数是仅在特定条件下可用的 cmdlet、函数或脚本的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-301">Dynamic parameters are parameters of a cmdlet, function, or script that are available only under certain conditions.</span></span>

<span data-ttu-id="ab08e-302">例如，多个提供程序 cmdlet 的参数仅在提供程序驱动器中使用 cmdlet 时，或在提供程序驱动器的特定路径中可用。</span><span class="sxs-lookup"><span data-stu-id="ab08e-302">For example, several provider cmdlets have parameters that are available only when the cmdlet is used in the provider drive, or in a particular path of the provider drive.</span></span> <span data-ttu-id="ab08e-303">例如， **Encoding** `Add-Content` `Get-Content` `Set-Content` 仅当在文件系统驱动器中使用编码参数时，才在、和 cmdlet 上使用该参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-303">For example, the **Encoding** parameter is available on the `Add-Content`, `Get-Content`, and `Set-Content` cmdlets only when it's used in a file system drive.</span></span>

<span data-ttu-id="ab08e-304">你还可以创建一个参数，该参数仅在函数命令中使用另一个参数或其他参数具有特定值时显示。</span><span class="sxs-lookup"><span data-stu-id="ab08e-304">You can also create a parameter that appears only when another parameter is used in the function command or when another parameter has a certain value.</span></span>

<span data-ttu-id="ab08e-305">动态参数非常有用，但仅在必要时才使用，因为它们可能会很难发现用户。</span><span class="sxs-lookup"><span data-stu-id="ab08e-305">Dynamic parameters can be useful, but use them only when necessary, because they can be difficult for users to discover.</span></span> <span data-ttu-id="ab08e-306">若要查找动态参数，用户必须在提供程序路径中，使用 cmdlet 的 **ArgumentList** 参数 `Get-Command` ，或使用的 **path** 参数 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-306">To find a dynamic parameter, the user must be in the provider path, use the **ArgumentList** parameter of the `Get-Command` cmdlet, or use the **Path** parameter of `Get-Help`.</span></span>

<span data-ttu-id="ab08e-307">若要为函数或脚本创建动态参数，请使用 `DynamicParam` 关键字。</span><span class="sxs-lookup"><span data-stu-id="ab08e-307">To create a dynamic parameter for a function or script, use the `DynamicParam` keyword.</span></span>

<span data-ttu-id="ab08e-308">语法如下：</span><span class="sxs-lookup"><span data-stu-id="ab08e-308">The syntax is as follows:</span></span>

`DynamicParam {<statement-list>}`

<span data-ttu-id="ab08e-309">在语句列表中，使用 `If` 语句指定参数在函数中可用的条件。</span><span class="sxs-lookup"><span data-stu-id="ab08e-309">In the statement list, use an `If` statement to specify the conditions under which the parameter is available in the function.</span></span>

<span data-ttu-id="ab08e-310">使用 `New-Object` cmdlet 创建一个 **RuntimeDefinedParameter** 对象，用于表示参数并指定其名称。</span><span class="sxs-lookup"><span data-stu-id="ab08e-310">Use the `New-Object` cmdlet to create a **System.Management.Automation.RuntimeDefinedParameter** object to represent the parameter and specify its name.</span></span>

<span data-ttu-id="ab08e-311">您可以使用 `New-Object` 命令创建 **ParameterAttribute** 对象来表示参数的属性，例如 **必需** 、 **位置** 或 **ValueFromPipeline** 或其参数集。。</span><span class="sxs-lookup"><span data-stu-id="ab08e-311">You can use a `New-Object` command to create a **System.Management.Automation.ParameterAttribute** object to represent attributes of the parameter, such as **Mandatory** , **Position** , or **ValueFromPipeline** or its parameter set.</span></span>

<span data-ttu-id="ab08e-312">下面的示例演示了一个示例函数，其中包含名为 **Name** 和 **Path** 的标准参数，以及一个名为 **sjc-dp1** 的可选动态参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-312">The following example shows a sample function with standard parameters named **Name** and **Path** , and an optional dynamic parameter named **DP1** .</span></span> <span data-ttu-id="ab08e-313">**Sjc-dp1** 参数在 `PSet1` 参数集中，并且具有类型 `Int32` 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-313">The **DP1** parameter is in the `PSet1` parameter set and has a type of `Int32`.</span></span>
<span data-ttu-id="ab08e-314">**Sjc-dp1** 参数 `Get-Sample` 仅在 **Path** 参数的值以开头时才在函数中提供 `HKLM:` ，指示它正在 `HKEY_LOCAL_MACHINE` 注册表驱动器中使用。</span><span class="sxs-lookup"><span data-stu-id="ab08e-314">The **DP1** parameter is available in the `Get-Sample` function only when the value of the **Path** parameter starts with `HKLM:`, indicating that it's being used in the `HKEY_LOCAL_MACHINE` registry drive.</span></span>

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

<span data-ttu-id="ab08e-315">有关详细信息，请参阅 [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-315">For more information, see [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span></span>

## <a name="switch-parameters"></a><span data-ttu-id="ab08e-316">开关参数</span><span class="sxs-lookup"><span data-stu-id="ab08e-316">Switch parameters</span></span>

<span data-ttu-id="ab08e-317">开关参数是没有参数值的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-317">Switch parameters are parameters with no parameter value.</span></span> <span data-ttu-id="ab08e-318">它们只有在使用时才有效，只具有一个效果。</span><span class="sxs-lookup"><span data-stu-id="ab08e-318">They're effective only when they're used and have only one effect.</span></span>

<span data-ttu-id="ab08e-319">例如， **powershell.exe** 的 **NoProfile** 参数是一个开关参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-319">For example, the **NoProfile** parameter of **powershell.exe** is a switch parameter.</span></span>

<span data-ttu-id="ab08e-320">若要在函数中创建开关参数，请 `Switch` 在参数定义中指定类型。</span><span class="sxs-lookup"><span data-stu-id="ab08e-320">To create a switch parameter in a function, specify the `Switch` type in the parameter definition.</span></span>

<span data-ttu-id="ab08e-321">例如：</span><span class="sxs-lookup"><span data-stu-id="ab08e-321">For example:</span></span>

```powershell
Param([Switch]<ParameterName>)
```

<span data-ttu-id="ab08e-322">或者，您可以使用另一种方法：</span><span class="sxs-lookup"><span data-stu-id="ab08e-322">Or, you can use an another method:</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

<span data-ttu-id="ab08e-323">开关参数易于使用，并且优先于具有更难语法的布尔参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-323">Switch parameters are easy to use and are preferred over Boolean parameters, which have a more difficult syntax.</span></span>

<span data-ttu-id="ab08e-324">例如，若要使用开关参数，用户需要在命令中键入参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-324">For example, to use a switch parameter, the user types the parameter in the command.</span></span>

`-IncludeAll`

<span data-ttu-id="ab08e-325">若要使用布尔参数，用户需要键入参数和布尔值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-325">To use a Boolean parameter, the user types the parameter and a Boolean value.</span></span>

`-IncludeAll:$true`

<span data-ttu-id="ab08e-326">创建开关参数时，请仔细选择参数名称。</span><span class="sxs-lookup"><span data-stu-id="ab08e-326">When creating switch parameters, choose the parameter name carefully.</span></span> <span data-ttu-id="ab08e-327">请确保参数名称将参数的效果传达给用户。</span><span class="sxs-lookup"><span data-stu-id="ab08e-327">Be sure that the parameter name communicates the effect of the parameter to the user.</span></span>
<span data-ttu-id="ab08e-328">避免使用不明确的术语，如 " **筛选器** " 或 " **最大** 值"。</span><span class="sxs-lookup"><span data-stu-id="ab08e-328">Avoid ambiguous terms, such as **Filter** or **Maximum** that might imply a value is required.</span></span>

## <a name="argumentcompleter-attribute"></a><span data-ttu-id="ab08e-329">ArgumentCompleter 特性</span><span class="sxs-lookup"><span data-stu-id="ab08e-329">ArgumentCompleter attribute</span></span>

<span data-ttu-id="ab08e-330">**ArgumentCompleter** 属性允许您向特定参数添加制表符完成值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-330">The **ArgumentCompleter** attribute allows you to add tab completion values to a specific parameter.</span></span> <span data-ttu-id="ab08e-331">必须为需要 tab 自动补全的每个参数定义 **ArgumentCompleter** 属性。</span><span class="sxs-lookup"><span data-stu-id="ab08e-331">An **ArgumentCompleter** attribute must be defined for each parameter that needs tab completion.</span></span> <span data-ttu-id="ab08e-332">类似于 **get-dynamicparameters** ，当用户在参数名称后面按 <kbd>Tab 键</kbd> 时，可用值会在运行时计算。</span><span class="sxs-lookup"><span data-stu-id="ab08e-332">Similar to **DynamicParameters** , the available values are calculated at runtime when the user presses <kbd>Tab</kbd> after the parameter name.</span></span>

<span data-ttu-id="ab08e-333">若要添加 **ArgumentCompleter** 属性，需要定义一个确定值的脚本块。</span><span class="sxs-lookup"><span data-stu-id="ab08e-333">To add an **ArgumentCompleter** attribute, you need to define a script block that determines the values.</span></span> <span data-ttu-id="ab08e-334">脚本块必须按下面指定的顺序采用以下参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-334">The script block must take the following parameters in the order specified below.</span></span> <span data-ttu-id="ab08e-335">参数的名称并不重要，因为按位置提供了这些值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-335">The parameter's names don't matter as the values are provided positionally.</span></span>

<span data-ttu-id="ab08e-336">语法如下：</span><span class="sxs-lookup"><span data-stu-id="ab08e-336">The syntax is as follows:</span></span>

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a><span data-ttu-id="ab08e-337">ArgumentCompleter 脚本块</span><span class="sxs-lookup"><span data-stu-id="ab08e-337">ArgumentCompleter script block</span></span>

<span data-ttu-id="ab08e-338">脚本块参数设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="ab08e-338">The script block parameters are set to the following values:</span></span>

- <span data-ttu-id="ab08e-339">`$commandName` (位置 0) -此参数设置为脚本块为其提供 tab 自动补全的命令的名称。</span><span class="sxs-lookup"><span data-stu-id="ab08e-339">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="ab08e-340">`$parameterName` (位置 1) -此参数设置为其值需要 tab 自动补全的参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-340">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="ab08e-341">`$wordToComplete` (位置 2) -此参数设置为用户在按 <kbd>Tab 键</kbd>之前提供的值。脚本块应使用此值来确定 tab 填写值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-341">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="ab08e-342">`$commandAst` (位置 3) -此参数设置为当前输入行 (AST) 的抽象语法树。</span><span class="sxs-lookup"><span data-stu-id="ab08e-342">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="ab08e-343">有关详细信息，请参阅 [Ast 类](/dotnet/api/system.management.automation.language.ast)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-343">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="ab08e-344">`$fakeBoundParameters` (位置 4) - `$PSBoundParameters` 在用户按 <kbd>Tab</kbd>之前，此参数设置为包含 cmdlet 的的哈希表。有关详细信息，请参阅 [about_Automatic_Variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="ab08e-344">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="ab08e-345">**ArgumentCompleter** 脚本块必须使用管道（例如 `ForEach-Object` 、 `Where-Object` ）或其他合适的方法展开值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-345">The **ArgumentCompleter** script block must unroll the values using the pipeline, such as `ForEach-Object`, `Where-Object`, or another suitable method.</span></span>
<span data-ttu-id="ab08e-346">返回值数组将导致 PowerShell 将整个数组视为 **一个** 制表符完成值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-346">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="ab08e-347">下面的示例将 tab 自动补全添加到 **值** 参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-347">The following example adds tab completion to the **Value** parameter.</span></span> <span data-ttu-id="ab08e-348">如果只指定 **值** 参数，则显示 **值** 的所有可能的值或参数。</span><span class="sxs-lookup"><span data-stu-id="ab08e-348">If only the **Value** parameter is specified, all possible values, or arguments, for **Value** are displayed.</span></span> <span data-ttu-id="ab08e-349">指定 **类型** 参数时， **Value** 参数只显示该类型的可能值。</span><span class="sxs-lookup"><span data-stu-id="ab08e-349">When the **Type** parameter is specified, the **Value** parameter only displays the possible values for that type.</span></span>

<span data-ttu-id="ab08e-350">此外， `-like` 运算符确保如果用户键入以下命令并使用 <kbd>Tab</kbd> 自动补全，则仅返回 **Apple** 。</span><span class="sxs-lookup"><span data-stu-id="ab08e-350">In addition, the `-like` operator ensures that if the user types the following command and uses <kbd>Tab</kbd> completion, only **Apple** is returned.</span></span>

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a><span data-ttu-id="ab08e-351">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab08e-351">See also</span></span>

[<span data-ttu-id="ab08e-352">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="ab08e-352">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="ab08e-353">about_Functions</span><span class="sxs-lookup"><span data-stu-id="ab08e-353">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="ab08e-354">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="ab08e-354">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="ab08e-355">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="ab08e-355">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="ab08e-356">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="ab08e-356">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="ab08e-357">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="ab08e-357">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
