---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateLength 属性声明
description: ValidateLength 属性声明
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646186"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="fc1b0-103">ValidateLength 属性声明</span><span class="sxs-lookup"><span data-stu-id="fc1b0-103">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="fc1b0-104">ValidateLength 属性指定 cmdlet 参数参数的最小和最大字符数。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-104">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="fc1b0-105">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc1b0-106">语法</span><span class="sxs-lookup"><span data-stu-id="fc1b0-106">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="fc1b0-107">parameters</span><span class="sxs-lookup"><span data-stu-id="fc1b0-107">Parameters</span></span>

<span data-ttu-id="fc1b0-108">`MinLength`需要[ () 。](/dotnet/api/System.Int32)</span><span class="sxs-lookup"><span data-stu-id="fc1b0-108">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="fc1b0-109">指定允许的最小字符数。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-109">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="fc1b0-110">`MaxLength`需要[ () 。](/dotnet/api/System.Int32)</span><span class="sxs-lookup"><span data-stu-id="fc1b0-110">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="fc1b0-111">指定允许的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-111">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc1b0-112">备注</span><span class="sxs-lookup"><span data-stu-id="fc1b0-112">Remarks</span></span>

- <span data-ttu-id="fc1b0-113">有关如何声明此属性的详细信息，请参阅 [如何声明输入验证规则](./how-to-validate-parameter-input.md)。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-113">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="fc1b0-114">如果未使用此属性，则相应的参数参数可以为任意长度。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-114">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="fc1b0-115">Windows PowerShell 运行时在以下条件下引发错误：</span><span class="sxs-lookup"><span data-stu-id="fc1b0-115">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="fc1b0-116">当 attribute 参数的值 `MaxLength` 小于 attribute 参数的值时 `MinLength` 。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-116">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="fc1b0-117">如果 `MaxLength` 特性参数设置为0，则为。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-117">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="fc1b0-118">如果参数不是字符串，则为。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-118">When the argument is not a string.</span></span>

- <span data-ttu-id="fc1b0-119">ValidateLength 特性是由 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) 类定义的。</span><span class="sxs-lookup"><span data-stu-id="fc1b0-119">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc1b0-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc1b0-120">See Also</span></span>

[<span data-ttu-id="fc1b0-121">System.web. Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="fc1b0-121">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="fc1b0-122">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc1b0-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
