---
ms.date: 09/13/2016
ms.topic: reference
title: ValidatePattern 属性声明
description: ValidatePattern 属性声明
ms.openlocfilehash: 364f63d2c52563eaefe64bcbb2bbae511bccb074
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646166"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="0d58c-103">ValidatePattern 属性声明</span><span class="sxs-lookup"><span data-stu-id="0d58c-103">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="0d58c-104">ValidatePattern 属性指定用于验证 cmdlet 参数的参数的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="0d58c-104">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="0d58c-105">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="0d58c-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="0d58c-106">在 cmdlet 中调用 ValidatePattern 时，Windows PowerShell 运行时将 cmdlet 参数的参数转换为字符串，然后将该字符串与 ValidatePattern 特性提供的模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="0d58c-106">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="0d58c-107">仅当参数的转换字符串表示形式和提供的模式匹配时，才运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d58c-107">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="0d58c-108">如果二者不匹配，则 Windows PowerShell 运行时将引发错误。</span><span class="sxs-lookup"><span data-stu-id="0d58c-108">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d58c-109">语法</span><span class="sxs-lookup"><span data-stu-id="0d58c-109">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="0d58c-110">parameters</span><span class="sxs-lookup"><span data-stu-id="0d58c-110">Parameters</span></span>

<span data-ttu-id="0d58c-111">`RegexString`需要[ () 。](/dotnet/api/System.String)</span><span class="sxs-lookup"><span data-stu-id="0d58c-111">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="0d58c-112">指定用于验证参数参数的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="0d58c-112">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="0d58c-113">选项 ([system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) 可选的命名参数。</span><span class="sxs-lookup"><span data-stu-id="0d58c-113">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="0d58c-114">指定指定正则表达式选项的 [system.text.regularexpressions. system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) 标志的按位组合。</span><span class="sxs-lookup"><span data-stu-id="0d58c-114">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d58c-115">备注</span><span class="sxs-lookup"><span data-stu-id="0d58c-115">Remarks</span></span>

- <span data-ttu-id="0d58c-116">此属性仅可用于每个参数一次。</span><span class="sxs-lookup"><span data-stu-id="0d58c-116">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="0d58c-117">可以使用特性的 `Option` 参数进一步定义模式。</span><span class="sxs-lookup"><span data-stu-id="0d58c-117">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="0d58c-118">例如，可以使模式区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0d58c-118">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="0d58c-119">如果将此特性应用于集合，则集合中的每个元素都必须与模式匹配。</span><span class="sxs-lookup"><span data-stu-id="0d58c-119">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="0d58c-120">ValidatePattern 特性是由 [Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) 类定义的。</span><span class="sxs-lookup"><span data-stu-id="0d58c-120">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d58c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d58c-121">See Also</span></span>

[<span data-ttu-id="0d58c-122">System.web. Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="0d58c-122">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="0d58c-123">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d58c-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
