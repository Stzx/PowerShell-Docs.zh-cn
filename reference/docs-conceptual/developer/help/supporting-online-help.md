---
ms.date: 09/13/2016
ms.topic: reference
title: 支持联机帮助
description: 支持联机帮助
ms.openlocfilehash: 0164b5e6c6c8d66a6ab2467a8adfb7efffe0fe17
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645417"
---
# <a name="supporting-online-help"></a><span data-ttu-id="d22a0-103">支持联机帮助</span><span class="sxs-lookup"><span data-stu-id="d22a0-103">Supporting Online Help</span></span>

<span data-ttu-id="d22a0-104">从 PowerShell 3.0 开始，有两种方法可支持 `Get-Help` PowerShell 命令的联机功能。</span><span class="sxs-lookup"><span data-stu-id="d22a0-104">Beginning in PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for PowerShell commands.</span></span> <span data-ttu-id="d22a0-105">本主题说明如何针对不同的命令类型实现此功能。</span><span class="sxs-lookup"><span data-stu-id="d22a0-105">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="d22a0-106">关于联机帮助</span><span class="sxs-lookup"><span data-stu-id="d22a0-106">About Online Help</span></span>

<span data-ttu-id="d22a0-107">联机帮助始终是 PowerShell 的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="d22a0-107">Online help has always been a vital part of PowerShell.</span></span> <span data-ttu-id="d22a0-108">尽管该 `Get-Help` cmdlet 会在命令提示符下显示帮助主题，但许多用户喜欢联机阅读的体验，包括颜色编码、超链接，以及在社区内容和基于 wiki 的文档中共享创意。</span><span class="sxs-lookup"><span data-stu-id="d22a0-108">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="d22a0-109">最重要的是，在可更新帮助出现之前，联机帮助提供了最新版本的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="d22a0-109">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="d22a0-110">随着 PowerShell 3.0 中可更新的帮助的出现，联机帮助仍起着至关重要的作用。</span><span class="sxs-lookup"><span data-stu-id="d22a0-110">With the advent of Updatable Help in PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="d22a0-111">除了灵活的用户体验外，联机帮助还向不或无法使用可更新帮助下载帮助主题的用户提供帮助。</span><span class="sxs-lookup"><span data-stu-id="d22a0-111">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="d22a0-112">Get-Help-Online 的工作方式</span><span class="sxs-lookup"><span data-stu-id="d22a0-112">How Get-Help -Online Works</span></span>

<span data-ttu-id="d22a0-113">若要帮助用户查找命令的联机帮助主题，此 `Get-Help` 命令有一个联机参数，可在用户的默认 internet 浏览器中打开命令的联机版本帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d22a0-113">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default internet browser.</span></span>

<span data-ttu-id="d22a0-114">例如，以下命令将打开 cmdlet 的联机帮助主题 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="d22a0-114">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="d22a0-115">为实现 `Get-Help -Online` ，该 `Get-Help` cmdlet 将在以下位置中查找联机版本帮助主题 (URI) 的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="d22a0-115">To implement `Get-Help -Online`, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="d22a0-116">命令的帮助主题的 " **相关链接** " 部分中的第一个链接。</span><span class="sxs-lookup"><span data-stu-id="d22a0-116">The first link in the **Related Links** section of the help topic for the command.</span></span> <span data-ttu-id="d22a0-117">必须在用户计算机上安装 "帮助" 主题。</span><span class="sxs-lookup"><span data-stu-id="d22a0-117">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="d22a0-118">此功能是在 PowerShell 2.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d22a0-118">This feature was introduced in PowerShell 2.0.</span></span>

- <span data-ttu-id="d22a0-119">任何命令的 **HelpUri** 属性。</span><span class="sxs-lookup"><span data-stu-id="d22a0-119">The **HelpUri** property of any command.</span></span> <span data-ttu-id="d22a0-120">即使在用户的计算机上未安装命令的帮助主题，也可以访问 **HelpUri** 属性。</span><span class="sxs-lookup"><span data-stu-id="d22a0-120">The **HelpUri** property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="d22a0-121">此功能是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d22a0-121">This feature was introduced in PowerShell 3.0.</span></span>

  <span data-ttu-id="d22a0-122">`Get-Help`获取 **HelpUri** 属性值之前，在 "**相关链接**" 部分的第一项中查找 URI。</span><span class="sxs-lookup"><span data-stu-id="d22a0-122">`Get-Help` looks for a URI in the first entry in the **Related Links** section before getting the **HelpUri** property value.</span></span> <span data-ttu-id="d22a0-123">如果属性值不正确或已更改，则可以通过在第一个相关链接中输入不同的值来覆盖它。</span><span class="sxs-lookup"><span data-stu-id="d22a0-123">If the property value is incorrect or has changed, you can override it by entering a different value in the first related link.</span></span> <span data-ttu-id="d22a0-124">但是，只有在用户计算机上安装了帮助主题后，第一个相关链接才有效。</span><span class="sxs-lookup"><span data-stu-id="d22a0-124">However, the first related link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="d22a0-125">将 URI 添加到命令帮助主题中的第一个相关链接</span><span class="sxs-lookup"><span data-stu-id="d22a0-125">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="d22a0-126">可以 `Get-Help -Online` 通过将有效 URI 添加到命令的基于 XML 的帮助主题的 " **相关链接** " 部分中的第一个条目来支持任何命令。</span><span class="sxs-lookup"><span data-stu-id="d22a0-126">You can support `Get-Help -Online` for any command by adding a valid URI to the first entry in the **Related Links** section of the XML-based help topic for the command.</span></span> <span data-ttu-id="d22a0-127">此选项仅在基于 XML 的帮助主题中有效，并且仅在用户计算机上安装了帮助主题时才有效。</span><span class="sxs-lookup"><span data-stu-id="d22a0-127">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="d22a0-128">如果安装了帮助主题并填充了 URI，则此值优先于命令的 **HelpUri** 属性。</span><span class="sxs-lookup"><span data-stu-id="d22a0-128">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="d22a0-129">若要支持此功能，URI 必须出现在 `maml:uri` 元素中第一个元素下的元素中 `maml:relatedLinks/maml:navigationLink` `maml:relatedLinks` 。</span><span class="sxs-lookup"><span data-stu-id="d22a0-129">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="d22a0-130">下面的 XML 显示 URI 的正确位置。</span><span class="sxs-lookup"><span data-stu-id="d22a0-130">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="d22a0-131">`Online version:`元素中的文本 `maml:linkText` 是最佳实践，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d22a0-131">The `Online version:` text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml
