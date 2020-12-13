---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建 Cmdlet 帮助文件
description: 如何创建 Cmdlet 帮助文件
ms.openlocfilehash: 40259c8f9496b10380805a78f3711aed6f1bf2e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659097"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="12374-103">如何创建 Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="12374-103">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="12374-104">本部分介绍如何创建包含 Windows PowerShell cmdlet 帮助主题内容的有效 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="12374-104">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="12374-105">本部分讨论如何命名帮助文件，如何添加相应的 XML 标头，以及如何添加将包含 cmdlet 帮助内容的不同部分的节点。</span><span class="sxs-lookup"><span data-stu-id="12374-105">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="12374-106">若要获取帮助文件的完整视图，请打开 `dll-Help.xml` 位于 Windows PowerShell 安装目录中的文件之一。</span><span class="sxs-lookup"><span data-stu-id="12374-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="12374-107">例如，该 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` 文件包含多个 PowerShell cmdlet 的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="12374-108">如何创建 Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="12374-108">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="12374-109">创建一个文本文件，并使用 UTF8 编码保存该文件。</span><span class="sxs-lookup"><span data-stu-id="12374-109">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="12374-110">文件名必须具有以下格式，以便 Windows PowerShell 能够将其作为 cmdlet 帮助文件进行检测。</span><span class="sxs-lookup"><span data-stu-id="12374-110">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="12374-111">将以下 XML 标头添加到文本文件。</span><span class="sxs-lookup"><span data-stu-id="12374-111">Add the following XML headers to the text file.</span></span> <span data-ttu-id="12374-112">请注意，将根据 Microsoft 协助标记语言 (MAML) 架构来验证该文件。</span><span class="sxs-lookup"><span data-stu-id="12374-112">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="12374-113">目前，PowerShell 不提供任何用于验证文件的工具。</span><span class="sxs-lookup"><span data-stu-id="12374-113">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="12374-114">将 **命令** 节点添加到程序集中每个 cmdlet 的 cmdlet 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="12374-114">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="12374-115">**命令** 节点内的每个节点都与 cmdlet 帮助主题的不同部分相关。</span><span class="sxs-lookup"><span data-stu-id="12374-115">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="12374-116">下表列出了每个节点的 XML 元素，后跟每个节点的说明。</span><span class="sxs-lookup"><span data-stu-id="12374-116">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="12374-117">节点</span><span class="sxs-lookup"><span data-stu-id="12374-117">Node</span></span>           |                                                                                                     <span data-ttu-id="12374-118">描述</span><span class="sxs-lookup"><span data-stu-id="12374-118">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="12374-119">为 cmdlet 帮助主题的名称和摘要部分添加内容。</span><span class="sxs-lookup"><span data-stu-id="12374-119">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-120">有关详细信息，请参阅 [如何添加 Cmdlet 名称和摘要](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-120">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="12374-121">添加 cmdlet 帮助主题的 "描述" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-121">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-122">有关详细信息，请参阅 [如何将详细描述添加到 Cmdlet 的帮助主题](./how-to-add-a-cmdlet-description.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-122">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="12374-123">为 cmdlet 帮助主题的语法部分添加内容。</span><span class="sxs-lookup"><span data-stu-id="12374-123">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-124">有关详细信息，请参阅 [如何将语法添加到 Cmdlet 的帮助主题](./how-to-add-syntax-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-124">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="12374-125">添加 cmdlet 帮助主题的参数部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-125">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-126">有关详细信息，请参阅 [如何将参数添加到 Cmdlet 的帮助主题](./how-to-add-parameter-information.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-126">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="12374-127">添加 cmdlet 帮助主题的 "输入" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-127">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-128">有关详细信息，请参阅 [如何将输入类型添加到 Cmdlet 的帮助主题](./how-to-add-input-types-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-128">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="12374-129">添加 cmdlet 帮助主题的 "输出" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-129">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-130">有关详细信息，请参阅 [如何将返回值添加到 Cmdlet 的帮助主题](./how-to-add-return-values-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-130">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="12374-131">添加 cmdlet 帮助主题的 "注释" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-131">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-132">有关详细信息，请参阅 [如何向 Cmdlet 帮助主题添加注释](./how-to-add-notes-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-132">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="12374-133">添加 cmdlet 帮助主题的 "示例" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-133">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-134">有关详细信息，请参阅 [如何将示例添加到 Cmdlet 的帮助主题](./how-to-add-examples-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-134">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="12374-135">添加 cmdlet 帮助主题的 "相关链接" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="12374-135">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="12374-136">有关详细信息，请参阅 [如何将相关链接添加到 Cmdlet 的帮助主题](./how-to-add-related-links-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="12374-136">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="12374-137">示例</span><span class="sxs-lookup"><span data-stu-id="12374-137">Example</span></span>

 <span data-ttu-id="12374-138">下面是一个 **命令** 节点示例，其中包含 cmdlet 帮助主题各个部分的节点。</span><span class="sxs-lookup"><span data-stu-id="12374-138">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a><span data-ttu-id="12374-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12374-139">See Also</span></span>

 [<span data-ttu-id="12374-140">如何添加 Cmdlet 名称和摘要</span><span class="sxs-lookup"><span data-stu-id="12374-140">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-141">如何将详细描述添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="12374-141">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="12374-142">如何向 Cmdlet 帮助主题添加语法</span><span class="sxs-lookup"><span data-stu-id="12374-142">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-143">如何将参数添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="12374-143">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="12374-144">如何向 Cmdlet 帮助主题添加输入类型</span><span class="sxs-lookup"><span data-stu-id="12374-144">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-145">如何向 Cmdlet 帮助主题添加返回值</span><span class="sxs-lookup"><span data-stu-id="12374-145">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-146">如何向 Cmdlet 帮助主题添加注释</span><span class="sxs-lookup"><span data-stu-id="12374-146">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-147">如何向 Cmdlet 帮助主题添加示例</span><span class="sxs-lookup"><span data-stu-id="12374-147">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-148">如何向 Cmdlet 帮助主题添加相关链接</span><span class="sxs-lookup"><span data-stu-id="12374-148">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="12374-149">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="12374-149">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
