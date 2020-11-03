---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 3bfa1db6d8ad14a5681e22f2708d6c69dc165d3d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198876"
---
# <span data-ttu-id="d67d0-103">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="d67d0-103">Compress-Archive</span></span>

## <span data-ttu-id="d67d0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d67d0-104">SYNOPSIS</span></span>
<span data-ttu-id="d67d0-105">从指定的文件和目录创建压缩的存档文件或压缩文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-105">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="d67d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d67d0-106">SYNTAX</span></span>

### <span data-ttu-id="d67d0-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="d67d0-107">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d67d0-108">PathWithUpdate</span><span class="sxs-lookup"><span data-stu-id="d67d0-108">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d67d0-109">PathWithForce</span><span class="sxs-lookup"><span data-stu-id="d67d0-109">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d67d0-110">LiteralPathWithUpdate</span><span class="sxs-lookup"><span data-stu-id="d67d0-110">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d67d0-111">LiteralPathWithForce</span><span class="sxs-lookup"><span data-stu-id="d67d0-111">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d67d0-112">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d67d0-112">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d67d0-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d67d0-113">DESCRIPTION</span></span>

<span data-ttu-id="d67d0-114">`Compress-Archive`Cmdlet 从一个或多个指定的文件或目录创建压缩文件或压缩文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-114">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="d67d0-115">存档将多个文件（具有可选压缩）打包到一个压缩文件中，以便于分发和存储。</span><span class="sxs-lookup"><span data-stu-id="d67d0-115">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="d67d0-116">可以使用 **CompressionLevel** 参数指定的压缩算法来压缩存档文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-116">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="d67d0-117">`Compress-Archive`Cmdlet 使用 MICROSOFT .NET API [System.IO.Compression.Zip存档](/dotnet/api/system.io.compression.ziparchive)来压缩文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-117">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="d67d0-118">最大文件大小为 2 GB，因为存在基础 API 限制。</span><span class="sxs-lookup"><span data-stu-id="d67d0-118">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="d67d0-119">一些示例使用展开来减少代码示例的行长度。</span><span class="sxs-lookup"><span data-stu-id="d67d0-119">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="d67d0-120">有关详细信息，请参阅 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="d67d0-120">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="d67d0-121">示例</span><span class="sxs-lookup"><span data-stu-id="d67d0-121">EXAMPLES</span></span>