<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>https://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="d22a0-132">将 HelpUri 属性添加到命令</span><span class="sxs-lookup"><span data-stu-id="d22a0-132">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="d22a0-133">本部分介绍如何将 HelpUri 属性添加到不同类型的命令。</span><span class="sxs-lookup"><span data-stu-id="d22a0-133">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="d22a0-134">向 Cmdlet 添加 HelpUri 属性</span><span class="sxs-lookup"><span data-stu-id="d22a0-134">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="d22a0-135">对于用 c # 编写的 cmdlet，请将 **HelpUri** 特性添加到 **Cmdlet** 类中。</span><span class="sxs-lookup"><span data-stu-id="d22a0-135">For cmdlets written in C#, add a **HelpUri** attribute to the **Cmdlet** class.</span></span> <span data-ttu-id="d22a0-136">特性的值必须是以或开头的 URI `http` `https` 。</span><span class="sxs-lookup"><span data-stu-id="d22a0-136">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="d22a0-137">下面的代码显示了 cmdlet 类的 **HelpUri** 属性 `Get-History` 。</span><span class="sxs-lookup"><span data-stu-id="d22a0-137">The following code shows the **HelpUri** attribute of the `Get-History` cmdlet class.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="d22a0-138">将 HelpUri 属性添加到高级函数</span><span class="sxs-lookup"><span data-stu-id="d22a0-138">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="d22a0-139">对于高级函数，请将 **HelpUri** 属性添加到 **CmdletBinding** 属性。</span><span class="sxs-lookup"><span data-stu-id="d22a0-139">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="d22a0-140">属性的值必须是以 "http" 或 "https" 开头的 URI。</span><span class="sxs-lookup"><span data-stu-id="d22a0-140">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="d22a0-141">下面的代码演示函数的 **HelpUri** 特性。 `New-Calendar`</span><span class="sxs-lookup"><span data-stu-id="d22a0-141">The following code shows the **HelpUri** attribute of the `New-Calendar` function</span></span>

```powershell
function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="d22a0-142">将 HelpUri 特性添加到 CIM 命令</span><span class="sxs-lookup"><span data-stu-id="d22a0-142">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="d22a0-143">对于 CIM 命令，请将 **HelpUri** 属性添加到 CDXML 文件中的 **CmdletMetadata** 元素。</span><span class="sxs-lookup"><span data-stu-id="d22a0-143">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span>
<span data-ttu-id="d22a0-144">特性的值必须是以或开头的 URI `http` `https` 。</span><span class="sxs-lookup"><span data-stu-id="d22a0-144">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="d22a0-145">以下代码显示了 CIM 命令的 HelpUri 属性 `Start-Debug`</span><span class="sxs-lookup"><span data-stu-id="d22a0-145">The following code shows the HelpUri attribute of the `Start-Debug` CIM command</span></span>

```xml
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="d22a0-146">向工作流添加 HelpUri 属性</span><span class="sxs-lookup"><span data-stu-id="d22a0-146">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="d22a0-147">对于用 PowerShell 语言编写的工作流，请添加 **。将 .Externalhelp** 注释指令添加到工作流代码。</span><span class="sxs-lookup"><span data-stu-id="d22a0-147">For workflows that are written in the PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="d22a0-148">指令的值必须是以或开头的 URI `http` `https` 。</span><span class="sxs-lookup"><span data-stu-id="d22a0-148">The value of the directive must be a URI that begins with `http` or `https`.</span></span>

> [!NOTE]
> <span data-ttu-id="d22a0-149">在 PowerShell 中，基于 XAML 的工作流不支持 HelpUri 属性。</span><span class="sxs-lookup"><span data-stu-id="d22a0-149">The HelpUri property is not supported for XAML-based workflows in PowerShell.</span></span>

<span data-ttu-id="d22a0-150">下面的代码演示了。工作流文件中的 .Externalhelp 指令。</span><span class="sxs-lookup"><span data-stu-id="d22a0-150">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```
