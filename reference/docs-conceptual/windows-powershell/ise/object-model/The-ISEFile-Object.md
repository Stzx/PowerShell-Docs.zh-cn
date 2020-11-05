---
ms.date: 12/31/2019
title: ISEFile 对象
description: ISEFile 对象表示 Windows PowerShell ISE 中的文件。
ms.openlocfilehash: 0de19c45bde7e5629d5721635150d3b0915aaa7d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662128"
---
# <a name="the-isefile-object"></a><span data-ttu-id="b2d3a-103">ISEFile 对象</span><span class="sxs-lookup"><span data-stu-id="b2d3a-103">The ISEFile Object</span></span>

<span data-ttu-id="b2d3a-104">ISEFile 对象表示 Windows PowerShell&reg; 集成脚本环境 (ISE) 中的文件。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-104">An **ISEFile** object represents a file in Windows PowerShell&reg; Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="b2d3a-105">它是 Microsoft.PowerShell.Host.ISE.ISEFile  类的实例。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEFile** class.</span></span> <span data-ttu-id="b2d3a-106">本主题列出其成员方法和成员属性。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="b2d3a-107">`$psISE.CurrentFile` 和 PowerShell 选项卡中的文件集合中的文件是 \*\***Microsoft.PowerShell.Host.ISE.ISEFile** 类的所有实例。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-107">The `$psISE.CurrentFile` and the files in the Files collection in a PowerShell tab are all instances of the \*\*\*\*Microsoft.PowerShell.Host.ISE.ISEFile\*\* class.</span></span>

## <a name="methods"></a><span data-ttu-id="b2d3a-108">方法</span><span class="sxs-lookup"><span data-stu-id="b2d3a-108">Methods</span></span>

### <a name="save-saveencoding-"></a><span data-ttu-id="b2d3a-109">Save\( \[saveEncoding\] \)</span><span class="sxs-lookup"><span data-stu-id="b2d3a-109">Save\( \[saveEncoding\] \)</span></span>

<span data-ttu-id="b2d3a-110">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-111">将该文件保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-111">Saves the file to disk.</span></span>

<span data-ttu-id="b2d3a-112">**\[saveEncoding\]** - 可选 [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx)，用于已保存文件的可选字符编码参数。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-112">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="b2d3a-113">默认值是 **UTF8** 。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-113">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b2d3a-114">例外</span><span class="sxs-lookup"><span data-stu-id="b2d3a-114">Exceptions</span></span>

- <span data-ttu-id="b2d3a-115">**System.IO.IOException** ：无法保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-115">**System.IO.IOException** : The file could not be saved.</span></span>

```powershell
# Save the file using the default encoding (UTF8)
$psISE.CurrentFile.Save()

# Save the file as ASCII.
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)

# Gets the current encoding.
$myfile = $psISE.CurrentFile
$myfile.Encoding
```

### <a name="saveasfilename-saveencoding"></a><span data-ttu-id="b2d3a-116">SaveAs\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="b2d3a-116">SaveAs\(filename, \[saveEncoding\]\)</span></span>

<span data-ttu-id="b2d3a-117">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-118">使用指定的文件名和编码保存文件。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-118">Saves the file with the specified file name and encoding.</span></span>

<span data-ttu-id="b2d3a-119">**filename** - 字符串要用于保存该文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-119">**filename** - String The name to be used to save the file.</span></span>

<span data-ttu-id="b2d3a-120">**\[saveEncoding\]** - 可选 [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx)，用于已保存文件的可选字符编码参数。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-120">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="b2d3a-121">默认值是 **UTF8** 。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-121">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b2d3a-122">例外</span><span class="sxs-lookup"><span data-stu-id="b2d3a-122">Exceptions</span></span>

- <span data-ttu-id="b2d3a-123">**System.ArgumentNullException** ： **filename** 参数为 null。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-123">**System.ArgumentNullException** : The **filename** parameter is null.</span></span>
- <span data-ttu-id="b2d3a-124">**System.ArgumentException** ： **filename** 参数为空。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-124">**System.ArgumentException** : The **filename** parameter is empty.</span></span>
- <span data-ttu-id="b2d3a-125">**System.IO.IOException** ：无法保存该文件。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-125">**System.IO.IOException** : The file could not be saved.</span></span>

