---
title: ValidatePattern 特性声明 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787795"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="7bc63-102">ValidatePattern 属性声明</span><span class="sxs-lookup"><span data-stu-id="7bc63-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="7bc63-103">ValidatePattern 属性指定用于验证 cmdlet 参数的参数的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="7bc63-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="7bc63-104">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="7bc63-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="7bc63-105">在 cmdlet 中调用 ValidatePattern 时，Windows PowerShell 运行时将 cmdlet 参数的参数转换为字符串，然后将该字符串与 ValidatePattern 特性提供的模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="7bc63-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="7bc63-106">仅当参数的转换字符串表示形式和提供的模式匹配时，才运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7bc63-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="7bc63-107">如果二者不匹配，则 Windows PowerShell 运行时将引发错误。</span><span class="sxs-lookup"><span data-stu-id="7bc63-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="7bc63-108">语法</span><span class="sxs-lookup"><span data-stu-id="7bc63-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="7bc63-109">parameters</span><span class="sxs-lookup"><span data-stu-id="7bc63-109">Parameters</span></span>

<span data-ttu-id="7bc63-110">`RegexString`需要[ () 。](/dotnet/api/System.String)</span><span class="sxs-lookup"><span data-stu-id="7bc63-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="7bc63-111">指定用于验证参数参数的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="7bc63-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="7bc63-112">选项 ([system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) 可选的命名参数。</span><span class="sxs-lookup"><span data-stu-id="7bc63-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="7bc63-113">指定指定正则表达式选项的[system.text.regularexpressions. system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)标志的按位组合。</span><span class="sxs-lookup"><span data-stu-id="7bc63-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bc63-114">备注</span><span class="sxs-lookup"><span data-stu-id="7bc63-114">Remarks</span></span>

- <span data-ttu-id="7bc63-115">此属性仅可用于每个参数一次。</span><span class="sxs-lookup"><span data-stu-id="7bc63-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="7bc63-116">可以使用特性的 `Option` 参数进一步定义模式。</span><span class="sxs-lookup"><span data-stu-id="7bc63-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="7bc63-117">例如，可以使模式区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7bc63-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="7bc63-118">如果将此特性应用于集合，则集合中的每个元素都必须与模式匹配。</span><span class="sxs-lookup"><span data-stu-id="7bc63-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="7bc63-119">ValidatePattern 特性是由[Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)类定义的。</span><span class="sxs-lookup"><span data-stu-id="7bc63-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bc63-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bc63-120">See Also</span></span>

[<span data-ttu-id="7bc63-121">System.web. Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="7bc63-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="7bc63-122">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7bc63-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
