---
title: Cmdlet 参数 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.openlocfilehash: 98b1d5fd0e7ffbf2d4d161f1bed73fb96a737bd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774756"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="b9a1b-102">Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="b9a1b-102">Cmdlet Parameters</span></span>

<span data-ttu-id="b9a1b-103">Cmdlet 参数提供允许 cmdlet 接受输入的机制。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-103">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="b9a1b-104">参数可以直接从命令行进行输入，也可以从通过管道传递给 cmdlet 的对象中进行输入，参数 (也称为*值*) 这些参数可以指定 cmdlet 接受的输入、cmdlet 应如何执行其操作以及 cmdlet 返回到管道的数据。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-104">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b9a1b-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="b9a1b-105">In This Section</span></span>

<span data-ttu-id="b9a1b-106">将[属性声明为参数](./declaring-properties-as-parameters.md)提供在声明 cmdlet 参数之前必须了解的基本信息。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-106">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="b9a1b-107">[Cmdlet 参数的类型](./types-of-cmdlet-parameters.md)描述可在 cmdlet 中声明的不同类型的参数。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-107">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="b9a1b-108">[Cmdlet 参数名称和功能指导原则](./standard-cmdlet-parameter-names-and-types.md)讨论了标准参数的名称、建议的数据类型和功能。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-108">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discusses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="b9a1b-109">[参数别名](./parameter-aliases.md)讨论可以为参数定义的别名。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-109">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="b9a1b-110">[常见参数名称](./common-parameter-names.md)本主题介绍 Windows PowerShell 添加到 cmdlet 的参数。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-110">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="b9a1b-111">[Cmdlet 参数集](./cmdlet-parameter-sets.md)讨论如何使用参数集编写单个 cmdlet，该 cmdlet 可以针对不同的方案执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-111">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="b9a1b-112">[Cmdlet 动态参数](./cmdlet-dynamic-parameters.md)讨论在特殊条件下可用于用户的参数。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-112">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="b9a1b-113">[支持 Cmdlet 参数中的通配符](./supporting-wildcard-characters-in-cmdlet-parameters.md)描述在设计将针对一组资源运行的 cmdlet 时，如何提供对通配符字符的支持。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-113">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="b9a1b-114">[正在验证参数输入](./validating-parameter-input.md)介绍 Windows PowerShell 如何验证传递给 cmdlet 参数的参数。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-114">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="b9a1b-115">[输入筛选器参数](./input-filter-parameters.md)讨论 `Filter` 、 `Include` 和参数， `Exclude` 这些参数用于筛选 cmdlet 影响的输入对象集。</span><span class="sxs-lookup"><span data-stu-id="b9a1b-115">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b9a1b-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="b9a1b-116">Related Sections</span></span>

[<span data-ttu-id="b9a1b-117">如何验证参数输入</span><span class="sxs-lookup"><span data-stu-id="b9a1b-117">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="b9a1b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9a1b-118">See Also</span></span>

[<span data-ttu-id="b9a1b-119">参数属性声明</span><span class="sxs-lookup"><span data-stu-id="b9a1b-119">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="b9a1b-120">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b9a1b-120">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)
