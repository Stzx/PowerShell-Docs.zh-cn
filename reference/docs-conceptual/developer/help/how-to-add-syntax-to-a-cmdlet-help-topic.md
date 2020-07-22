---
title: 如何向 Cmdlet 帮助主题添加语法
ms.date: 09/12/2016
ms.openlocfilehash: 3457341a577b283bf3da5dc010de9bbbb36b78d2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893044"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="870f3-102">如何向 Cmdlet 帮助主题添加语法</span><span class="sxs-lookup"><span data-stu-id="870f3-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="870f3-103">在开始编写 cmdlet 帮助文件中语法关系图的 XML 代码之前，请阅读此部分以清楚地了解你需要提供的数据类型，如参数特性，以及如何在语法关系图中显示这些数据。</span><span class="sxs-lookup"><span data-stu-id="870f3-103">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="870f3-104">参数属性</span><span class="sxs-lookup"><span data-stu-id="870f3-104">Parameter Attributes</span></span>

- <span data-ttu-id="870f3-105">必需</span><span class="sxs-lookup"><span data-stu-id="870f3-105">Required</span></span>
  - <span data-ttu-id="870f3-106">如果为 true，则参数必须出现在所有使用参数集的命令中。</span><span class="sxs-lookup"><span data-stu-id="870f3-106">If true, the parameter must appear in all commands that use the parameter set.</span></span>
  - <span data-ttu-id="870f3-107">如果为 false，则参数在所有使用参数集的命令中是可选的。</span><span class="sxs-lookup"><span data-stu-id="870f3-107">If false, the parameter is optional in all commands that use the parameter set.</span></span>
- <span data-ttu-id="870f3-108">位置</span><span class="sxs-lookup"><span data-stu-id="870f3-108">Position</span></span>
  - <span data-ttu-id="870f3-109">如果已命名，则参数名称是必需的。</span><span class="sxs-lookup"><span data-stu-id="870f3-109">If named, the parameter name is required.</span></span>
  - <span data-ttu-id="870f3-110">如果是位置，则参数名称是可选的。</span><span class="sxs-lookup"><span data-stu-id="870f3-110">If positional, the parameter name is optional.</span></span> <span data-ttu-id="870f3-111">如果省略此参数，则参数值必须在命令中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="870f3-111">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="870f3-112">例如，如果值为 position = "1"，则参数值必须是命令中的第一个或唯一一个未命名的参数值。</span><span class="sxs-lookup"><span data-stu-id="870f3-112">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>
- <span data-ttu-id="870f3-113">管道输入</span><span class="sxs-lookup"><span data-stu-id="870f3-113">Pipeline Input</span></span>
  - <span data-ttu-id="870f3-114">如果为 true （ByValue），则可以通过管道将输入传递给参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-114">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="870f3-115">即使属性名称和对象类型与预期类型不匹配，输入也与（"绑定到"）参数相关联。</span><span class="sxs-lookup"><span data-stu-id="870f3-115">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span>
    <span data-ttu-id="870f3-116">PowerShell 参数绑定组件尝试将输入转换为正确的类型，并且仅当无法转换该类型时才会导致命令失败。</span><span class="sxs-lookup"><span data-stu-id="870f3-116">The PowerShell parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="870f3-117">参数集中只能有一个参数可以通过值来关联。</span><span class="sxs-lookup"><span data-stu-id="870f3-117">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="870f3-118">如果为 true （ByPropertyName），则可以通过管道将输入传递给参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-118">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="870f3-119">但是，仅当参数名称与输入对象的属性的名称匹配时，输入才与参数相关联。</span><span class="sxs-lookup"><span data-stu-id="870f3-119">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="870f3-120">例如，如果参数名称为，则 `Path` 仅当对象具有名为 path 的属性时，才与该参数关联的对象将与该参数相关联。</span><span class="sxs-lookup"><span data-stu-id="870f3-120">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>
  - <span data-ttu-id="870f3-121">如果为 true （ByValue，ByPropertyName），则可以通过属性名称或值通过管道将输入传递给参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-121">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="870f3-122">参数集中只能有一个参数可以通过值来关联。</span><span class="sxs-lookup"><span data-stu-id="870f3-122">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="870f3-123">如果为 false，则不能通过管道将输入传递给此参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-123">If false, you cannot pipe input to this parameter.</span></span>
