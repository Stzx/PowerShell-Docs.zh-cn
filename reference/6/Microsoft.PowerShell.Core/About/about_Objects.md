---
description: 提供有关 PowerShell 中的对象的基本信息。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: 152234de5e4f55f63b70ee9775bba0c5c9977f84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199797"
---
# <a name="about-objects"></a><span data-ttu-id="ea269-104">关于对象</span><span class="sxs-lookup"><span data-stu-id="ea269-104">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="ea269-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="ea269-105">Short Description</span></span>
<span data-ttu-id="ea269-106">提供有关 PowerShell 中的对象的基本信息。</span><span class="sxs-lookup"><span data-stu-id="ea269-106">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ea269-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="ea269-107">Long Description</span></span>

<span data-ttu-id="ea269-108">在 PowerShell 中执行的每个操作都在对象的上下文中发生。</span><span class="sxs-lookup"><span data-stu-id="ea269-108">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="ea269-109">当数据从一个命令移到下一个命令时，它将作为一个或多个可识别对象移动。</span><span class="sxs-lookup"><span data-stu-id="ea269-109">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="ea269-110">对象是表示项的数据集合。</span><span class="sxs-lookup"><span data-stu-id="ea269-110">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="ea269-111">对象由三种类型的数据组成：对象类型、对象的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="ea269-111">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="ea269-112">类型、方法和属性</span><span class="sxs-lookup"><span data-stu-id="ea269-112">Types, Methods, and Properties</span></span>

<span data-ttu-id="ea269-113">对象类型告诉对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ea269-113">The object type tells what kind of object it is.</span></span> <span data-ttu-id="ea269-114">例如，表示文件的对象是一个 FileInfo 对象。</span><span class="sxs-lookup"><span data-stu-id="ea269-114">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="ea269-115">对象方法是可对对象执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ea269-115">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="ea269-116">例如，FileInfo 对象具有可用于复制文件的 CopyTo 方法。</span><span class="sxs-lookup"><span data-stu-id="ea269-116">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="ea269-117">对象属性存储有关对象的信息。</span><span class="sxs-lookup"><span data-stu-id="ea269-117">Object properties store information about the object.</span></span> <span data-ttu-id="ea269-118">例如，FileInfo 对象具有 LastWriteTime 属性，该属性存储最近一次访问该文件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ea269-118">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="ea269-119">使用对象时，可以使用命令中的方法和属性来执行操作和管理数据。</span><span class="sxs-lookup"><span data-stu-id="ea269-119">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="ea269-120">管道中的对象</span><span class="sxs-lookup"><span data-stu-id="ea269-120">Objects in Pipelines</span></span>

<span data-ttu-id="ea269-121">当命令合并到管道中时，它们会将信息互相传递为对象。</span><span class="sxs-lookup"><span data-stu-id="ea269-121">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="ea269-122">第一条命令运行时，它将一个或多个对象向下移动到第二个命令。</span><span class="sxs-lookup"><span data-stu-id="ea269-122">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="ea269-123">第二个命令从第一个命令接收对象，处理对象，然后将新的或已修改的对象传递到管道中的下一个命令。</span><span class="sxs-lookup"><span data-stu-id="ea269-123">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="ea269-124">此过程将一直继续，直到管道中的所有命令都运行为止。</span><span class="sxs-lookup"><span data-stu-id="ea269-124">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="ea269-125">下面的示例演示如何将对象从一个命令传递到下一个命令：</span><span class="sxs-lookup"><span data-stu-id="ea269-125">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="ea269-126">第一个命令 `Get-ChildItem C:` 为文件系统的根目录中的每个项返回一个文件或目录对象。</span><span class="sxs-lookup"><span data-stu-id="ea269-126">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="ea269-127">文件和目录对象通过管道向下传递到第二个命令。</span><span class="sxs-lookup"><span data-stu-id="ea269-127">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="ea269-128">第二个命令 `where { $_.PsIsContainer -eq $false }` 使用所有文件系统对象的 PsIsContainer 属性来仅选择文件，这些文件的 PsIsContainer 属性中的值为 false (\$ false) 。</span><span class="sxs-lookup"><span data-stu-id="ea269-128">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="ea269-129">文件夹是容器，因此，它们的 PsIsContainer 属性中的值为 True (\$ true) 。</span><span class="sxs-lookup"><span data-stu-id="ea269-129">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="ea269-130">第二个命令仅将文件对象传递给第三个命令 `Format-List` ，后者将在列表中显示文件对象。</span><span class="sxs-lookup"><span data-stu-id="ea269-130">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea269-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea269-131">See Also</span></span>

[<span data-ttu-id="ea269-132">about_Methods</span><span class="sxs-lookup"><span data-stu-id="ea269-132">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="ea269-133">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="ea269-133">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="ea269-134">about_Properties</span><span class="sxs-lookup"><span data-stu-id="ea269-134">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="ea269-135">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="ea269-135">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="ea269-136">Get-Member</span><span class="sxs-lookup"><span data-stu-id="ea269-136">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
