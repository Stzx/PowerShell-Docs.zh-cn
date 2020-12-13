---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 类声明
description: Cmdlet 类声明
ms.openlocfilehash: 854b0a4ca9f6c87c4fad3b71ee726beade585e02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653493"
---
# <a name="cmdlet-class-declaration"></a><span data-ttu-id="aa707-103">Cmdlet 类声明</span><span class="sxs-lookup"><span data-stu-id="aa707-103">Cmdlet Class Declaration</span></span>

<span data-ttu-id="aa707-104">通过将 **cmdlet** 特性指定为类的元数据，将 Microsoft .NET 框架类声明为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa707-104">A Microsoft .NET Framework class is declared as a cmdlet by specifying the **Cmdlet** attribute as metadata for the class.</span></span> <span data-ttu-id="aa707-105"> (**cmdlet** 特性是所有 cmdlet) 唯一必需的属性。</span><span class="sxs-lookup"><span data-stu-id="aa707-105">(The **Cmdlet** attribute is the only required attribute for all cmdlets).</span></span>
<span data-ttu-id="aa707-106">指定 **cmdlet** 属性时，必须指定用于向用户标识 Cmdlet 的动词和名词对。</span><span class="sxs-lookup"><span data-stu-id="aa707-106">When you specify the **Cmdlet** attribute, you must specify the verb-and-noun pair that identifies the cmdlet to the user.</span></span> <span data-ttu-id="aa707-107">并且，你必须描述 cmdlet 支持的 Windows PowerShell 功能。</span><span class="sxs-lookup"><span data-stu-id="aa707-107">And, you must describe the Windows PowerShell functionality that the cmdlet supports.</span></span> <span data-ttu-id="aa707-108">有关用于指定 **cmdlet** 特性的声明语法的详细信息，请参阅 [cmdlet 特性声明](./cmdlet-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aa707-108">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aa707-109">该 **Cmdlet** 特性由 [CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) 类定义。）</span><span class="sxs-lookup"><span data-stu-id="aa707-109">The **Cmdlet** attribute is defined by the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) class.</span></span> <span data-ttu-id="aa707-110">此类的属性对应于声明特性时使用的声明参数。</span><span class="sxs-lookup"><span data-stu-id="aa707-110">The properties of this class correspond to the declaration parameters that are used when you declare the attribute.</span></span>

## <a name="nouns"></a><span data-ttu-id="aa707-111">名词</span><span class="sxs-lookup"><span data-stu-id="aa707-111">Nouns</span></span>

<span data-ttu-id="aa707-112">Cmdlet 的名词指定该 cmdlet 操作的资源。</span><span class="sxs-lookup"><span data-stu-id="aa707-112">The noun of the cmdlet specifies the resources upon which the cmdlet acts.</span></span> <span data-ttu-id="aa707-113">名词将 cmdlet 与其他 cmdlet 区分开来。</span><span class="sxs-lookup"><span data-stu-id="aa707-113">The noun differentiates your cmdlets from other cmdlets.</span></span>

<span data-ttu-id="aa707-114">Cmdlet 名称中的名词必须是特定的，如果是泛型名词（如 *server*），最好添加一个短前缀，将资源与其他类似资源区分开来。</span><span class="sxs-lookup"><span data-stu-id="aa707-114">Nouns in cmdlet names must be specific, and in the case of generic nouns, such as *server*, it is best to add a short prefix that differentiates your resource from other similar resources.</span></span> <span data-ttu-id="aa707-115">例如，包含带有前缀的名词的 cmdlet 名称是 `Get-SQLServer` 。</span><span class="sxs-lookup"><span data-stu-id="aa707-115">For example, a cmdlet name that includes a noun with a prefix is `Get-SQLServer`.</span></span> <span data-ttu-id="aa707-116">将特定名词与更通用的动词组合后，用户可以通过其操作快速找到 cmdlet，然后通过其资源确定 cmdlet，同时避免不必要的 cmdlet 名称重复。</span><span class="sxs-lookup"><span data-stu-id="aa707-116">The combination of a specific noun with a more general verb enables the user to quickly locate the cmdlet by its action and then identify the cmdlet by its resource while avoiding unnecessary cmdlet name duplication.</span></span>

<span data-ttu-id="aa707-117">有关不能在 cmdlet 名称中使用的特殊字符列表，请参阅 [所需的开发指南](./required-development-guidelines.md)。</span><span class="sxs-lookup"><span data-stu-id="aa707-117">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="verbs"></a><span data-ttu-id="aa707-118">动词</span><span class="sxs-lookup"><span data-stu-id="aa707-118">Verbs</span></span>

