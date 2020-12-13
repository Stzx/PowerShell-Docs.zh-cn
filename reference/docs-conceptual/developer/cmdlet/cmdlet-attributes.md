---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 属性
description: Cmdlet 属性
ms.openlocfilehash: 6a106f33cb34c6c33b88a981815543bc9af4e4ba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653521"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="935d3-103">Cmdlet 属性</span><span class="sxs-lookup"><span data-stu-id="935d3-103">Cmdlet Attributes</span></span>

<span data-ttu-id="935d3-104">Windows PowerShell 定义多个属性，可用于向 cmdlet 添加常见功能，而无需在自己的代码中实现该功能。</span><span class="sxs-lookup"><span data-stu-id="935d3-104">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="935d3-105">这包括 Cmdlet 属性，该属性用于将 Microsoft .NET 框架类标识为 cmdlet 类、指定 cmdlet 返回的 .NET Framework 类型的 OutputType 属性、用于将公共属性标识为 cmdlet 参数的参数属性等。</span><span class="sxs-lookup"><span data-stu-id="935d3-105">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="935d3-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="935d3-106">In This Section</span></span>

<span data-ttu-id="935d3-107">[Cmdlet 代码中的属性](./attributes-in-cmdlet-code.md) 介绍使用 cmdlet 代码中的属性的好处。</span><span class="sxs-lookup"><span data-stu-id="935d3-107">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="935d3-108">[特性类型](./attribute-types.md) 描述可以修饰 cmdlet 类的不同属性。</span><span class="sxs-lookup"><span data-stu-id="935d3-108">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="935d3-109">[Alias 特性声明](./alias-attribute-declaration.md) 描述如何为 cmdlet 参数名称定义别名。</span><span class="sxs-lookup"><span data-stu-id="935d3-109">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="935d3-110">[Cmdlet 特性声明](./cmdlet-attribute-declaration.md) 描述如何将 .NET Framework 类定义为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="935d3-110">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="935d3-111">[Credential 特性声明](./credential-attribute-declaration.md) 介绍如何添加对将字符串输入转换为 [system.web](/dotnet/api/System.Management.Automation.PSCredential) 对象的支持。</span><span class="sxs-lookup"><span data-stu-id="935d3-111">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="935d3-112">[OutputType 特性声明](./outputtype-attribute-declaration.md) 描述如何指定 cmdlet 返回的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="935d3-112">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="935d3-113">[参数属性声明](./parameter-attribute-declaration.md) 描述如何定义 cmdlet 的参数。</span><span class="sxs-lookup"><span data-stu-id="935d3-113">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="935d3-114">[ValidateCount 特性声明](./validatecount-attribute-declaration.md) 描述如何定义参数允许的参数数量。</span><span class="sxs-lookup"><span data-stu-id="935d3-114">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="935d3-115">[ValidateLength 特性声明](./validatelength-attribute-declaration.md) 描述如何定义参数参数的长度 (以字符) 。</span><span class="sxs-lookup"><span data-stu-id="935d3-115">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="935d3-116">[ValidatePattern 特性声明](./validatepattern-attribute-declaration.md) 描述如何定义参数参数的有效模式。</span><span class="sxs-lookup"><span data-stu-id="935d3-116">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="935d3-117">[ValidateRange 特性声明](./validaterange-attribute-declaration.md) 描述如何定义参数参数的有效范围。</span><span class="sxs-lookup"><span data-stu-id="935d3-117">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="935d3-118">[ValidateSet 特性声明](./validateset-attribute-declaration.md) 描述如何定义参数参数的可能值。</span><span class="sxs-lookup"><span data-stu-id="935d3-118">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="935d3-119">参考</span><span class="sxs-lookup"><span data-stu-id="935d3-119">Reference</span></span>

[<span data-ttu-id="935d3-120">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="935d3-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
