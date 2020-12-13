---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateSet 属性声明
description: ValidateSet 属性声明
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660471"
---
# <a name="validateset-attribute-declaration"></a><span data-ttu-id="c188a-103">ValidateSet 属性声明</span><span class="sxs-lookup"><span data-stu-id="c188a-103">ValidateSet Attribute Declaration</span></span>

<span data-ttu-id="c188a-104">ValidateSetAttribute 属性为 cmdlet 参数参数指定一组可能的值。</span><span class="sxs-lookup"><span data-stu-id="c188a-104">The ValidateSetAttribute attribute specifies a set of possible values for a cmdlet parameter argument.</span></span> <span data-ttu-id="c188a-105">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="c188a-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="c188a-106">如果指定此属性，则 Windows PowerShell 运行时将确定 cmdlet 参数的提供参数是否与提供的元素集中的元素匹配。</span><span class="sxs-lookup"><span data-stu-id="c188a-106">When this attribute is specified, the Windows PowerShell runtime determines whether the supplied argument for the cmdlet parameter matches an element in the supplied element set.</span></span> <span data-ttu-id="c188a-107">仅当参数参数与集中的元素匹配时，才运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c188a-107">The cmdlet is run only if the parameter argument matches an element in the set.</span></span> <span data-ttu-id="c188a-108">如果未找到匹配项，则 Windows PowerShell 运行时将引发错误。</span><span class="sxs-lookup"><span data-stu-id="c188a-108">If no match is found, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="c188a-109">语法</span><span class="sxs-lookup"><span data-stu-id="c188a-109">Syntax</span></span>

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="c188a-110">parameters</span><span class="sxs-lookup"><span data-stu-id="c188a-110">Parameters</span></span>

<span data-ttu-id="c188a-111">`ValidValues`需要[ () 。](/dotnet/api/System.String)</span><span class="sxs-lookup"><span data-stu-id="c188a-111">`ValidValues` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="c188a-112">指定有效的参数元素值。</span><span class="sxs-lookup"><span data-stu-id="c188a-112">Specifies the valid parameter element values.</span></span> <span data-ttu-id="c188a-113">下面的示例演示如何指定一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="c188a-113">The following sample shows how to specify one element or multiple elements.</span></span>

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

<span data-ttu-id="c188a-114">`IgnoreCase` ([system.object](/dotnet/api/System.Boolean)) 可选的命名参数。</span><span class="sxs-lookup"><span data-stu-id="c188a-114">`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="c188a-115">的默认值 `true` 指示忽略大小写。</span><span class="sxs-lookup"><span data-stu-id="c188a-115">The default value of `true` indicates that case is ignored.</span></span> <span data-ttu-id="c188a-116">值为 `false` ，使 cmdlet 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c188a-116">A value of `false` makes the cmdlet case-sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="c188a-117">备注</span><span class="sxs-lookup"><span data-stu-id="c188a-117">Remarks</span></span>

- <span data-ttu-id="c188a-118">此属性仅可用于每个参数一次。</span><span class="sxs-lookup"><span data-stu-id="c188a-118">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="c188a-119">如果参数值为数组，则数组的每个元素都必须与属性集的元素匹配。</span><span class="sxs-lookup"><span data-stu-id="c188a-119">If the parameter value is an array, every element of the array must match an element of the attribute set.</span></span>

- <span data-ttu-id="c188a-120">ValidateSetAttribute 特性是由 [ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) 类定义的。</span><span class="sxs-lookup"><span data-stu-id="c188a-120">The ValidateSetAttribute attribute is defined by the [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c188a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c188a-121">See Also</span></span>

[<span data-ttu-id="c188a-122">System.web. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="c188a-122">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="c188a-123">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c188a-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
