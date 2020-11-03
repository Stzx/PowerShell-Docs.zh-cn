---
description: 引入了一种使用脚本创建 cmdlet 的高级功能。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: 53cba129778161d8c44186eb999387e51bb71e50
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200115"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="f2743-104">关于函数高级</span><span class="sxs-lookup"><span data-stu-id="f2743-104">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="f2743-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="f2743-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f2743-106">引入了一种使用脚本创建 cmdlet 的高级功能。</span><span class="sxs-lookup"><span data-stu-id="f2743-106">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="f2743-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="f2743-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f2743-108">Cmdlet 是参与 PowerShell 管道语义的单个命令。</span><span class="sxs-lookup"><span data-stu-id="f2743-108">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="f2743-109">这包括二进制 cmdlet、高级脚本函数、CDXML 和工作流。</span><span class="sxs-lookup"><span data-stu-id="f2743-109">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="f2743-110">利用高级功能，你可以创建以 PowerShell 函数形式编写的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2743-110">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="f2743-111">利用高级功能，无需编写和编译二进制 cmdlet 即可更轻松地创建 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2743-111">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="f2743-112">二进制 cmdlet 是用 .NET 语言（如 c #）编写的 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="f2743-112">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="f2743-113">高级函数使用 `CmdletBinding` 特性将它们标识为充当 cmdlet 的函数。</span><span class="sxs-lookup"><span data-stu-id="f2743-113">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="f2743-114">`CmdletBinding`属性类似于编译的 cmdlet 类中使用的 cmdlet 属性，用于将类标识为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2743-114">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="f2743-115">有关此属性的详细信息，请参阅 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)。</span><span class="sxs-lookup"><span data-stu-id="f2743-115">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="f2743-116">下面的示例演示一个函数，该函数接受名称，然后使用提供的名称打印问候语。</span><span class="sxs-lookup"><span data-stu-id="f2743-116">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="f2743-117">另请注意，此函数定义一个名称，该名称包括一个谓词 (发送) 和名词 (问候语) 对，如编译 cmdlet 的动词-名词对。</span><span class="sxs-lookup"><span data-stu-id="f2743-117">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="f2743-118">但是，函数不需要具有动词-名词名称。</span><span class="sxs-lookup"><span data-stu-id="f2743-118">However, functions are not required to have a verb-noun name.</span></span>

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

<span data-ttu-id="f2743-119">函数的参数是使用参数特性声明的。</span><span class="sxs-lookup"><span data-stu-id="f2743-119">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="f2743-120">此特性可以单独使用，也可以与 Alias 特性或其他一些参数验证特性结合使用。</span><span class="sxs-lookup"><span data-stu-id="f2743-120">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="f2743-121">有关如何声明参数 (包括在运行时) 添加的动态参数的详细信息，请参阅 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f2743-121">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="f2743-122">先前函数的实际工作是在进程块中执行的，该进程块等效于编译的 cmdlet 用来处理传递到 cmdlet 的数据的 ProcessingRecord 方法。</span><span class="sxs-lookup"><span data-stu-id="f2743-122">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="f2743-123">[About_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)主题中介绍了此块以及 Begin 和 End 块。</span><span class="sxs-lookup"><span data-stu-id="f2743-123">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="f2743-124">高级函数与已编译的 cmdlet 在以下方面有所不同：</span><span class="sxs-lookup"><span data-stu-id="f2743-124">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="f2743-125">当字符串数组绑定到布尔参数时，高级函数参数绑定不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="f2743-125">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="f2743-126">ValidateSet 属性和 ValidatePattern 属性不能传递指定的参数。</span><span class="sxs-lookup"><span data-stu-id="f2743-126">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="f2743-127">不能在事务中使用高级函数。</span><span class="sxs-lookup"><span data-stu-id="f2743-127">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2743-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2743-128">SEE ALSO</span></span>

[<span data-ttu-id="f2743-129">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f2743-129">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="f2743-130">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="f2743-130">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="f2743-131">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="f2743-131">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="f2743-132">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="f2743-132">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="f2743-133">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="f2743-133">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
