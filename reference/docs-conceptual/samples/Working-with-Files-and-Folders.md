---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 使用文件和文件夹
description: 本文介绍如何使用 PowerShell 处理特定文件和文件夹操作任务。
ms.openlocfilehash: c0c3abb082b05296daa480ac06bcbfa3a784e0c9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500022"
---
# <a name="working-with-files-and-folders"></a><span data-ttu-id="62d04-104">使用文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="62d04-104">Working with Files and Folders</span></span>

<span data-ttu-id="62d04-105">在 Windows PowerShell 驱动器中导航和操作其上面的项类似于操作 Windows 物理磁盘驱动器上的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="62d04-105">Navigating through Windows PowerShell drives and manipulating the items on them is similar to manipulating files and folders on Windows physical disk drives.</span></span> <span data-ttu-id="62d04-106">本文介绍如何使用 PowerShell 处理特定文件和文件夹操作任务。</span><span class="sxs-lookup"><span data-stu-id="62d04-106">This article discusses how to deal with specific file and folder manipulation tasks using PowerShell.</span></span>

## <a name="listing-all-the-files-and-folders-within-a-folder"></a><span data-ttu-id="62d04-107">列出某个文件夹内的所有文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="62d04-107">Listing All the Files and Folders Within a Folder</span></span>

<span data-ttu-id="62d04-108">可以使用 `Get-ChildItem` 来直接获取文件夹中的所有项。</span><span class="sxs-lookup"><span data-stu-id="62d04-108">You can get all items directly within a folder by using `Get-ChildItem`.</span></span> <span data-ttu-id="62d04-109">添加可选的 **Force** 参数以显示隐藏项或系统项。</span><span class="sxs-lookup"><span data-stu-id="62d04-109">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="62d04-110">例如，此命令将显示 Windows PowerShell 驱动器 C（它与 Windows 物理驱动器 C 相同）的直观内容：</span><span class="sxs-lookup"><span data-stu-id="62d04-110">For example, this command displays the direct contents of Windows PowerShell Drive C (which is the same as the Windows physical drive C):</span></span>

```powershell
Get-ChildItem -Path C:\ -Force
```

<span data-ttu-id="62d04-111">此命令只列出直接包含的项，很像使用 `Cmd.exe` 的 `DIR` 命令或 UNIX shell 中的 `ls`。</span><span class="sxs-lookup"><span data-stu-id="62d04-111">The command lists only the directly contained items, much like using `Cmd.exe`'s `DIR` command or `ls` in a UNIX shell.</span></span> <span data-ttu-id="62d04-112">为了显示包含的项，还需要指定 `-Recurse` 参数。</span><span class="sxs-lookup"><span data-stu-id="62d04-112">In order to show contained items, you need to specify the `-Recurse` parameter as well.</span></span> <span data-ttu-id="62d04-113">（这可能需要相当长的时间才能完成。）列出 C 驱动器上的所有内容：</span><span class="sxs-lookup"><span data-stu-id="62d04-113">(This can take an extremely long time to complete.) To list everything on the C drive:</span></span>

```powershell
Get-ChildItem -Path C:\ -Force -Recurse
```

<span data-ttu-id="62d04-114">`Get-ChildItem` 可以使用 Path  、Filter  、Include  和 Exclude  参数来筛选项，但这些通常只以名称为依据。</span><span class="sxs-lookup"><span data-stu-id="62d04-114">`Get-ChildItem` can filter items with its **Path** , **Filter** , **Include** , and **Exclude** parameters, but those are typically based only on name.</span></span> <span data-ttu-id="62d04-115">使用 `Where-Object`，还可以执行基于项的其他属性的复杂筛选。</span><span class="sxs-lookup"><span data-stu-id="62d04-115">You can perform complex filtering based on other properties of items by using `Where-Object`.</span></span>

<span data-ttu-id="62d04-116">下面的命令用于查找上次于 2005 年 10 月 1 日之后修改，并且不小于 1 兆字节，也不大于 10 兆字节的 Program Files 文件夹中的所有可执行文件：</span><span class="sxs-lookup"><span data-stu-id="62d04-116">The following command finds all executables within the Program Files folder that were last modified after October 1, 2005 and which are neither smaller than 1 megabyte nor larger than 10 megabytes:</span></span>