### <span data-ttu-id="d67d0-122">示例1：压缩文件以创建存档文件</span><span class="sxs-lookup"><span data-stu-id="d67d0-122">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="d67d0-123">此示例压缩来自不同目录的文件，并创建存档文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-123">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="d67d0-124">通配符用于获取具有特定文件扩展名的所有文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-124">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="d67d0-125">存档文件中没有目录结构，因为该 **路径** 仅指定文件名。</span><span class="sxs-lookup"><span data-stu-id="d67d0-125">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="d67d0-126">**Path** 参数接受带有通配符的特定文件名和文件名 `*.vsd` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-126">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="d67d0-127">**路径** 使用以逗号分隔的列表从不同的目录中获取文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-127">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="d67d0-128">压缩级别是 **最快** 的，可减少处理时间。</span><span class="sxs-lookup"><span data-stu-id="d67d0-128">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="d67d0-129">**DestinationPath** 参数指定文件的位置 `Draft.zip` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-129">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="d67d0-130">`Draft.zip`文件包含扩展名为的文件 `Draftdoc.docx` 以及所有文件 `.vsd` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-130">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="d67d0-131">示例2：使用 LiteralPath 压缩文件</span><span class="sxs-lookup"><span data-stu-id="d67d0-131">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="d67d0-132">此示例将压缩特定的命名文件并创建一个新的存档文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-132">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="d67d0-133">存档文件中没有目录结构，因为该 **路径** 仅指定文件名。</span><span class="sxs-lookup"><span data-stu-id="d67d0-133">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="d67d0-134">使用绝对路径和文件名，因为 **LiteralPath** 参数不接受通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-134">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="d67d0-135">**路径** 使用以逗号分隔的列表从不同的目录中获取文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-135">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="d67d0-136">压缩级别是 **最快** 的，可减少处理时间。</span><span class="sxs-lookup"><span data-stu-id="d67d0-136">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="d67d0-137">**DestinationPath** 参数指定文件的位置 `Draft.zip` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-137">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="d67d0-138">`Draft.zip`文件仅包含 `Draftdoc.docx` 和 `diagram2.vsd` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-138">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="d67d0-139">示例3：压缩包含根目录的目录</span><span class="sxs-lookup"><span data-stu-id="d67d0-139">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="d67d0-140">此示例将压缩目录，并创建 **包含** 根目录及其所有文件和子目录的存档文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-140">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="d67d0-141">存档文件具有目录结构，因为 **路径** 指定了根目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-141">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="d67d0-142">`Compress-Archive` 使用 **Path** 参数指定根目录 `C:\Reference` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-142">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="d67d0-143">**DestinationPath** 参数指定存档文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d67d0-143">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="d67d0-144">`Draft.zip`存档包括 `Reference` 根目录及其所有文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-144">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="d67d0-145">示例4：压缩排除根目录的目录</span><span class="sxs-lookup"><span data-stu-id="d67d0-145">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="d67d0-146">此示例将压缩目录，并创建一个 **排除** 根目录的存档文件，因为 **路径** 使用的星号 (`*`) 通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-146">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="d67d0-147">存档包含包含根目录文件和子目录的目录结构。</span><span class="sxs-lookup"><span data-stu-id="d67d0-147">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="d67d0-148">`Compress-Archive` 使用 **Path** 参数指定根目录， `C:\Reference` 其中星号 (`*`) 通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-148">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="d67d0-149">**DestinationPath** 参数指定存档文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d67d0-149">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="d67d0-150">`Draft.zip`存档包含根目录的文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-150">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="d67d0-151">`Reference`从存档中排除了根目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-151">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="d67d0-152">示例5：仅压缩根目录中的文件</span><span class="sxs-lookup"><span data-stu-id="d67d0-152">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="d67d0-153">此示例仅压缩根目录中的文件，并创建存档文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-153">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="d67d0-154">存档中没有目录结构，因为只有文件被压缩。</span><span class="sxs-lookup"><span data-stu-id="d67d0-154">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="d67d0-155">`Compress-Archive` 使用 **Path** 参数指定根目录， `C:\Reference` 并将 **星形** (`*.*`) 通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-155">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="d67d0-156">**DestinationPath** 参数指定存档文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d67d0-156">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="d67d0-157">`Draft.zip`存档只包含 `Reference` 根目录文件，并排除根目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-157">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="d67d0-158">示例6：使用管道对文件进行存档</span><span class="sxs-lookup"><span data-stu-id="d67d0-158">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="d67d0-159">此示例将文件沿管道向下发送，以创建存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-159">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="d67d0-160">存档文件中没有目录结构，因为该 **路径** 仅指定文件名。</span><span class="sxs-lookup"><span data-stu-id="d67d0-160">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="d67d0-161">`Get-ChildItem` 使用 **Path** 参数指定不同目录中的两个文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-161">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="d67d0-162">每个文件由一个 **FileInfo** 对象表示，并沿管道向下发送到 `Compress-Archive` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-162">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="d67d0-163">在中存档两个指定的文件 `PipelineFiles.zip` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-163">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="d67d0-164">示例7：使用管道将目录存档</span><span class="sxs-lookup"><span data-stu-id="d67d0-164">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="d67d0-165">此示例向下发送目录，以创建存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-165">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="d67d0-166">文件作为 **FileInfo** 对象和目录作为 **DirectoryInfo** 对象发送。</span><span class="sxs-lookup"><span data-stu-id="d67d0-166">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="d67d0-167">存档的目录结构不包含根目录，但其文件和子目录都包括在存档中。</span><span class="sxs-lookup"><span data-stu-id="d67d0-167">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="d67d0-168">`Get-ChildItem` 使用 **Path** 参数指定 `C:\LogFiles` 根目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-168">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="d67d0-169">每个 **FileInfo** 和 **DirectoryInfo** 对象都沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="d67d0-169">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="d67d0-170">`Compress-Archive` 将每个对象添加到 `PipelineDir.zip` 存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-170">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="d67d0-171">未指定 **Path** 参数，因为管道对象收到参数位置0。</span><span class="sxs-lookup"><span data-stu-id="d67d0-171">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="d67d0-172">示例8：递归如何影响存档</span><span class="sxs-lookup"><span data-stu-id="d67d0-172">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="d67d0-173">此示例演示递归如何在存档中复制文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-173">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="d67d0-174">例如，如果将 `Get-ChildItem` 与 **递归** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="d67d0-174">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="d67d0-175">作为递归过程，每个 **FileInfo** 和 **DirectoryInfo** 对象都向下发送到该管道并添加到存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-175">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="d67d0-176">`C:\TestLog`目录不包含任何文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-176">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="d67d0-177">它包含一个 `testsub` 包含文件的名为的子目录 `testlog.txt` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-177">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="d67d0-178">`Get-ChildItem` 使用 **Path** 参数指定根目录 `C:\TestLog` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-178">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="d67d0-179">**递归** 参数处理文件和目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-179">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="d67d0-180">为 **DirectoryInfo** `testsub` 和 **FileInfo** 对象创建 DirectoryInfo 对象 `testlog.txt` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-180">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="d67d0-181">每个对象都向下发送到 `Compress-Archive` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-181">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="d67d0-182">**DestinationPath** 指定存档文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d67d0-182">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="d67d0-183">未指定 **Path** 参数，因为管道对象收到参数位置0。</span><span class="sxs-lookup"><span data-stu-id="d67d0-183">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="d67d0-184">以下摘要说明了 `PipelineRecurse.zip` 包含重复文件的存档内容：</span><span class="sxs-lookup"><span data-stu-id="d67d0-184">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="d67d0-185">**DirectoryInfo** 对象创建 `testsub` 目录并包含 `testlog.txt` 文件，该文件反映了原始目录结构。</span><span class="sxs-lookup"><span data-stu-id="d67d0-185">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="d67d0-186">**FileInfo** 对象 `testlog.txt` 在存档的根中创建一个重复项。</span><span class="sxs-lookup"><span data-stu-id="d67d0-186">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="d67d0-187">由于递归将文件对象发送到，因此会创建重复的文件 `Compress-Archive` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-187">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="d67d0-188">此行为是预期行为，因为管道下发送的每个对象都会添加到存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-188">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="d67d0-189">示例9：更新现有存档文件</span><span class="sxs-lookup"><span data-stu-id="d67d0-189">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="d67d0-190">此示例将更新目录中的现有存档文件 `Draft.Zip` `C:\Archives` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-190">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="d67d0-191">在此示例中，现有存档文件包含根目录及其文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-191">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="d67d0-192">命令会更新 `Draft.Zip` 目录及其子目录中的现有文件的较新版本 `C:\Reference` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-192">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="d67d0-193">而且，已添加到 `C:\Reference` 或其子目录中的新文件将包含在更新的 `Draft.Zip` 存档中。</span><span class="sxs-lookup"><span data-stu-id="d67d0-193">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="d67d0-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d67d0-194">PARAMETERS</span></span>