- <span data-ttu-id="870f3-124">通配</span><span class="sxs-lookup"><span data-stu-id="870f3-124">Globbing</span></span>
  - <span data-ttu-id="870f3-125">如果为 true，则用户键入的参数值文本可以包含通配符。</span><span class="sxs-lookup"><span data-stu-id="870f3-125">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>
  - <span data-ttu-id="870f3-126">如果为 false，则用户为参数值键入的文本不能包含通配符。</span><span class="sxs-lookup"><span data-stu-id="870f3-126">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="870f3-127">参数值特性</span><span class="sxs-lookup"><span data-stu-id="870f3-127">Parameter Value Attributes</span></span>

- <span data-ttu-id="870f3-128">必需</span><span class="sxs-lookup"><span data-stu-id="870f3-128">Required</span></span>
  - <span data-ttu-id="870f3-129">如果为 true，则只要在命令中使用参数，就必须使用指定的值。</span><span class="sxs-lookup"><span data-stu-id="870f3-129">If true, the specified value must be used whenever using the parameter in a command.</span></span>
  - <span data-ttu-id="870f3-130">如果为 false，则参数值是可选的。</span><span class="sxs-lookup"><span data-stu-id="870f3-130">If false, the parameter value is optional.</span></span> <span data-ttu-id="870f3-131">通常，仅当值为参数的多个有效值之一（如枚举类型中的值）时，此值才是可选的。</span><span class="sxs-lookup"><span data-stu-id="870f3-131">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="870f3-132">参数值的**必需**特性与参数的**必需**特性不同。</span><span class="sxs-lookup"><span data-stu-id="870f3-132">The **Required** attribute of a parameter value is different from the **Required** attribute of a parameter.</span></span>

<span data-ttu-id="870f3-133">参数的必需特性指示在调用 cmdlet 时是否必须包含参数（及其值）。</span><span class="sxs-lookup"><span data-stu-id="870f3-133">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="870f3-134">相反，仅当参数包含在命令中时，才使用参数值的必需特性。</span><span class="sxs-lookup"><span data-stu-id="870f3-134">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="870f3-135">它指示特定值是否必须与参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="870f3-135">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="870f3-136">通常，作为占位符的参数值是必需的，参数值不是必需的，因为它们是可能与参数一起使用的几个值中的一个。</span><span class="sxs-lookup"><span data-stu-id="870f3-136">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="870f3-137">正在收集语法信息</span><span class="sxs-lookup"><span data-stu-id="870f3-137">Gathering Syntax Information</span></span>

1. <span data-ttu-id="870f3-138">以 cmdlet 名称开头。</span><span class="sxs-lookup"><span data-stu-id="870f3-138">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

1. <span data-ttu-id="870f3-139">列出 cmdlet 的所有参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-139">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="870f3-140">`-`在每个参数名称前键入连字符（）（ASCII 45）。</span><span class="sxs-lookup"><span data-stu-id="870f3-140">Type a hyphen (`-`) (ASCII 45) before each parameter name.</span></span>
   <span data-ttu-id="870f3-141">将参数分为多个参数集（某些 cmdlet 只能设置一个参数）。</span><span class="sxs-lookup"><span data-stu-id="870f3-141">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="870f3-142">在此示例中，"Get-help" cmdlet 具有两个参数集。</span><span class="sxs-lookup"><span data-stu-id="870f3-142">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="870f3-143">用 cmdlet 名称启动每个参数集。</span><span class="sxs-lookup"><span data-stu-id="870f3-143">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="870f3-144">首先列出默认参数集。</span><span class="sxs-lookup"><span data-stu-id="870f3-144">List the default parameter set first.</span></span> <span data-ttu-id="870f3-145">默认参数是由 cmdlet 类指定的。</span><span class="sxs-lookup"><span data-stu-id="870f3-145">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="870f3-146">对于每个参数集，请首先列出其唯一参数，除非存在必须首先出现的位置参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-146">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="870f3-147">在上面的示例中，Name 和 ID 参数是这两个参数集的唯一参数（每个参数集必须有一个参数集独有的参数）。</span><span class="sxs-lookup"><span data-stu-id="870f3-147">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="870f3-148">这样，用户就可以更轻松地标识他们需要为参数集提供哪些参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-148">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="870f3-149">按它们应出现在命令中的顺序列出参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-149">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="870f3-150">如果顺序不重要，请将相关参数一起列出，或首先列出最常用的参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-150">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="870f3-151">如果 cmdlet 支持 ShouldProcess，请务必列出 WhatIf 和 Confirm 参数。</span><span class="sxs-lookup"><span data-stu-id="870f3-151">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="870f3-152">不要在语法关系图中列出常见参数（例如 Verbose、Debug 和 ErrorAction）。</span><span class="sxs-lookup"><span data-stu-id="870f3-152">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="870f3-153">`Get-Help`Cmdlet 在显示帮助主题时会为你添加该信息。</span><span class="sxs-lookup"><span data-stu-id="870f3-153">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