<span data-ttu-id="aa707-119">指定谓词后，开发指南需要使用 Windows PowerShell 提供的一个预定义谓词。</span><span class="sxs-lookup"><span data-stu-id="aa707-119">When you specify a verb, the development guidelines require you to use one of the predefined verbs provided by Windows PowerShell.</span></span> <span data-ttu-id="aa707-120">通过使用其中一个预定义的动词，你将确保你编写的 cmdlet 与 Microsoft 和其他用户编写的 cmdlet 之间的一致性。</span><span class="sxs-lookup"><span data-stu-id="aa707-120">By using one of these predefined verbs, you will ensure consistency between the cmdlets that you write and the cmdlets that are written by Microsoft and by others.</span></span> <span data-ttu-id="aa707-121">例如，"Get" 谓词用于检索数据的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa707-121">For example, the "Get" verb is used for cmdlets that retrieve data.</span></span>

<span data-ttu-id="aa707-122">有关谓词准则的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="aa707-122">For more information about guidelines for verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span> <span data-ttu-id="aa707-123">有关不能在 cmdlet 名称中使用的特殊字符列表，请参阅 [所需的开发指南](./required-development-guidelines.md)。</span><span class="sxs-lookup"><span data-stu-id="aa707-123">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="supporting-windows-powershell-functionality"></a><span data-ttu-id="aa707-124">支持 Windows PowerShell 功能</span><span class="sxs-lookup"><span data-stu-id="aa707-124">Supporting Windows PowerShell Functionality</span></span>

<span data-ttu-id="aa707-125">**Cmdlet** 属性还允许你指定 Cmdlet 支持 Windows PowerShell 提供的某些常见功能。</span><span class="sxs-lookup"><span data-stu-id="aa707-125">The **Cmdlet** attribute also allows you to specify that your cmdlet supports some of the common functionality that is provided by Windows PowerShell.</span></span> <span data-ttu-id="aa707-126">这包括对常见功能的支持，例如用户反馈确认 (称为支持 ShouldProcess 功能) 和支持事务。</span><span class="sxs-lookup"><span data-stu-id="aa707-126">This includes support for common functionality such as user feedback confirmation (referred to as support for the ShouldProcess feature) and support for transactions.</span></span> <span data-ttu-id="aa707-127">Windows PowerShell 2.0) 中引入了 (对事务的支持。</span><span class="sxs-lookup"><span data-stu-id="aa707-127">(Support for transactions was introduced in Windows PowerShell 2.0).</span></span>

<span data-ttu-id="aa707-128">有关用于指定 **cmdlet** 特性的声明语法的详细信息，请参阅 [cmdlet 特性声明](./cmdlet-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aa707-128">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="cmdlet-class-definition"></a><span data-ttu-id="aa707-129">Cmdlet 类定义</span><span class="sxs-lookup"><span data-stu-id="aa707-129">Cmdlet Class Definition</span></span>

<span data-ttu-id="aa707-130">下面的代码是 GetProc cmdlet 类的定义。</span><span class="sxs-lookup"><span data-stu-id="aa707-130">The following code is the definition for a GetProc cmdlet class.</span></span> <span data-ttu-id="aa707-131">请注意，使用了 Pascal 大小写，并且类的名称包含 cmdlet 的动词和名词。</span><span class="sxs-lookup"><span data-stu-id="aa707-131">Notice that Pascal casing is used and that the name of the class includes the verb and noun of the cmdlet.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="33-34":::

## <a name="pascal-casing"></a><span data-ttu-id="aa707-132">Pascal 大小写</span><span class="sxs-lookup"><span data-stu-id="aa707-132">Pascal Casing</span></span>

<span data-ttu-id="aa707-133">命名 cmdlet 时，请使用 Pascal 大小写。</span><span class="sxs-lookup"><span data-stu-id="aa707-133">When you name cmdlets, use Pascal casing.</span></span> <span data-ttu-id="aa707-134">例如，在 `Get-Item` `Get-ItemProperty` 命名 cmdlet 时，和 cmdlet 会显示正确使用大小写的方式。</span><span class="sxs-lookup"><span data-stu-id="aa707-134">For example, the `Get-Item` and `Get-ItemProperty` cmdlets show the correct way to use capitalization when you are naming cmdlets.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa707-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa707-135">See Also</span></span>

[<span data-ttu-id="aa707-136">System.web. CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="aa707-136">System.Management.Automation.CmdletAttribute</span></span>](/dotnet/api/System.Management.Automation.CmdletAttribute)

[<span data-ttu-id="aa707-137">CmdletAttribute 声明</span><span class="sxs-lookup"><span data-stu-id="aa707-137">CmdletAttribute Declaration</span></span>](./cmdlet-attribute-declaration.md)

[<span data-ttu-id="aa707-138">Cmdlet 谓词名称</span><span class="sxs-lookup"><span data-stu-id="aa707-138">Cmdlet Verb Names</span></span>](./approved-verbs-for-windows-powershell-commands.md)

[<span data-ttu-id="aa707-139">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aa707-139">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="aa707-140">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="aa707-140">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