```powershell
Get-ChildItem -Path $env:ProgramFiles -Recurse -Include *.exe | Where-Object -FilterScript {($_.LastWriteTime -gt '2005-10-01') -and ($_.Length -ge 1mb) -and ($_.Length -le 10mb)}
```

## <a name="copying-files-and-folders"></a><span data-ttu-id="62d04-117">复制文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="62d04-117">Copying Files and Folders</span></span>

<span data-ttu-id="62d04-118">复制通过 `Copy-Item` 完成。</span><span class="sxs-lookup"><span data-stu-id="62d04-118">Copying is done with `Copy-Item`.</span></span> <span data-ttu-id="62d04-119">以下命令用于将 C:\\boot.ini 备份到 C:\\boot.bak：</span><span class="sxs-lookup"><span data-stu-id="62d04-119">The following command backs up C:\\boot.ini to C:\\boot.bak:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak
```

<span data-ttu-id="62d04-120">如果目标文件已存在，则复制尝试失败。</span><span class="sxs-lookup"><span data-stu-id="62d04-120">If the destination file already exists, the copy attempt fails.</span></span> <span data-ttu-id="62d04-121">若要覆盖预先存在的目标，请使用 Force 参数  ：</span><span class="sxs-lookup"><span data-stu-id="62d04-121">To overwrite a pre-existing destination, use the **Force** parameter:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak -Force
```

<span data-ttu-id="62d04-122">即使当目标为只读时，该命令也有效。</span><span class="sxs-lookup"><span data-stu-id="62d04-122">This command works even when the destination is read-only.</span></span>

<span data-ttu-id="62d04-123">复制文件夹的操作方式与此相同。</span><span class="sxs-lookup"><span data-stu-id="62d04-123">Folder copying works the same way.</span></span> <span data-ttu-id="62d04-124">以下命令以递归方式将文件夹 `C:\temp\test1` 复制到新文件夹 `C:\temp\DeleteMe`：</span><span class="sxs-lookup"><span data-stu-id="62d04-124">This command copies the folder `C:\temp\test1` to the new folder `C:\temp\DeleteMe` recursively:</span></span>

```powershell
Copy-Item C:\temp\test1 -Recurse C:\temp\DeleteMe
```

<span data-ttu-id="62d04-125">还可以复制选定的项。</span><span class="sxs-lookup"><span data-stu-id="62d04-125">You can also copy a selection of items.</span></span> <span data-ttu-id="62d04-126">以下命令将 `C:\data` 中任意位置包含的所有 .txt 文件都复制到 `C:\temp\text`：</span><span class="sxs-lookup"><span data-stu-id="62d04-126">The following command copies all .txt files contained anywhere in `C:\data` to `C:\temp\text`:</span></span>

```powershell
Copy-Item -Filter *.txt -Path c:\data -Recurse -Destination C:\temp\text
```

<span data-ttu-id="62d04-127">你仍然可以使用其他工具执行文件系统复制。</span><span class="sxs-lookup"><span data-stu-id="62d04-127">You can still use other tools to perform file system copies.</span></span> <span data-ttu-id="62d04-128">XCOPY、ROBOCOPY 和 COM 对象（如 **Scripting.FileSystemObject** ）都适用于 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="62d04-128">XCOPY, ROBOCOPY, and COM objects, such as the **Scripting.FileSystemObject,** all work in Windows PowerShell.</span></span> <span data-ttu-id="62d04-129">例如，可以使用 Windows 脚本宿主 Scripting.FileSystem COM  类将 `C:\boot.ini` 备份到 `C:\boot.bak`：</span><span class="sxs-lookup"><span data-stu-id="62d04-129">For example, you can use the Windows Script Host **Scripting.FileSystem COM** class to back up `C:\boot.ini` to `C:\boot.bak`:</span></span>

```powershell
(New-Object -ComObject Scripting.FileSystemObject).CopyFile('C:\boot.ini', 'C:\boot.bak')
```

## <a name="creating-files-and-folders"></a><span data-ttu-id="62d04-130">创建文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="62d04-130">Creating Files and Folders</span></span>

