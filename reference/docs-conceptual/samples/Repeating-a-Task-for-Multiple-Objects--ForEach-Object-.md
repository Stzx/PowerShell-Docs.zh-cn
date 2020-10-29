---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: 为多个对象重复执行任务 (ForEach Object)
description: 使用 ForEach-Object 可为管道上传递的每个对象重复执行一组命令。
ms.openlocfilehash: 7353be833dc8bf77dd18b7fc45bdd97e092ff6ef
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499947"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="81a4b-104">为多个对象重复执行任务 (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="81a4b-104">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>

<span data-ttu-id="81a4b-105">`ForEach-Object` cmdlet 为当前管道对象使用脚本块和 `$_` 描述符，以便你可以对管道中的每个对象运行命令。</span><span class="sxs-lookup"><span data-stu-id="81a4b-105">The `ForEach-Object` cmdlet uses script blocks and the `$_` descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="81a4b-106">这可用于执行某些复杂的任务。</span><span class="sxs-lookup"><span data-stu-id="81a4b-106">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="81a4b-107">一种有帮助的情况就是操纵数据使其更为有用。</span><span class="sxs-lookup"><span data-stu-id="81a4b-107">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="81a4b-108">例如，WMI 的 Win32_LogicalDisk 类可用于返回每个本地磁盘的可用空间信息。 </span><span class="sxs-lookup"><span data-stu-id="81a4b-108">For example, the **Win32_LogicalDisk** class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="81a4b-109">返回以字节表示的数据，但是，这也将增加阅读的难度：</span><span class="sxs-lookup"><span data-stu-id="81a4b-109">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk
```

```Output
DeviceID DriveType ProviderName VolumeName Size          FreeSpace
-------- --------- ------------ ---------- ----          ---------
C:       3                      Local Disk 203912880128  50665070592
```

<span data-ttu-id="81a4b-110">通过将每个值除以 1 MB，可以将 FreeSpace 值转换为以十亿字节为单位。 </span><span class="sxs-lookup"><span data-stu-id="81a4b-110">We can convert the **FreeSpace** value to megabytes by dividing each value by 1MB.</span></span> <span data-ttu-id="81a4b-111">你可通过键入以下内容在 `ForEach-Object` 脚本块中实现此操作：</span><span class="sxs-lookup"><span data-stu-id="81a4b-111">You can do that in a `ForEach-Object` script block by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {($_.FreeSpace)/1MB}
```

```Output
48318.01171875
```

<span data-ttu-id="81a4b-112">遗憾的是，该输出现在是没有关联标签的数据。</span><span class="sxs-lookup"><span data-stu-id="81a4b-112">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="81a4b-113">因为这样的 WMI 属性为只读，所以不能直接转换 FreeSpace。 </span><span class="sxs-lookup"><span data-stu-id="81a4b-113">Because WMI properties such as this are read-only, you cannot directly convert **FreeSpace** .</span></span> <span data-ttu-id="81a4b-114">如果键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="81a4b-114">If you type this:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
```

<span data-ttu-id="81a4b-115">则将收到错误消息：</span><span class="sxs-lookup"><span data-stu-id="81a4b-115">You get an error message:</span></span>

```Output
"FreeSpace" is a ReadOnly property.
At line:2 char:28
+   ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1MB}
+                            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], SetValueException
+ FullyQualifiedErrorId : ReadOnlyCIMProperty
```

<span data-ttu-id="81a4b-116">可以通过使用一些高级技术重新组织数据，但更简单的方法是通过使用 `Select-Object` 创建新对象。</span><span class="sxs-lookup"><span data-stu-id="81a4b-116">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using `Select-Object`.</span></span>