```powershell
# Save the file with a full path and name.
$fullpath = "c:\temp\newname.txt"
$psISE.CurrentFile.SaveAs($fullPath)
# Save the file with a full path and name and explicitly as UTF8.
$psISE.CurrentFile.SaveAs($fullPath, [System.Text.Encoding]::UTF8)
```

## <a name="properties"></a><span data-ttu-id="b2d3a-126">属性</span><span class="sxs-lookup"><span data-stu-id="b2d3a-126">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="b2d3a-127">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b2d3a-127">DisplayName</span></span>

<span data-ttu-id="b2d3a-128">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-129">只读属性，可获取包含此文件显示名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="b2d3a-130">名称显示在编辑器顶部的  “文件”选项卡上。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="b2d3a-131">名称结尾处存在星号 `(*)` 表示文件具有未保存的更改。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-131">The presence of an asterisk `(*)` at the end of the name indicates that the file has changes that have not been saved.</span></span>

```powershell
# Shows the display name of the file.
$psISE.CurrentFile.DisplayName
```

### <a name="editor"></a><span data-ttu-id="b2d3a-132">编辑器</span><span class="sxs-lookup"><span data-stu-id="b2d3a-132">Editor</span></span>

<span data-ttu-id="b2d3a-133">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-134">只读属性，可获取用于指定文件的[编辑器对象](The-ISEEditor-Object.md)。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```powershell
# Gets the editor and the text.
$psISE.CurrentFile.Editor.Text
```

### <a name="encoding"></a><span data-ttu-id="b2d3a-135">编码</span><span class="sxs-lookup"><span data-stu-id="b2d3a-135">Encoding</span></span>

<span data-ttu-id="b2d3a-136">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-137">只读属性，可获取原始文件编码。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="b2d3a-138">这是一个 **System.Text.Encoding** 对象。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-138">This is a **System.Text.Encoding** object.</span></span>

```powershell
# Shows the encoding for the file.
$psISE.CurrentFile.Encoding
```

### <a name="fullpath"></a><span data-ttu-id="b2d3a-139">FullPath</span><span class="sxs-lookup"><span data-stu-id="b2d3a-139">FullPath</span></span>

<span data-ttu-id="b2d3a-140">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-141">只读属性，可获取指定已打开文件的完整路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```powershell
# Shows the full path for the file.
$psISE.CurrentFile.FullPath
```

### <a name="issaved"></a><span data-ttu-id="b2d3a-142">IsSaved</span><span class="sxs-lookup"><span data-stu-id="b2d3a-142">IsSaved</span></span>

<span data-ttu-id="b2d3a-143">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-144">只读布尔属性，如果在最后一次修改文件后保存了文件，则返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-144">The read-only Boolean property that returns `$true` if the file has been saved after it was last modified.</span></span>

```powershell
# Determines whether the file has been saved since it was last modified.
$myfile = $psISE.CurrentFile
$myfile.IsSaved
```

### <a name="isuntitled"></a><span data-ttu-id="b2d3a-145">IsUntitled</span><span class="sxs-lookup"><span data-stu-id="b2d3a-145">IsUntitled</span></span>

<span data-ttu-id="b2d3a-146">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b2d3a-147">只读属性，如果从未指定文件标题，则返回 `$true`。</span><span class="sxs-lookup"><span data-stu-id="b2d3a-147">The read-only property that returns `$true` if the file has never been given a title.</span></span>

```powershell
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled
```

## <a name="see-also"></a><span data-ttu-id="b2d3a-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2d3a-148">See Also</span></span>

- [<span data-ttu-id="b2d3a-149">ISEFileCollectionObject</span><span class="sxs-lookup"><span data-stu-id="b2d3a-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md)
- [<span data-ttu-id="b2d3a-150">Windows PowerShell ISE 脚本对象模型的用途</span><span class="sxs-lookup"><span data-stu-id="b2d3a-150">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="b2d3a-151">ISE 对象模型层次结构</span><span class="sxs-lookup"><span data-stu-id="b2d3a-151">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
