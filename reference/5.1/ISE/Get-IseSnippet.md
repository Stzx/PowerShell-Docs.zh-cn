---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198956"
---
# <span data-ttu-id="da956-103">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="da956-103">Get-IseSnippet</span></span>

## <span data-ttu-id="da956-104">摘要</span><span class="sxs-lookup"><span data-stu-id="da956-104">SYNOPSIS</span></span>
<span data-ttu-id="da956-105">获取用户创建的代码段。</span><span class="sxs-lookup"><span data-stu-id="da956-105">Gets snippets that the user created.</span></span>

## <span data-ttu-id="da956-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da956-106">SYNTAX</span></span>

```
Get-IseSnippet [<CommonParameters>]
```

## <span data-ttu-id="da956-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="da956-107">DESCRIPTION</span></span>

<span data-ttu-id="da956-108">该 `Get-IseSnippet` cmdlet 将获取包含用户创建的可重用文本代码段的 types.ps1xml 文件。</span><span class="sxs-lookup"><span data-stu-id="da956-108">The `Get-IseSnippet` cmdlet gets the PS1XML files that contain reusable text snippets that the user created.</span></span> <span data-ttu-id="da956-109">它只能在 Windows PowerShell 集成脚本环境 (ISE) 中正常运行。</span><span class="sxs-lookup"><span data-stu-id="da956-109">It works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="da956-110">使用 `New-IseSnippet` cmdlet 创建代码段时，将 `New-IseSnippet` `<SnippetTitle>.Snippets.ps1xml` 在目录中创建一个文件 `$home\Documents\WindowsPowerShell\Snippets` 。</span><span class="sxs-lookup"><span data-stu-id="da956-110">When you use the `New-IseSnippet` cmdlet to create a snippet, `New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
<span data-ttu-id="da956-111">`Get-IseSnippet` 获取代码段目录中的代码段文件。</span><span class="sxs-lookup"><span data-stu-id="da956-111">`Get-IseSnippet` gets the snippet files in the Snippets directory.</span></span>

<span data-ttu-id="da956-112">此 cmdlet 不会获取内置代码段或通过 cmdlet 从模块导入的代码段 `Import-IseSnippet` 。</span><span class="sxs-lookup"><span data-stu-id="da956-112">This cmdlet does not get built-in snippets or snippets that are imported from modules through the `Import-IseSnippet` cmdlet.</span></span>

<span data-ttu-id="da956-113">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="da956-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="da956-114">示例</span><span class="sxs-lookup"><span data-stu-id="da956-114">EXAMPLES</span></span>

### <span data-ttu-id="da956-115">示例 1：获取所有用户定义的代码段</span><span class="sxs-lookup"><span data-stu-id="da956-115">Example 1: Get all user-defined snippets</span></span>

<span data-ttu-id="da956-116">此示例获取代码段目录中所有用户定义的代码段。</span><span class="sxs-lookup"><span data-stu-id="da956-116">This example gets all user-define snippets in the Snippets directory.</span></span>

```powershell
Get-IseSnippet
```

### <span data-ttu-id="da956-117">示例 2：将所有用户定义的代码段从远程计算机复制到共享目录</span><span class="sxs-lookup"><span data-stu-id="da956-117">Example 2: Copy all user-defined snippets from remote computers to a shared directory</span></span>

<span data-ttu-id="da956-118">此示例将用户创建的所有代码段从一组远程计算机复制到共享的代码段目录。</span><span class="sxs-lookup"><span data-stu-id="da956-118">This example copies all of the user-created snippets from a group of remote computers to a shared Snippets directory.</span></span>

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

<span data-ttu-id="da956-119">`Invoke-Command` 在 `Get-IseSnippet` 文件中的计算机上运行 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="da956-119">`Invoke-Command` runs `Get-IseSnippet` on the computers in the `Servers.txt` file.</span></span> <span data-ttu-id="da956-120">管道运算符 (`|`) 将代码段文件发送到 `Copy-Item` cmdlet，这会将这些文件复制到由 **Destination** 参数指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="da956-120">A pipeline operator (`|`) sends the snippet files to the `Copy-Item` cmdlet, which copies them to the directory that is specified by the **Destination** parameter.</span></span>

### <span data-ttu-id="da956-121">示例 3：在本地计算机上显示每个代码段的标题和文本</span><span class="sxs-lookup"><span data-stu-id="da956-121">Example 3: Display the title and text of each snippet on a local computer</span></span>

<span data-ttu-id="da956-122">此示例使用 `Get-IseSnippet` 和 `Select-Xml` cmdlet 在本地计算机上显示每个代码段的标题和文本。</span><span class="sxs-lookup"><span data-stu-id="da956-122">This example uses the `Get-IseSnippet` and `Select-Xml` cmdlets to display the title and text of each snippet on the local computer.</span></span>

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### <span data-ttu-id="da956-123">示例 4：在会话中显示所有代码段的标题和说明</span><span class="sxs-lookup"><span data-stu-id="da956-123">Example 4: Display the title and description of all snippets in the session</span></span>

<span data-ttu-id="da956-124">此示例显示会话中所有代码段的标题和说明，其中包括内置代码段、用户定义的代码段和导入的代码段。</span><span class="sxs-lookup"><span data-stu-id="da956-124">This example displays the title and description of all snippets in the session, including built-in snippets, user-defined snippets, and imported snippets.</span></span>

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

<span data-ttu-id="da956-125">`$PSISE`变量表示 Windows PowerShell ISE 主机程序。</span><span class="sxs-lookup"><span data-stu-id="da956-125">The `$PSISE` variable represents the Windows PowerShell ISE host program.</span></span> <span data-ttu-id="da956-126">该变量的 **psise.currentpowershelltab** 属性 `$PSISE` 表示当前会话。</span><span class="sxs-lookup"><span data-stu-id="da956-126">The **CurrentPowerShellTab** property of the `$PSISE` variable represent the current session.</span></span> <span data-ttu-id="da956-127">**Snippets** 属性表示当前会话中的代码段。</span><span class="sxs-lookup"><span data-stu-id="da956-127">The **Snippets** property represents snippets in the current session.</span></span>

<span data-ttu-id="da956-128">`$PSISE.CurrentPowerShellTab.Snippets`命令返回一个表示代码段的 **new-isesnippet** 对象，这与 `Get-IseSnippet` cmdlet 不同。</span><span class="sxs-lookup"><span data-stu-id="da956-128">The `$PSISE.CurrentPowerShellTab.Snippets` command returns a **Microsoft.PowerShell.Host.ISE.ISESnippet** object that represents a snippet, unlike the `Get-IseSnippet` cmdlet.</span></span> <span data-ttu-id="da956-129">`Get-IseSnippet` 返回表示代码段文件 () 的文件对象。</span><span class="sxs-lookup"><span data-stu-id="da956-129">`Get-IseSnippet` returns a file object (System.Io.FileInfo) that represents a snippet file.</span></span>

<span data-ttu-id="da956-130">Cmdlet 将在 `Format-Table` 表中显示代码段的 **DisplayTitle** 和 **Description** 属性。</span><span class="sxs-lookup"><span data-stu-id="da956-130">The `Format-Table` cmdlet displays the **DisplayTitle** and **Description** properties of the snippets in a table.</span></span>

## <span data-ttu-id="da956-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da956-131">PARAMETERS</span></span>

### <span data-ttu-id="da956-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="da956-132">CommonParameters</span></span>

<span data-ttu-id="da956-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="da956-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da956-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="da956-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da956-135">输入</span><span class="sxs-lookup"><span data-stu-id="da956-135">INPUTS</span></span>

## <span data-ttu-id="da956-136">输出</span><span class="sxs-lookup"><span data-stu-id="da956-136">OUTPUTS</span></span>

### <span data-ttu-id="da956-137">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="da956-137">System.IO.FileInfo</span></span>

<span data-ttu-id="da956-138">此 cmdlet 返回表示代码段文件的文件对象。</span><span class="sxs-lookup"><span data-stu-id="da956-138">This cmdlet returns a file object that represents the snippet file.</span></span>

## <span data-ttu-id="da956-139">注释</span><span class="sxs-lookup"><span data-stu-id="da956-139">NOTES</span></span>

* <span data-ttu-id="da956-140">`New-IseSnippet`Cmdlet 将新的用户创建的代码段存储在 types.ps1xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="da956-140">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="da956-141">因此，Windows PowerShell 无法将其添加到执行策略为 **AllSigned** 或 **Restricted** 的会话中。</span><span class="sxs-lookup"><span data-stu-id="da956-141">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="da956-142">在 **Restricted** 或 **AllSigned** 会话中，你可以创建、获取和导入用户创建的未签名代码段，但无法在会话中使用它们。</span><span class="sxs-lookup"><span data-stu-id="da956-142">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="da956-143">若要使用 cmdlet 返回的未签名用户创建的代码段 `Get-IseSnippet` ，请更改执行策略，然后重新启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="da956-143">To use unsigned user-created snippets that the `Get-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="da956-144">有关 Windows PowerShell 执行策略的详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="da956-144">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="da956-145">相关链接</span><span class="sxs-lookup"><span data-stu-id="da956-145">RELATED LINKS</span></span>

[<span data-ttu-id="da956-146">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="da956-146">New-IseSnippet</span></span>](New-IseSnippet.md)

[<span data-ttu-id="da956-147">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="da956-147">Import-IseSnippet</span></span>](Import-IseSnippet.md)
