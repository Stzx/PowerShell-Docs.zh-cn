---
ms.date: 09/13/2016
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要
description: 如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要
ms.openlocfilehash: aeeb0cdd1d6d17b88067928ff952dc57a9441917
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659048"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="c5bfa-103">如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要</span><span class="sxs-lookup"><span data-stu-id="c5bfa-103">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="c5bfa-104">本部分介绍如何添加在 cmdlet 帮助的 " **名称** " 和 " **概要** " 部分中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-104">This section describes how to add content that is displayed in the **NAME** and **SYNOPSIS** sections of the cmdlet help.</span></span> <span data-ttu-id="c5bfa-105">在帮助文件中，此内容将添加到每个 cmdlet 的命令节点。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-105">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="c5bfa-106">若要获取帮助文件的完整视图，请打开 `dll-Help.xml` 位于 PowerShell 安装目录中的文件之一。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="c5bfa-107">例如，该 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` 文件包含多个 PowerShell cmdlet 的内容。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

## <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="c5bfa-108">添加 Cmdlet 名称和摘要</span><span class="sxs-lookup"><span data-stu-id="c5bfa-108">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="c5bfa-109">Cmdlet 帮助可以为 cmdlet 显示两个描述。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-109">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="c5bfa-110">第一个说明是称为 "摘要" 的简短说明。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-110">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="c5bfa-111">第二个说明是在 [将详细描述添加到 Cmdlet 帮助主题](./how-to-add-a-cmdlet-description.md)中所述的更详细说明。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-111">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>
  <span data-ttu-id="c5bfa-112">这两个说明应作为一个段落来编写。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-112">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="c5bfa-113">在 "摘要" 中，不重复 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-113">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="c5bfa-114">通知用户 `Get-Server` cmdlet 获取服务器非常简短，但没有提示信息。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-114">Informing the user that the `Get-Server` cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="c5bfa-115">请改用同义词并向说明添加详细信息。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-115">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="c5bfa-116">示例： "获取表示本地或远程计算机的对象。"</span><span class="sxs-lookup"><span data-stu-id="c5bfa-116">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="c5bfa-117">使用摘要中的简单谓词，例如 "get"、"create" 和 "change"。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-117">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="c5bfa-118">避免使用 "set"，因为它不明确，如 "修改"。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-118">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="c5bfa-119">示例： "获取有关文件中 Authenticode 签名的信息。"</span><span class="sxs-lookup"><span data-stu-id="c5bfa-119">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="c5bfa-120">写入活动的语音。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-120">Write in active voice.</span></span> <span data-ttu-id="c5bfa-121">例如，"使用 TimeSpan 对象 ..."比 "可使用 TimeSpan 对象 ..." 更清晰。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-121">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="c5bfa-122">描述用于获取对象的 cmdlet 时，应避免出现 "显示" 谓词。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-122">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="c5bfa-123">虽然 Windows PowerShell 显示 cmdlet 数据，但向用户介绍 cmdlet 会返回 .NET Framework 对象（这些对象的数据可能不会显示），这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-123">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="c5bfa-124">如果您强调显示，用户可能不会意识到该 cmdlet 可能返回了许多其他有用的属性和未显示的方法。</span><span class="sxs-lookup"><span data-stu-id="c5bfa-124">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5bfa-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5bfa-125">See Also</span></span>

[<span data-ttu-id="c5bfa-126">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c5bfa-126">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