### <span data-ttu-id="d67d0-195">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="d67d0-195">-CompressionLevel</span></span>

<span data-ttu-id="d67d0-196">指定创建存档文件时要应用的压缩量。</span><span class="sxs-lookup"><span data-stu-id="d67d0-196">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="d67d0-197">较快的压缩需要的文件创建时间较少，但可能导致文件大小较大。</span><span class="sxs-lookup"><span data-stu-id="d67d0-197">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="d67d0-198">如果未指定此参数，则该命令将使用默认值 " **最佳** "。</span><span class="sxs-lookup"><span data-stu-id="d67d0-198">If this parameter isn't specified, the command uses the default value, **Optimal** .</span></span>

<span data-ttu-id="d67d0-199">以下是此参数可接受的值：</span><span class="sxs-lookup"><span data-stu-id="d67d0-199">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="d67d0-200">**最快** 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-200">**Fastest** .</span></span> <span data-ttu-id="d67d0-201">使用最快的压缩方法可减少处理时间。</span><span class="sxs-lookup"><span data-stu-id="d67d0-201">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="d67d0-202">更快的压缩可能导致文件大小较大。</span><span class="sxs-lookup"><span data-stu-id="d67d0-202">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="d67d0-203">**NoCompression** 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-203">**NoCompression** .</span></span> <span data-ttu-id="d67d0-204">不压缩源文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-204">Doesn't compress the source files.</span></span>
- <span data-ttu-id="d67d0-205">**最佳** ：</span><span class="sxs-lookup"><span data-stu-id="d67d0-205">**Optimal** .</span></span> <span data-ttu-id="d67d0-206">处理时间取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="d67d0-206">Processing time is dependent on file size.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d67d0-207">-Confirm</span></span>

