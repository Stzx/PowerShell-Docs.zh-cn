---
ms.date: 09/13/2016
ms.topic: reference
title: 验证参数输入
description: 验证参数输入
ms.openlocfilehash: a97b5c670e8c36463a85bbef1506f6311bdd5ec3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660397"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="b332c-103">验证参数输入</span><span class="sxs-lookup"><span data-stu-id="b332c-103">Validating Parameter Input</span></span>

<span data-ttu-id="b332c-104">PowerShell 可以通过多种方式验证传递到 cmdlet 参数的参数。</span><span class="sxs-lookup"><span data-stu-id="b332c-104">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="b332c-105">PowerShell 可以验证参数的字符的长度、范围和模式。</span><span class="sxs-lookup"><span data-stu-id="b332c-105">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="b332c-106">它可以验证计数)  (可用参数的数目。</span><span class="sxs-lookup"><span data-stu-id="b332c-106">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="b332c-107">这些验证规则由使用 cmdlet 类的公共属性上的 Parameter 特性声明的验证特性定义。</span><span class="sxs-lookup"><span data-stu-id="b332c-107">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="b332c-108">若要验证参数参数，PowerShell 运行时使用验证特性提供的信息来确认在运行 cmdlet 之前参数的值。</span><span class="sxs-lookup"><span data-stu-id="b332c-108">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="b332c-109">如果参数输入无效，则用户将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="b332c-109">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="b332c-110">每个验证参数都定义一个由 PowerShell 强制执行的验证规则。</span><span class="sxs-lookup"><span data-stu-id="b332c-110">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="b332c-111">PowerShell 根据以下属性强制执行验证规则。</span><span class="sxs-lookup"><span data-stu-id="b332c-111">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="b332c-112">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="b332c-112">ValidateCount</span></span>

<span data-ttu-id="b332c-113">指定参数可以接受的最小和最大参数数目。</span><span class="sxs-lookup"><span data-stu-id="b332c-113">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="b332c-114">有关详细信息，请参阅 [ValidateCount 特性声明](./validatecount-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="b332c-114">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="b332c-115">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="b332c-115">ValidateLength</span></span>

<span data-ttu-id="b332c-116">指定参数参数中的最小和最大字符数。</span><span class="sxs-lookup"><span data-stu-id="b332c-116">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="b332c-117">有关详细信息，请参阅 [ValidateLength 特性声明](./validatelength-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="b332c-117">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="b332c-118">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="b332c-118">ValidatePattern</span></span>

<span data-ttu-id="b332c-119">指定用于验证参数参数的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="b332c-119">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="b332c-120">有关详细信息，请参阅 [ValidatePattern 特性声明](./validatepattern-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="b332c-120">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="b332c-121">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="b332c-121">ValidateRange</span></span>

<span data-ttu-id="b332c-122">指定参数参数的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="b332c-122">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="b332c-123">有关详细信息，请参阅 [ValidateRange 特性声明](./validaterange-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="b332c-123">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="b332c-124">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="b332c-124">ValidateSet</span></span>

<span data-ttu-id="b332c-125">指定参数参数的有效值。</span><span class="sxs-lookup"><span data-stu-id="b332c-125">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="b332c-126">有关详细信息，请参阅 [ValidateSet 特性声明](./validateset-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="b332c-126">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b332c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b332c-127">See Also</span></span>

[<span data-ttu-id="b332c-128">如何验证参数输入</span><span class="sxs-lookup"><span data-stu-id="b332c-128">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="b332c-129">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b332c-129">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
