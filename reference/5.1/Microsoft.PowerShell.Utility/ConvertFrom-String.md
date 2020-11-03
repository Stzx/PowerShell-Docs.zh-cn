---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "93199379"
---
# <span data-ttu-id="cf9a5-103">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="cf9a5-103">ConvertFrom-String</span></span>

## <span data-ttu-id="cf9a5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="cf9a5-104">SYNOPSIS</span></span>
<span data-ttu-id="cf9a5-105">从字符串内容中提取并分析结构化对象。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-105">Extracts and parses structured properties from string content.</span></span>

## <span data-ttu-id="cf9a5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cf9a5-106">SYNTAX</span></span>

### <span data-ttu-id="cf9a5-107">ByDelimiter（默认值）</span><span class="sxs-lookup"><span data-stu-id="cf9a5-107">ByDelimiter (Default)</span></span>

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="cf9a5-108">TemplateParsing</span><span class="sxs-lookup"><span data-stu-id="cf9a5-108">TemplateParsing</span></span>

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="cf9a5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cf9a5-109">DESCRIPTION</span></span>

<span data-ttu-id="cf9a5-110">**ConvertFrom-String** cmdlet 提取并分析字符串内容中的结构化属性。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-110">The **ConvertFrom-String** cmdlet extracts and parses structured properties from string content.</span></span>
<span data-ttu-id="cf9a5-111">此 cmdlet 通过分析传统文本流中的文本，生成对象。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-111">This cmdlet generates an object by parsing text from a traditional text stream.</span></span>
<span data-ttu-id="cf9a5-112">对于管道中的每个字符串，该 cmdlet 通过分隔符或分析表达式拆分输入，然后将属性名称分配给每个由此得到的拆分元素。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-112">For each string in the pipeline, the cmdlet splits the input by either a delimiter or a parse expression, and then assigns property names to each of the resulting split elements.</span></span>
<span data-ttu-id="cf9a5-113">可提供这些属性名称；如果不提供，它们将自动生成。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-113">You can provide these property names; if you do not, they are automatically generated for you.</span></span>

<span data-ttu-id="cf9a5-114">该 cmdlet 的默认参数集 **ByDelimiter** 严格通过正则表达式分隔符进行拆分。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-114">The cmdlet's default parameter set, **ByDelimiter** , splits exactly on the regular expression delimiter.</span></span>
<span data-ttu-id="cf9a5-115">与 cmdlet 一样，它不执行引号匹配或分隔符转义 `Import-Csv` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-115">It does not perform quote matching or delimiter escaping as the `Import-Csv` cmdlet does.</span></span>

<span data-ttu-id="cf9a5-116">该 cmdlet 的可选参数集 TemplateParsing  从正则表达式捕获的组中生成元素。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-116">The cmdlet's alternate parameter set, **TemplateParsing** , generates elements from the groups that are captured by a regular expression.</span></span> <span data-ttu-id="cf9a5-117">有关正则表达式的详细信息，请参阅 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-117">For more information on regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

<span data-ttu-id="cf9a5-118">此 cmdlet 支持两种模式：基本分隔分析和自动生成的示例驱动的分析。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-118">This cmdlet supports two modes: basic delimited parsing, and automatically-generated, example-driven parsing.</span></span>

<span data-ttu-id="cf9a5-119">默认情况下，分隔分析会在空格处将输入拆分，并为得到的组分配属性名称。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-119">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="cf9a5-120">可以通过将结果通过管道传递 `ConvertFrom-String` 到其中一个 cmdlet 来自定义分隔符 `Format-*` ，也可以使用 **分隔符** 参数。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-120">You can customize the delimiter by piping the `ConvertFrom-String` results into one of the `Format-*` cmdlets, or you can use the **Delimiter** parameter.</span></span>

<span data-ttu-id="cf9a5-121">该 cmdlet 还支持 [Microsoft Research 的 FlashExtract 研究工作](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/)的自动生成的示例驱动的分析。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-121">The cmdlet also supports automatically-generated, example-driven parsing based on the [FlashExtract, research work by Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span></span>

## <span data-ttu-id="cf9a5-122">示例</span><span class="sxs-lookup"><span data-stu-id="cf9a5-122">EXAMPLES</span></span>

### <span data-ttu-id="cf9a5-123">示例 1：生成具有默认属性名称的对象</span><span class="sxs-lookup"><span data-stu-id="cf9a5-123">Example 1: Generate an object with default property names</span></span>

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

