---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建格式设置文件 (.format.ps1xml)
description: 如何创建格式设置文件 (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652006"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="2df95-103">如何创建格式设置文件 (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="2df95-103">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="2df95-104">本主题介绍如何创建 ( # B0 xml) 格式的格式化文件。</span><span class="sxs-lookup"><span data-stu-id="2df95-104">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="2df95-105">还可以通过复制 Windows PowerShell 提供的文件之一来创建格式化文件。</span><span class="sxs-lookup"><span data-stu-id="2df95-105">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="2df95-106">如果复制现有的文件，请删除现有的数字签名，并将您自己的签名添加到新文件中。</span><span class="sxs-lookup"><span data-stu-id="2df95-106">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="2df95-107">创建 .format.ps1xml 文件。</span><span class="sxs-lookup"><span data-stu-id="2df95-107">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="2df95-108">使用文本编辑器（如记事本）创建文本文件 ( .txt) 。</span><span class="sxs-lookup"><span data-stu-id="2df95-108">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="2df95-109">将以下行复制到格式设置文件中。</span><span class="sxs-lookup"><span data-stu-id="2df95-109">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="2df95-110">`<Configuration></Configuration>`标记定义根 `Configuration` 节点。</span><span class="sxs-lookup"><span data-stu-id="2df95-110">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="2df95-111">所有其他 XML 标记将包含在此节点中。</span><span class="sxs-lookup"><span data-stu-id="2df95-111">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="2df95-112">`<ViewDefinitions></ViewDefinitions>`标记定义 `ViewDefinitions` 节点。</span><span class="sxs-lookup"><span data-stu-id="2df95-112">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="2df95-113">所有视图都在此节点中定义。</span><span class="sxs-lookup"><span data-stu-id="2df95-113">All views are defined within this node.</span></span>

3. <span data-ttu-id="2df95-114">将该文件保存到 Windows PowerShell 安装文件夹、模块文件夹或模块文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="2df95-114">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="2df95-115">保存文件时，请使用以下名称格式：  `MyFile.format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="2df95-115">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="2df95-116">格式化文件必须使用 `.format.ps1xml` 扩展名。</span><span class="sxs-lookup"><span data-stu-id="2df95-116">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="2df95-117">你现在可以将视图添加到格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="2df95-117">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="2df95-118">对于可在格式设置文件中定义的视图数没有限制。</span><span class="sxs-lookup"><span data-stu-id="2df95-118">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="2df95-119">您可以为每个对象添加单个视图、同一个对象的多个视图或多个对象使用的单个视图。</span><span class="sxs-lookup"><span data-stu-id="2df95-119">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="2df95-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2df95-120">See Also</span></span>

[<span data-ttu-id="2df95-121">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="2df95-121">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
