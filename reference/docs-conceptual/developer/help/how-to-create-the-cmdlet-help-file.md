---
title: 如何创建 Cmdlet 帮助文件 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: b5a5f3e187634b38ba3ce3da18a7ad64ccc09ce2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893010"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="24334-102">如何创建 Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="24334-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="24334-103">本部分介绍如何创建包含 Windows PowerShell cmdlet 帮助主题内容的有效 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="24334-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="24334-104">本部分讨论如何命名帮助文件，如何添加相应的 XML 标头，以及如何添加将包含 cmdlet 帮助内容的不同部分的节点。</span><span class="sxs-lookup"><span data-stu-id="24334-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="24334-105">若要获取帮助文件的完整视图，请打开 `dll-Help.xml` 位于 Windows PowerShell 安装目录中的文件之一。</span><span class="sxs-lookup"><span data-stu-id="24334-105">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="24334-106">例如，该 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` 文件包含多个 PowerShell cmdlet 的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-106">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="24334-107">如何创建 Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="24334-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="24334-108">创建一个文本文件，并使用 UTF8 编码保存该文件。</span><span class="sxs-lookup"><span data-stu-id="24334-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="24334-109">文件名必须具有以下格式，以便 Windows PowerShell 能够将其作为 cmdlet 帮助文件进行检测。</span><span class="sxs-lookup"><span data-stu-id="24334-109">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="24334-110">将以下 XML 标头添加到文本文件。</span><span class="sxs-lookup"><span data-stu-id="24334-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="24334-111">请注意，将根据 Microsoft 协助标记语言（MAML）架构对文件进行验证。</span><span class="sxs-lookup"><span data-stu-id="24334-111">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="24334-112">目前，PowerShell 不提供任何用于验证文件的工具。</span><span class="sxs-lookup"><span data-stu-id="24334-112">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="24334-113">将**命令**节点添加到程序集中每个 cmdlet 的 cmdlet 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="24334-113">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="24334-114">**命令**节点内的每个节点都与 cmdlet 帮助主题的不同部分相关。</span><span class="sxs-lookup"><span data-stu-id="24334-114">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="24334-115">下表列出了每个节点的 XML 元素，后跟每个节点的说明。</span><span class="sxs-lookup"><span data-stu-id="24334-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="24334-116">节点</span><span class="sxs-lookup"><span data-stu-id="24334-116">Node</span></span>           |                                                                                                     <span data-ttu-id="24334-117">说明</span><span class="sxs-lookup"><span data-stu-id="24334-117">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="24334-118">为 cmdlet 帮助主题的名称和摘要部分添加内容。</span><span class="sxs-lookup"><span data-stu-id="24334-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-119">有关详细信息，请参阅[如何添加 Cmdlet 名称和摘要](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="24334-120">添加 cmdlet 帮助主题的 "描述" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-121">有关详细信息，请参阅[如何将详细描述添加到 Cmdlet 的帮助主题](./how-to-add-a-cmdlet-description.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="24334-122">为 cmdlet 帮助主题的语法部分添加内容。</span><span class="sxs-lookup"><span data-stu-id="24334-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-123">有关详细信息，请参阅[如何将语法添加到 Cmdlet 的帮助主题](./how-to-add-syntax-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="24334-124">添加 cmdlet 帮助主题的参数部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-125">有关详细信息，请参阅[如何将参数添加到 Cmdlet 的帮助主题](./how-to-add-parameter-information.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="24334-126">添加 cmdlet 帮助主题的 "输入" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-127">有关详细信息，请参阅[如何将输入类型添加到 Cmdlet 的帮助主题](./how-to-add-input-types-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="24334-128">添加 cmdlet 帮助主题的 "输出" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-129">有关详细信息，请参阅[如何将返回值添加到 Cmdlet 的帮助主题](./how-to-add-return-values-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="24334-130">添加 cmdlet 帮助主题的 "注释" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-130">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-131">有关详细信息，请参阅[如何向 Cmdlet 帮助主题添加注释](./how-to-add-notes-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="24334-132">添加 cmdlet 帮助主题的 "示例" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-133">有关详细信息，请参阅[如何将示例添加到 Cmdlet 的帮助主题](./how-to-add-examples-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="24334-134">添加 cmdlet 帮助主题的 "相关链接" 部分的内容。</span><span class="sxs-lookup"><span data-stu-id="24334-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="24334-135">有关详细信息，请参阅[如何将相关链接添加到 Cmdlet 的帮助主题](./how-to-add-related-links-to-a-cmdlet-help-topic.md)。</span><span class="sxs-lookup"><span data-stu-id="24334-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="24334-136">示例</span><span class="sxs-lookup"><span data-stu-id="24334-136">Example</span></span>

 <span data-ttu-id="24334-137">下面是一个**命令**节点示例，其中包含 cmdlet 帮助主题各个部分的节点。</span><span class="sxs-lookup"><span data-stu-id="24334-137">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="https://schemas.microsoft.com/maml/2004/10"
  xmlns:command="https://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="https://schemas.microsoft.com/maml/dev/2004/10">
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

## <a name="see-also"></a><span data-ttu-id="24334-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24334-138">See Also</span></span>

 [<span data-ttu-id="24334-139">如何添加 Cmdlet 名称和摘要</span><span class="sxs-lookup"><span data-stu-id="24334-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-140">如何将详细描述添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="24334-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="24334-141">如何向 Cmdlet 帮助主题添加语法</span><span class="sxs-lookup"><span data-stu-id="24334-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-142">如何将参数添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="24334-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="24334-143">如何向 Cmdlet 帮助主题添加输入类型</span><span class="sxs-lookup"><span data-stu-id="24334-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-144">如何向 Cmdlet 帮助主题添加返回值</span><span class="sxs-lookup"><span data-stu-id="24334-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-145">如何向 Cmdlet 帮助主题添加注释</span><span class="sxs-lookup"><span data-stu-id="24334-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-146">如何向 Cmdlet 帮助主题添加示例</span><span class="sxs-lookup"><span data-stu-id="24334-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-147">如何向 Cmdlet 帮助主题添加相关链接</span><span class="sxs-lookup"><span data-stu-id="24334-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="24334-148">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="24334-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