1. <span data-ttu-id="870f3-154">添加参数值。</span><span class="sxs-lookup"><span data-stu-id="870f3-154">Add the parameter values.</span></span> <span data-ttu-id="870f3-155">在 PowerShell 中，参数值按其 .NET 类型表示。</span><span class="sxs-lookup"><span data-stu-id="870f3-155">In PowerShell, parameter values are represented by their .NET type.</span></span>
   <span data-ttu-id="870f3-156">但是，类型名称可以缩写，如 system.string 的 "string"。</span><span class="sxs-lookup"><span data-stu-id="870f3-156">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="870f3-157">缩写**类型的含义**清楚，如**system.string 的字符串**和**system.object**的**int** 。</span><span class="sxs-lookup"><span data-stu-id="870f3-157">Abbreviate types as long as their meaning is clear, such as **string** for **System.String** and **int** for **System.Int32**.</span></span>

   <span data-ttu-id="870f3-158">列出枚举的所有值，如 `-type` 上一个示例中的参数，可以设置为 "**基本**" 或 "**高级**"。</span><span class="sxs-lookup"><span data-stu-id="870f3-158">List all values of enumerations, such as the `-type` parameter in the previous example, which can be set to **basic** or **advanced**.</span></span>

   <span data-ttu-id="870f3-159">开关参数（如 `-list` 前面的示例中的）没有值。</span><span class="sxs-lookup"><span data-stu-id="870f3-159">Switch parameters, such as `-list` in the previous example, do not have values.</span></span>

1. <span data-ttu-id="870f3-160">与作为文本的参数值相比，将尖括号添加到作为占位符的参数值。</span><span class="sxs-lookup"><span data-stu-id="870f3-160">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

1. <span data-ttu-id="870f3-161">将可选参数及其工位括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="870f3-161">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="870f3-162">将可选参数名称（用于位置参数）括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="870f3-162">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="870f3-163">位置的参数的名称（例如以下示例中的 Name 参数）不必包含在命令中。</span><span class="sxs-lookup"><span data-stu-id="870f3-163">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="870f3-164">如果参数值可以包含多个值，如 Name 参数中的名称列表，请在参数值之后直接添加一对方括号。</span><span class="sxs-lookup"><span data-stu-id="870f3-164">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="870f3-165">如果用户可以从参数或参数值（如类型参数）中进行选择，请将这些选项括在大括号中，并将它们与 xor 或符号（;) 分隔开。</span><span class="sxs-lookup"><span data-stu-id="870f3-165">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