<span data-ttu-id="d67d0-208">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="d67d0-208">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-209">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="d67d0-209">-DestinationPath</span></span>

<span data-ttu-id="d67d0-210">此参数是必需的，它指定存档输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d67d0-210">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="d67d0-211">**DestinationPath** 应包含压缩文件的名称，以及压缩文件的绝对或相对路径。</span><span class="sxs-lookup"><span data-stu-id="d67d0-211">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="d67d0-212">如果 **DestinationPath** 中的文件名没有 `.zip` 文件扩展名，则该 cmdlet 将添加 `.zip` 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="d67d0-212">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-213">-Force</span><span class="sxs-lookup"><span data-stu-id="d67d0-213">-Force</span></span>

<span data-ttu-id="d67d0-214">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="d67d0-214">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-215">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d67d0-215">-LiteralPath</span></span>

<span data-ttu-id="d67d0-216">指定想要添加到存档压缩文件的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d67d0-216">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="d67d0-217">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="d67d0-217">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="d67d0-218">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-218">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d67d0-219">如果路径包含转义符，请将每个转义符括在单引号内，以指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="d67d0-219">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="d67d0-220">若要指定多个路径，并将文件包括在输出压缩文件的多个位置中，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="d67d0-220">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-221">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d67d0-221">-PassThru</span></span>

<span data-ttu-id="d67d0-222">使 cmdlet 输出一个表示已创建的存档文件的文件对象。</span><span class="sxs-lookup"><span data-stu-id="d67d0-222">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="d67d0-223">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d67d0-223">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-224">-Path</span><span class="sxs-lookup"><span data-stu-id="d67d0-224">-Path</span></span>

<span data-ttu-id="d67d0-225">指定想要添加到存档压缩文件的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d67d0-225">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="d67d0-226">若要指定多个路径，并将文件包含在多个位置，请使用逗号分隔这些路径。</span><span class="sxs-lookup"><span data-stu-id="d67d0-226">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="d67d0-227">此参数接受通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-227">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="d67d0-228">通配符用于将目录中的所有文件添加到存档文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-228">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="d67d0-229">将通配符用于根目录会影响存档内容：</span><span class="sxs-lookup"><span data-stu-id="d67d0-229">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="d67d0-230">若要创建 **包含** 根目录及其所有文件和子目录的存档，请在不带通配符的 **路径** 中指定根目录。</span><span class="sxs-lookup"><span data-stu-id="d67d0-230">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="d67d0-231">例如：`-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="d67d0-231">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="d67d0-232">若要创建 **排除** 根目录的存档，但 zips 所有文件和子目录，请使用星号 (`*`) 通配符。</span><span class="sxs-lookup"><span data-stu-id="d67d0-232">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="d67d0-233">例如：`-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="d67d0-233">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="d67d0-234">若要创建仅 zips 根目录中的文件的存档，请使用) 通配符 ( **星形** `*.*` 。</span><span class="sxs-lookup"><span data-stu-id="d67d0-234">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="d67d0-235">根中的子目录不包括在存档中。</span><span class="sxs-lookup"><span data-stu-id="d67d0-235">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="d67d0-236">例如：`-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="d67d0-236">For example: `-Path C:\Reference\*.*`</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d67d0-237">-Update</span><span class="sxs-lookup"><span data-stu-id="d67d0-237">-Update</span></span>