<span data-ttu-id="cf9a5-124">此命令将生成具有默认属性名称 **P1** 和 **P2** 的对象。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-124">This command generates an object with default property names, **P1** and **P2** .</span></span>

### <span data-ttu-id="cf9a5-125">示例 1A：了解生成对象</span><span class="sxs-lookup"><span data-stu-id="cf9a5-125">Example 1A: Get to know the generated object</span></span>

<span data-ttu-id="cf9a5-126">此命令生成一个对象，属性为 **P1** ， **P2** ;默认情况下，这两个属性均为 **字符串** 类型。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-126">This command generates one object with properties **P1** , **P2** ; both properties are of **String** type, by default.</span></span>

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### <span data-ttu-id="cf9a5-127">示例 2：使用分隔符生成具有默认属性名称的对象</span><span class="sxs-lookup"><span data-stu-id="cf9a5-127">Example 2: Generate an object with default property names using a delimiter</span></span>

<span data-ttu-id="cf9a5-128">此命令使用反斜杠 () 作为分隔符，生成包含域和用户名的对象 `\` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-128">This command generates an object with a domain and username using the backslash (`\`) as the delimiter.</span></span> <span data-ttu-id="cf9a5-129">使用正则表达式时，反斜杠字符必须使用另一个反斜杠进行转义。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-129">The backslash character must be escaped with another backslash when using regular expressions.</span></span>

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### <span data-ttu-id="cf9a5-130">示例 3：生成包含两个命名属性的对象</span><span class="sxs-lookup"><span data-stu-id="cf9a5-130">Example 3: Generate an object that contains two named properties</span></span>

<span data-ttu-id="cf9a5-131">下面的示例从 Windows hosts 文件项创建对象。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-131">The following example creates objects from Windows hosts file entries.</span></span>

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

<span data-ttu-id="cf9a5-132">`Get-Content`Cmdlet 将 Windows hosts 文件的内容存储在中 `$content` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-132">The `Get-Content` cmdlet stores the content of a Windows hosts file in `$content`.</span></span> <span data-ttu-id="cf9a5-133">第二个命令使用与不以 () 开头的任何行匹配的正则表达式删除 hosts 文件开头的所有注释 `#` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-133">The second command removes any comments at the beginning of the hosts file using a regular expression that matches any line that does not start with (`#`).</span></span> <span data-ttu-id="cf9a5-134">最后一个命令将剩余文本转换为具有 **服务器** 和 **IP** 属性的对象。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-134">The last command converts the remaining text into objects with **Server** and **IP** properties.</span></span>

### <span data-ttu-id="cf9a5-135">示例 4：将表达式用作 TemplateContent 参数的值，将结果保存到变量中。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-135">Example 4: Use an expression as the value of the TemplateContent parameter, save the results in a variable.</span></span>

<span data-ttu-id="cf9a5-136">此命令将表达式用作 TemplateContent  参数的值。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-136">This command uses an expression as the value of the **TemplateContent** parameter.</span></span>
<span data-ttu-id="cf9a5-137">为简单起见，表达式保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-137">The expression is saved in a variable for simplicity.</span></span>
<span data-ttu-id="cf9a5-138">Windows PowerShell 现在知道，管道上用于的字符串 `ConvertFrom-String` 具有三个属性：</span><span class="sxs-lookup"><span data-stu-id="cf9a5-138">Windows PowerShell understands now that the string that is used on the pipeline to `ConvertFrom-String` has three properties:</span></span>

- <span data-ttu-id="cf9a5-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf9a5-139">**Name**</span></span>
- <span data-ttu-id="cf9a5-140">**phone**</span><span class="sxs-lookup"><span data-stu-id="cf9a5-140">**phone**</span></span>
- <span data-ttu-id="cf9a5-141">**年**</span><span class="sxs-lookup"><span data-stu-id="cf9a5-141">**age**</span></span>

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

<span data-ttu-id="cf9a5-142">输入中的每一行都按样本匹配项进行计算。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-142">Each line in the input is evaluated by the sample matches.</span></span> <span data-ttu-id="cf9a5-143">如果行与模式中给定的示例匹配，则提取值并将其传递给输出变量。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-143">If the line matches the examples given in the pattern, values are extracted and passed to the output variable.</span></span>