1. <span data-ttu-id="870f3-166">如果参数值必须使用特定的格式设置，如引号或括号，则在语法中显示格式。</span><span class="sxs-lookup"><span data-stu-id="870f3-166">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="870f3-167">编码语法关系图 XML</span><span class="sxs-lookup"><span data-stu-id="870f3-167">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="870f3-168">XML 的语法节点紧跟在说明节点之后，后者以 `</maml:description>` 标记结尾。</span><span class="sxs-lookup"><span data-stu-id="870f3-168">The syntax node of the XML begins immediately after the description node, which ends with the `</maml:description>` tag.</span></span> <span data-ttu-id="870f3-169">有关收集语法关系图中使用的数据的信息，请参阅[收集语法信息](#gathering-syntax-information)。</span><span class="sxs-lookup"><span data-stu-id="870f3-169">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="870f3-170">添加语法节点</span><span class="sxs-lookup"><span data-stu-id="870f3-170">Adding a Syntax Node</span></span>

<span data-ttu-id="870f3-171">Cmdlet 帮助主题中显示的语法关系图是从 XML 语法节点中的数据生成的。</span><span class="sxs-lookup"><span data-stu-id="870f3-171">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="870f3-172">如果标记，则语法节点包含在对中 `<command:syntax>` 。</span><span class="sxs-lookup"><span data-stu-id="870f3-172">The syntax node is enclosed in a pair if `<command:syntax>` tags.</span></span> <span data-ttu-id="870f3-173">将 cmdlet 的每个参数集用一对标记括起来 `<command:syntaxitem>` 。</span><span class="sxs-lookup"><span data-stu-id="870f3-173">With each parameter set of the cmdlet enclosed in a pair of `<command:syntaxitem>` tags.</span></span> <span data-ttu-id="870f3-174">可以添加的标记数没有限制 `<command:syntaxitem>` 。</span><span class="sxs-lookup"><span data-stu-id="870f3-174">There is no limit to the number of `<command:syntaxitem>` tags that you can add.</span></span>

<span data-ttu-id="870f3-175">下面的示例演示一个语法节点，该节点具有两个参数集的语法项节点。</span><span class="sxs-lookup"><span data-stu-id="870f3-175">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    ...
    <!--Parameter Set 1 (default parameter set) parameters go here-->
    ...
  </command:syntaxItem>
  <command:syntaxItem>
    ...
    <!--Parameter Set 2 parameters go here-->
    ...
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="870f3-176">将 Cmdlet 名称添加到参数集数据</span><span class="sxs-lookup"><span data-stu-id="870f3-176">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="870f3-177">Cmdlet 的每个参数集是在语法项节点中指定的。</span><span class="sxs-lookup"><span data-stu-id="870f3-177">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="870f3-178">每个语法项节点都以一对 `<maml:name>` 标记开头，其中包括 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="870f3-178">Each syntax item node begins with a pair of `<maml:name>` tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="870f3-179">下面的示例包含一个语法节点，该节点具有两个参数集的语法项节点。</span><span class="sxs-lookup"><span data-stu-id="870f3-179">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-parameters"></a><span data-ttu-id="870f3-180">添加参数</span><span class="sxs-lookup"><span data-stu-id="870f3-180">Adding Parameters</span></span>

<span data-ttu-id="870f3-181">添加到语法项节点的每个参数都是在一对标记中指定的 `<command:parameter>` 。</span><span class="sxs-lookup"><span data-stu-id="870f3-181">Each parameter added to the syntax item node is specified within a pair of `<command:parameter>` tags.</span></span> <span data-ttu-id="870f3-182">`<command:parameter>`对于参数集中包含的每个参数都需要一对标记，而 PowerShell 提供的通用参数除外。</span><span class="sxs-lookup"><span data-stu-id="870f3-182">You need a pair of `<command:parameter>` tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by PowerShell.</span></span>

<span data-ttu-id="870f3-183">开始标记的属性 `<command:parameter>` 决定了参数在语法关系图中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="870f3-183">The attributes of the opening `<command:parameter>` tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="870f3-184">有关参数属性的信息，请参阅[参数特性](#parameter-attributes)。</span><span class="sxs-lookup"><span data-stu-id="870f3-184">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="870f3-185">`<command:parameter>`标记支持 `<maml:description>` 其内容从未显示的子元素。</span><span class="sxs-lookup"><span data-stu-id="870f3-185">The `<command:parameter>` tag supports a child element `<maml:description>` whose content is never displayed.</span></span> <span data-ttu-id="870f3-186">在 XML 的参数节点中指定参数说明。</span><span class="sxs-lookup"><span data-stu-id="870f3-186">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="870f3-187">若要避免语法项预兆中的信息与参数节点中的信息不一致，请省略（ `<maml:description>` 或将其留空。</span><span class="sxs-lookup"><span data-stu-id="870f3-187">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (`<maml:description>` or leave it empty.</span></span>

<span data-ttu-id="870f3-188">下面的示例包含具有两个参数的参数集的语法项节点。</span><span class="sxs-lookup"><span data-stu-id="870f3-188">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

```xml
<command:syntaxItem>
  <maml:name>Cmdlet-Name</maml:name>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByValue)" position="1">
    <maml:name>ParameterName1</maml:name>
    <command:parameterValue required="true">
      string[]
    </command:parameterValue>
  </command:parameter>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByPropertyName)">
    <maml:name>ParameterName2</maml:name>
    <command:parameterValue required="true">
      int32[]
    </command:parameterValue>
  </command:parameter>
</command:syntaxItem>
```
