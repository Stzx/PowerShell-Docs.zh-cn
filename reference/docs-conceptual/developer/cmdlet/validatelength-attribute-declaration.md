---
title: ValidateLength 特性声明 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a1a494534169b2da470286020dfacfa8e9084839
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692327"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="5ea84-102">ValidateLength 属性声明</span><span class="sxs-lookup"><span data-stu-id="5ea84-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="5ea84-103">ValidateLength 属性指定 cmdlet 参数参数的最小和最大字符数。</span><span class="sxs-lookup"><span data-stu-id="5ea84-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="5ea84-104">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="5ea84-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ea84-105">语法</span><span class="sxs-lookup"><span data-stu-id="5ea84-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="5ea84-106">参数</span><span class="sxs-lookup"><span data-stu-id="5ea84-106">Parameters</span></span>

<span data-ttu-id="5ea84-107">`MinLength`必需[System.Int32](/dotnet/api/System.Int32)。</span><span class="sxs-lookup"><span data-stu-id="5ea84-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="5ea84-108">指定允许的最小字符数。</span><span class="sxs-lookup"><span data-stu-id="5ea84-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="5ea84-109">`MaxLength`必需[System.Int32](/dotnet/api/System.Int32)。</span><span class="sxs-lookup"><span data-stu-id="5ea84-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="5ea84-110">指定允许的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="5ea84-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ea84-111">备注</span><span class="sxs-lookup"><span data-stu-id="5ea84-111">Remarks</span></span>

- <span data-ttu-id="5ea84-112">有关如何声明此属性的详细信息，请参阅[如何声明输入验证规则](./how-to-validate-parameter-input.md)。</span><span class="sxs-lookup"><span data-stu-id="5ea84-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="5ea84-113">如果未使用此属性，则相应的参数参数可以为任意长度。</span><span class="sxs-lookup"><span data-stu-id="5ea84-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="5ea84-114">Windows PowerShell 运行时在以下条件下引发错误：</span><span class="sxs-lookup"><span data-stu-id="5ea84-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="5ea84-115">当 attribute 参数的值 `MaxLength` 小于 attribute 参数的值时 `MinLength` 。</span><span class="sxs-lookup"><span data-stu-id="5ea84-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

  - <span data-ttu-id="5ea84-116">如果 `MaxLength` 特性参数设置为0，则为。</span><span class="sxs-lookup"><span data-stu-id="5ea84-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

  - <span data-ttu-id="5ea84-117">如果参数不是字符串，则为。</span><span class="sxs-lookup"><span data-stu-id="5ea84-117">When the argument is not a string.</span></span>

- <span data-ttu-id="5ea84-118">ValidateLength 特性是由[Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)类定义的。</span><span class="sxs-lookup"><span data-stu-id="5ea84-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ea84-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea84-119">See Also</span></span>

[<span data-ttu-id="5ea84-120">System.web. Validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="5ea84-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="5ea84-121">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5ea84-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
