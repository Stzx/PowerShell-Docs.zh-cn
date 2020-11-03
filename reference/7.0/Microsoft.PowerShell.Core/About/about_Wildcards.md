---
description: 介绍如何在 PowerShell 中使用通配符。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 3a3146210a7d133190631f177d3a69ca120d1432
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199670"
---
# <a name="about-wildcards"></a><span data-ttu-id="2f253-104">关于通配符</span><span class="sxs-lookup"><span data-stu-id="2f253-104">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="2f253-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="2f253-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="2f253-106">介绍如何在 PowerShell 中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2f253-106">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2f253-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="2f253-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2f253-108">通配符表示一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="2f253-108">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="2f253-109">您可以使用它们在命令中创建 word 模式。</span><span class="sxs-lookup"><span data-stu-id="2f253-109">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="2f253-110">例如，若要获取文件扩展名为的目录中的所有文件 `C:\Techdocs` `.ppt` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="2f253-110">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="2f253-111">在这种情况下，星号 (`*`) 通配符表示在文件扩展名之前出现的任何字符 `.ppt` 。</span><span class="sxs-lookup"><span data-stu-id="2f253-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="2f253-112">PowerShell 支持以下通配符：</span><span class="sxs-lookup"><span data-stu-id="2f253-112">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="2f253-113">通配符</span><span class="sxs-lookup"><span data-stu-id="2f253-113">Wildcard</span></span>|<span data-ttu-id="2f253-114">说明</span><span class="sxs-lookup"><span data-stu-id="2f253-114">Description</span></span>               |<span data-ttu-id="2f253-115">示例</span><span class="sxs-lookup"><span data-stu-id="2f253-115">Example</span></span> |<span data-ttu-id="2f253-116">匹配</span><span class="sxs-lookup"><span data-stu-id="2f253-116">Match</span></span>        |<span data-ttu-id="2f253-117">无匹配项</span><span class="sxs-lookup"><span data-stu-id="2f253-117">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="2f253-118">匹配零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="2f253-118">Match zero or more characters</span></span> | <span data-ttu-id="2f253-119">的\*</span><span class="sxs-lookup"><span data-stu-id="2f253-119">a\*</span></span>  | <span data-ttu-id="2f253-120">aA、ag、Apple</span><span class="sxs-lookup"><span data-stu-id="2f253-120">aA, ag, Apple</span></span> | <span data-ttu-id="2f253-121">香蕉</span><span class="sxs-lookup"><span data-stu-id="2f253-121">banana</span></span> |
|<span data-ttu-id="2f253-122">?</span><span class="sxs-lookup"><span data-stu-id="2f253-122">?</span></span>       |<span data-ttu-id="2f253-123">匹配该位置中的一个字符</span><span class="sxs-lookup"><span data-stu-id="2f253-123">Match one character in that position</span></span> | <span data-ttu-id="2f253-124">？ n</span><span class="sxs-lookup"><span data-stu-id="2f253-124">?n</span></span> | <span data-ttu-id="2f253-125">，在中，在</span><span class="sxs-lookup"><span data-stu-id="2f253-125">an, in, on</span></span> | <span data-ttu-id="2f253-126">为名</span><span class="sxs-lookup"><span data-stu-id="2f253-126">ran</span></span> |
|<span data-ttu-id="2f253-127">\[ \]</span><span class="sxs-lookup"><span data-stu-id="2f253-127">\[ \]</span></span>   |<span data-ttu-id="2f253-128">匹配一系列字符</span><span class="sxs-lookup"><span data-stu-id="2f253-128">Match a range of characters</span></span> | <span data-ttu-id="2f253-129">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="2f253-129">\[a-l\]ook</span></span> | <span data-ttu-id="2f253-130">书籍，库，查找</span><span class="sxs-lookup"><span data-stu-id="2f253-130">book, cook, look</span></span> | <span data-ttu-id="2f253-131">需要</span><span class="sxs-lookup"><span data-stu-id="2f253-131">took</span></span> |
|<span data-ttu-id="2f253-132">\[ \]</span><span class="sxs-lookup"><span data-stu-id="2f253-132">\[ \]</span></span>   |<span data-ttu-id="2f253-133">匹配特定字符</span><span class="sxs-lookup"><span data-stu-id="2f253-133">Match specific characters</span></span> | <span data-ttu-id="2f253-134">\[bc \] ook</span><span class="sxs-lookup"><span data-stu-id="2f253-134">\[bc\]ook</span></span> | <span data-ttu-id="2f253-135">书籍，库</span><span class="sxs-lookup"><span data-stu-id="2f253-135">book, cook</span></span> | <span data-ttu-id="2f253-136">自已</span><span class="sxs-lookup"><span data-stu-id="2f253-136">hook</span></span> |

<span data-ttu-id="2f253-137">可以在同一单词模式中包含多个通配符字符。</span><span class="sxs-lookup"><span data-stu-id="2f253-137">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="2f253-138">例如，若要查找名称以字母 **a** 到 **l** 开头的文本文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="2f253-138">For example, to find text files with names that begin with the letters **a** through **l** , type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="2f253-139">许多 cmdlet 接受参数值中的通配符。</span><span class="sxs-lookup"><span data-stu-id="2f253-139">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="2f253-140">每个 cmdlet 的帮助主题描述了哪些参数接受通配符。</span><span class="sxs-lookup"><span data-stu-id="2f253-140">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="2f253-141">对于接受通配符的参数，其使用不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="2f253-141">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="2f253-142">可以在命令和脚本块中使用通配符，例如，创建表示属性值的单词模式。</span><span class="sxs-lookup"><span data-stu-id="2f253-142">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="2f253-143">例如，以下命令将获取 **ServiceType** 属性值包括 **Interactive** 的服务。</span><span class="sxs-lookup"><span data-stu-id="2f253-143">For example, the following command gets services in which the **ServiceType** property value includes **Interactive** .</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="2f253-144">在下面的示例中， `If` 语句包含使用通配符查找属性值的条件。</span><span class="sxs-lookup"><span data-stu-id="2f253-144">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="2f253-145">如果还原点的 **描述** 包含 **PowerShell** ，则该命令会将还原点的 **CreationTime** 属性的值添加到日志文件。</span><span class="sxs-lookup"><span data-stu-id="2f253-145">If the restore point's **Description** includes **PowerShell** , the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="2f253-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f253-146">SEE ALSO</span></span>

[<span data-ttu-id="2f253-147">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="2f253-147">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="2f253-148">about_If</span><span class="sxs-lookup"><span data-stu-id="2f253-148">about_If</span></span>](about_If.md)

[<span data-ttu-id="2f253-149">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="2f253-149">about_Script_Blocks</span></span>](about_Script_Blocks.md)