<span data-ttu-id="62d04-131">创建新项的操作方式在所有 Windows PowerShell 提供程序上都相同。</span><span class="sxs-lookup"><span data-stu-id="62d04-131">Creating new items works the same on all Windows PowerShell providers.</span></span> <span data-ttu-id="62d04-132">如果某个 Windows PowerShell 提供程序具有多个类型的项（例如，用于区分目录和文件的 FileSystem Windows PowerShell 提供程序），则需要指定项类型。</span><span class="sxs-lookup"><span data-stu-id="62d04-132">If a Windows PowerShell provider has more than one type of item—for example, the FileSystem Windows PowerShell provider distinguishes between directories and files—you need to specify the item type.</span></span>

<span data-ttu-id="62d04-133">以下命令新建文件夹 `C:\temp\New Folder`：</span><span class="sxs-lookup"><span data-stu-id="62d04-133">This command creates a new folder `C:\temp\New Folder`:</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder' -ItemType Directory
```

<span data-ttu-id="62d04-134">以下命令新建空的文件 `C:\temp\New Folder\file.txt`</span><span class="sxs-lookup"><span data-stu-id="62d04-134">This command creates a new empty file `C:\temp\New Folder\file.txt`</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder\file.txt' -ItemType File
```

> [!IMPORTANT]
> <span data-ttu-id="62d04-135">结合使用 Force  开关与 `New-Item` 命令来创建文件夹时，如果文件夹已存在，则不会  覆盖或替换此文件夹。</span><span class="sxs-lookup"><span data-stu-id="62d04-135">When using the **Force** switch with the `New-Item` command to create a folder, and the folder already exists, it _won't_ overwrite or replace the folder.</span></span> <span data-ttu-id="62d04-136">它会直接返回现有的文件夹对象。</span><span class="sxs-lookup"><span data-stu-id="62d04-136">It will simply return the existing folder object.</span></span> <span data-ttu-id="62d04-137">不过，如果对已存在的文件使用 `New-Item -Force`，此文件  会被完全覆盖。</span><span class="sxs-lookup"><span data-stu-id="62d04-137">However, if you use `New-Item -Force` on a file that already exists, the file _will_ be completely overwritten.</span></span>

## <a name="removing-all-files-and-folders-within-a-folder"></a><span data-ttu-id="62d04-138">删除某个文件夹内的所有文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="62d04-138">Removing All Files and Folders Within a Folder</span></span>

<span data-ttu-id="62d04-139">可以使用 `Remove-Item` 来删除包含的项，但如果项包含其他任何内容，系统就会提示你确认是否要删除。</span><span class="sxs-lookup"><span data-stu-id="62d04-139">You can remove contained items using `Remove-Item`, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="62d04-140">例如，如果尝试删除包含其他项的文件夹 `C:\temp\DeleteMe`，则在删除此文件夹前，Windows PowerShell 会提示你确认是否要删除：</span><span class="sxs-lookup"><span data-stu-id="62d04-140">For example, if you attempt to delete the folder `C:\temp\DeleteMe` that contains other items, Windows PowerShell prompts you for confirmation before deleting the folder:</span></span>