<span data-ttu-id="cf9a5-144">示例数据 `$template` 提供了两种不同的电话格式：</span><span class="sxs-lookup"><span data-stu-id="cf9a5-144">The sample data, `$template`, provides two different phone formats:</span></span>

- `425-123-6789`
- `(206) 987-4321`

<span data-ttu-id="cf9a5-145">示例数据还提供了两种不同的 age 格式：</span><span class="sxs-lookup"><span data-stu-id="cf9a5-145">The sample data also provides two different age formats:</span></span>

- `6`
- `12`

<span data-ttu-id="cf9a5-146">这意味着将无法识别像这样的手机 `(206) 987 4321` ，因为没有与该模式匹配的示例数据，因为没有连字符。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-146">This implies that phones like `(206) 987 4321` will not be recognized, because there's no sample data that matches that pattern because there are no hyphens.</span></span>

### <span data-ttu-id="cf9a5-147">示例 5：为生成的属性指定数据类型</span><span class="sxs-lookup"><span data-stu-id="cf9a5-147">Example 5: Specifying data types to the generated properties</span></span>

<span data-ttu-id="cf9a5-148">此示例与上面的示例4相同。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-148">This is the same example as Example 4, above.</span></span>
<span data-ttu-id="cf9a5-149">不同之处在于模式字符串包含每个所需属性的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-149">The difference is that the pattern string includes a data type for each desired property.</span></span>

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

<span data-ttu-id="cf9a5-150">`Get-Member`Cmdlet 用于显示 **age** 属性为整数。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-150">The `Get-Member` cmdlet is used to show that the **age** property is an integer.</span></span>

## <span data-ttu-id="cf9a5-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cf9a5-151">PARAMETERS</span></span>

### <span data-ttu-id="cf9a5-152">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="cf9a5-152">-Delimiter</span></span>

<span data-ttu-id="cf9a5-153">指定用于标识元素之间边界的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-153">Specifies a regular expression that identifies the boundary between elements.</span></span>
<span data-ttu-id="cf9a5-154">通过拆分创建的元素将成为生成的对象中的属性。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-154">Elements that are created by the split become properties in the resulting object.</span></span>
<span data-ttu-id="cf9a5-155">在对类型的 **Split** 方法的调用中，将最终使用分隔符 `[System.Text.RegularExpressions.RegularExpression]` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-155">The delimiter is ultimately used in a call to the **Split** method of the type `[System.Text.RegularExpressions.RegularExpression]`.</span></span>

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-156">-IncludeExtent</span><span class="sxs-lookup"><span data-stu-id="cf9a5-156">-IncludeExtent</span></span>

<span data-ttu-id="cf9a5-157">指示此 cmdlet 包括默认删除的扩展文本属性。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-157">Indicates that this cmdlet includes an extent text property that is removed by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-158">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cf9a5-158">-InputObject</span></span>

<span data-ttu-id="cf9a5-159">指定从管道接收到的字符串，或包含字符串对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-159">Specifies strings received from the pipeline, or a variable that contains a string object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-160">-PropertyNames</span><span class="sxs-lookup"><span data-stu-id="cf9a5-160">-PropertyNames</span></span>

<span data-ttu-id="cf9a5-161">指定要向其分配生成对象中的拆分值的属性名称数组。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-161">Specifies an array of property names to which to assign split values in the resulting object.</span></span>
<span data-ttu-id="cf9a5-162">拆分或分析的每个文本行将生成表示属性值的元素。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-162">Every line of text that you split or parse generates elements that represent property values.</span></span>
<span data-ttu-id="cf9a5-163">如果该元素是捕获组的结果，并且该捕获组命名为 (例如 `(?<name>)` 或 `(?'name')` ) ，则该捕获组的名称将分配给该属性。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-163">If the element is the result of a capture group, and that capture group is named (for example, `(?<name>)` or `(?'name')` ), then the name of that capture group is assigned to the property.</span></span>

<span data-ttu-id="cf9a5-164">如果提供 PropertyName  数组中的任何元素，则这些名称将分配给尚未命名的属性。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-164">If you provide any elements in the **PropertyName** array, those names are assigned to properties that have not yet been named.</span></span>