<span data-ttu-id="d67d0-238">通过使用具有相同名称的较新文件版本替换存档中较旧的文件版本来更新指定的存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-238">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="d67d0-239">此外，还可添加此参数，将文件添加到现有存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-239">You can also add this parameter to add files to an existing archive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-240">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d67d0-240">-WhatIf</span></span>

<span data-ttu-id="d67d0-241">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d67d0-241">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d67d0-242">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="d67d0-242">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d67d0-243">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d67d0-243">CommonParameters</span></span>

<span data-ttu-id="d67d0-244">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d67d0-244">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d67d0-245">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="d67d0-245">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d67d0-246">输入</span><span class="sxs-lookup"><span data-stu-id="d67d0-246">INPUTS</span></span>

### <span data-ttu-id="d67d0-247">System.String</span><span class="sxs-lookup"><span data-stu-id="d67d0-247">System.String</span></span>

<span data-ttu-id="d67d0-248">可以通过管道将包含路径的字符串传递给一个或多个文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-248">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="d67d0-249">输出</span><span class="sxs-lookup"><span data-stu-id="d67d0-249">OUTPUTS</span></span>

### <span data-ttu-id="d67d0-250">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="d67d0-250">System.IO.FileInfo</span></span>

<span data-ttu-id="d67d0-251">当使用 **PassThru** 参数时，该 cmdlet 仅返回 **FileInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="d67d0-251">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="d67d0-252">注释</span><span class="sxs-lookup"><span data-stu-id="d67d0-252">NOTES</span></span>

<span data-ttu-id="d67d0-253">使用递归并沿管道向下发送对象可以在存档中复制文件。</span><span class="sxs-lookup"><span data-stu-id="d67d0-253">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="d67d0-254">例如，如果将 `Get-ChildItem` 与 **递归** 参数一起使用，则在管道中发送的每个 **FileInfo** 和 **DirectoryInfo** 对象将添加到存档。</span><span class="sxs-lookup"><span data-stu-id="d67d0-254">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="d67d0-255">[ZIP 文件规范](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)未指定对包含非 ASCII 字符的文件名进行编码的标准方法。</span><span class="sxs-lookup"><span data-stu-id="d67d0-255">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="d67d0-256">`Compress-Archive`Cmdlet 使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="d67d0-256">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="d67d0-257">其他 ZIP 存档工具可以使用其他编码方案。</span><span class="sxs-lookup"><span data-stu-id="d67d0-257">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="d67d0-258">当使用不是使用 UTF-8 编码存储的文件名提取文件时， `Expand-Archive` 将使用存档中找到的原始值。</span><span class="sxs-lookup"><span data-stu-id="d67d0-258">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="d67d0-259">这可能会导致文件名不同于存储在存档中的源文件名。</span><span class="sxs-lookup"><span data-stu-id="d67d0-259">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="d67d0-260">相关链接</span><span class="sxs-lookup"><span data-stu-id="d67d0-260">RELATED LINKS</span></span>

[<span data-ttu-id="d67d0-261">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="d67d0-261">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="d67d0-262">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d67d0-262">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