```
Remove-Item -Path C:\temp\DeleteMe

Confirm
The item at C:\temp\DeleteMe has children and the Recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="62d04-141">如果不希望系统针对每个包含的项都提示你，则指定 **Recurse** 参数：</span><span class="sxs-lookup"><span data-stu-id="62d04-141">If you do not want to be prompted for each contained item, specify the **Recurse** parameter:</span></span>

```powershell
Remove-Item -Path C:\temp\DeleteMe -Recurse
```

## <a name="mapping-a-local-folder-as-a-drive"></a><span data-ttu-id="62d04-142">将本地文件夹映射为驱动器</span><span class="sxs-lookup"><span data-stu-id="62d04-142">Mapping a Local Folder as a drive</span></span>

<span data-ttu-id="62d04-143">还可以使用 `New-PSDrive` 命令来映射本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="62d04-143">You can also map a local folder, using the `New-PSDrive` command.</span></span> <span data-ttu-id="62d04-144">以下命令在本地 Program Files 目录中的根位置创建本地驱动器 `P:`（只在 PowerShell 会话中可见）：</span><span class="sxs-lookup"><span data-stu-id="62d04-144">The following command creates a local drive `P:` rooted in the local Program Files directory, visible only from the PowerShell session:</span></span>

```powershell
New-PSDrive -Name P -Root $env:ProgramFiles -PSProvider FileSystem
```

<span data-ttu-id="62d04-145">正如网络驱动器一样，在 Windows PowerShell 内映射的驱动器将对 Windows PowerShell shell 立即可见。</span><span class="sxs-lookup"><span data-stu-id="62d04-145">Just as with network drives, drives mapped within Windows PowerShell are immediately visible to the Windows PowerShell shell.</span></span> <span data-ttu-id="62d04-146">若要创建在文件资源管理器中可见的映射驱动器，需要使用参数 `-Persist`。</span><span class="sxs-lookup"><span data-stu-id="62d04-146">In order to create a mapped drive visible from File Explorer, the parameter `-Persist` is needed.</span></span> <span data-ttu-id="62d04-147">但是，只有远程路径才能与 Persist 一起使用。</span><span class="sxs-lookup"><span data-stu-id="62d04-147">However, only remote paths can be used with Persist.</span></span>

## <a name="reading-a-text-file-into-an-array"></a><span data-ttu-id="62d04-148">将文本文件数据读取到数组中</span><span class="sxs-lookup"><span data-stu-id="62d04-148">Reading a Text File into an Array</span></span>

<span data-ttu-id="62d04-149">文本数据更常见的存储格式之一是采用文件形式，其中单独的行被视为不同的数据元素。</span><span class="sxs-lookup"><span data-stu-id="62d04-149">One of the more common storage formats for text data is in a file with separate lines treated as distinct data elements.</span></span> <span data-ttu-id="62d04-150">`Get-Content` cmdlet 可用于一步读取整个文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="62d04-150">The `Get-Content` cmdlet can be used to read an entire file in one step, as shown here:</span></span>

```
PS> Get-Content -Path C:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS="Microsoft Windows XP Professional"
 /noexecute=AlwaysOff /fastdetect
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS=" Microsoft Windows XP Professional
with Data Execution Prevention" /noexecute=optin /fastdetect
```

<span data-ttu-id="62d04-151">`Get-Content` 已将从文件读取的数据视为数组，其中每行文件内容为一个元素。</span><span class="sxs-lookup"><span data-stu-id="62d04-151">`Get-Content` already treats the data read from the file as an array, with one element per line of file content.</span></span> <span data-ttu-id="62d04-152">可以通过检查返回的内容的 **长度** 来确认此点：</span><span class="sxs-lookup"><span data-stu-id="62d04-152">You can confirm this by checking the **Length** of the returned content:</span></span>

```
PS> (Get-Content -Path C:\boot.ini).Length
6
```

<span data-ttu-id="62d04-153">此命令对于直接从 Windows PowerShell 获取列表信息最为有用。</span><span class="sxs-lookup"><span data-stu-id="62d04-153">This command is most useful for getting lists of information into Windows PowerShell directly.</span></span> <span data-ttu-id="62d04-154">例如，你可能会在文件 `C:\temp\domainMembers.txt` 中存储计算机名或 IP 地址的列表，文件的每一行上都有一个名称。</span><span class="sxs-lookup"><span data-stu-id="62d04-154">For example, you might store a list of computer names or IP addresses in a file `C:\temp\domainMembers.txt`, with one name on each line of the file.</span></span> <span data-ttu-id="62d04-155">可以使用 `Get-Content` 来检索文件内容，并将它们放置在变量 `$Computers` 中：</span><span class="sxs-lookup"><span data-stu-id="62d04-155">You can use `Get-Content` to retrieve the file contents and put them in the variable `$Computers`:</span></span>

```powershell
$Computers = Get-Content -Path C:\temp\DomainMembers.txt
```

<span data-ttu-id="62d04-156">`$Computers` 现在是数组，其中每个元素包含一个计算机名。</span><span class="sxs-lookup"><span data-stu-id="62d04-156">`$Computers` is now an array containing a computer name in each element.</span></span>