<span data-ttu-id="cf9a5-165">如果提供的属性名称比字段多，则 PowerShell 将忽略额外的属性名称。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-165">If you provide more property names than there are fields, PowerShell ignores the extra property names.</span></span> <span data-ttu-id="cf9a5-166">如果未指定足够的属性名称来命名所有字段，则 PowerShell 会自动将数值属性名称分配给任何未命名的属性： **P1** 、 **P2** 等。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-166">If you do not specify enough property names to name all fields, PowerShell automatically assigns numerical property names to any properties that are not named: **P1** , **P2** , etc.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-167">-TemplateContent</span><span class="sxs-lookup"><span data-stu-id="cf9a5-167">-TemplateContent</span></span>

<span data-ttu-id="cf9a5-168">指定一个表达式，或一个保存为变量的表达式，用于描述此 cmdlet 会将字符串分配到的属性。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-168">Specifies an expression, or an expression saved as a variable, that describes the properties to which this cmdlet assigns strings.</span></span> <span data-ttu-id="cf9a5-169">模板字段规范的语法如下所示： `{[optional-typecast]<name>:<example-value>}` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-169">The syntax of a template field specification is the following: `{[optional-typecast]<name>:<example-value>}`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-170">-TemplateFile</span><span class="sxs-lookup"><span data-stu-id="cf9a5-170">-TemplateFile</span></span>

<span data-ttu-id="cf9a5-171">将文件指定为数组，包含所需的字符串分析的模板。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-171">Specifies a file, as an array, that contains a template for the desired parsing of the string.</span></span>
<span data-ttu-id="cf9a5-172">在模板文件中，属性及其值括在括号中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-172">In the template file, properties and their values are enclosed in brackets, as shown below.</span></span>
<span data-ttu-id="cf9a5-173">如果多次显示某个属性（如 **Name** 属性及其关联的其他属性），则可以添加一个星号 (`*`) ，以指示这会导致多个记录。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-173">If a property, such as the **Name** property and its associated other properties, appears multiple times, you can add an asterisk (`*`) to indicate that this results in multiple records.</span></span> <span data-ttu-id="cf9a5-174">这样可避免将多个属性提取到单个记录中。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-174">This avoids extracting multiple properties into a single record.</span></span>

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-175">-UpdateTemplate</span><span class="sxs-lookup"><span data-stu-id="cf9a5-175">-UpdateTemplate</span></span>

<span data-ttu-id="cf9a5-176">指示此 cmdlet 将学习算法的结果保存到模板文件中的注释内。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-176">Indicates that this cmdlet saves the results of a learning algorithm into a comment in the template file.</span></span>
<span data-ttu-id="cf9a5-177">这可加快算法学习过程的速度。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-177">This makes the algorithm learning process faster.</span></span>
<span data-ttu-id="cf9a5-178">若要使用此参数，还必须指定具有 TemplateFile  参数的模板文件。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-178">To use this parameter, you must also specify a template file with the **TemplateFile** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cf9a5-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cf9a5-179">CommonParameters</span></span>

<span data-ttu-id="cf9a5-180">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-180">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="cf9a5-181">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="cf9a5-181">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="cf9a5-182">输入</span><span class="sxs-lookup"><span data-stu-id="cf9a5-182">INPUTS</span></span>

### <span data-ttu-id="cf9a5-183">System.String</span><span class="sxs-lookup"><span data-stu-id="cf9a5-183">System.String</span></span>

## <span data-ttu-id="cf9a5-184">输出</span><span class="sxs-lookup"><span data-stu-id="cf9a5-184">OUTPUTS</span></span>

## <span data-ttu-id="cf9a5-185">注释</span><span class="sxs-lookup"><span data-stu-id="cf9a5-185">NOTES</span></span>

## <span data-ttu-id="cf9a5-186">相关链接</span><span class="sxs-lookup"><span data-stu-id="cf9a5-186">RELATED LINKS</span></span>

<span data-ttu-id="cf9a5-187">[ConvertFrom-String: Example-based text parsing](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)（ConvertFrom-String：基于示例的文本分析）</span><span class="sxs-lookup"><span data-stu-id="cf9a5-187">[ConvertFrom-String: Example-based text parsing](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)</span></span>

[<span data-ttu-id="cf9a5-188">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="cf9a5-188">ConvertFrom-StringData</span></span>](ConvertFrom-StringData.md)

[<span data-ttu-id="cf9a5-189">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="cf9a5-189">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="cf9a5-190">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="cf9a5-190">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
