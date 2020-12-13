---
ms.date: 09/12/2016
ms.topic: reference
title: 命名帮助文件
description: 命名帮助文件
ms.openlocfilehash: b77af8f9b9510785a4198fed9da1263184a27b99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667583"
---
# <a name="naming-help-files"></a><span data-ttu-id="475df-103">命名帮助文件</span><span class="sxs-lookup"><span data-stu-id="475df-103">Naming Help Files</span></span>

<span data-ttu-id="475df-104">本主题说明如何命名基于 XML 的帮助文件，以便 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet 可以找到它。</span><span class="sxs-lookup"><span data-stu-id="475df-104">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="475df-105">每个命令类型的名称要求不同。</span><span class="sxs-lookup"><span data-stu-id="475df-105">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="475df-106">Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="475df-106">Cmdlet Help Files</span></span>

<span data-ttu-id="475df-107">必须为在其中定义 cmdlet 的程序集命名 c # cmdlet 的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="475df-107">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="475df-108">使用以下文件名格式：</span><span class="sxs-lookup"><span data-stu-id="475df-108">Use the following filename format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="475df-109">程序集名称格式是必需的，即使程序集是嵌套模块也是如此。</span><span class="sxs-lookup"><span data-stu-id="475df-109">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="475df-110">例如， [get-winevent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet 是在 Microsoft.PowerShell.Diagnostics.dll 程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="475df-110">For example, the [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="475df-111">此 `Get-Help` cmdlet `Get-WinEvent` 仅在模块目录的文件中查找有关该 cmdlet 的帮助主题 `Microsoft.PowerShell.Diagnostics.dll-help.xml` 。</span><span class="sxs-lookup"><span data-stu-id="475df-111">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the `Microsoft.PowerShell.Diagnostics.dll-help.xml` file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="475df-112">提供程序帮助文件</span><span class="sxs-lookup"><span data-stu-id="475df-112">Provider Help files</span></span>

<span data-ttu-id="475df-113">对于在其中定义提供程序的程序集，必须为 PowerShell 提供程序的帮助文件命名。</span><span class="sxs-lookup"><span data-stu-id="475df-113">The help file for a PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="475df-114">使用以下文件名格式：</span><span class="sxs-lookup"><span data-stu-id="475df-114">Use the following filename format:</span></span>

`<AssemblyName>.dll-help.xml`

<span data-ttu-id="475df-115">程序集名称格式是必需的，即使程序集是嵌套模块也是如此。</span><span class="sxs-lookup"><span data-stu-id="475df-115">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="475df-116">例如，证书提供程序是在 `Microsoft.PowerShell.Security.dll` 程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="475df-116">For example, the Certificate provider is defined in the `Microsoft.PowerShell.Security.dll` assembly.</span></span> <span data-ttu-id="475df-117">此 `Get-Help` cmdlet 仅在模块目录的文件中查找证书提供程序的帮助主题 `Microsoft.PowerShell.Security.dll-help.xml` 。</span><span class="sxs-lookup"><span data-stu-id="475df-117">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the `Microsoft.PowerShell.Security.dll-help.xml` file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="475df-118">函数帮助文件</span><span class="sxs-lookup"><span data-stu-id="475df-118">Function Help Files</span></span>

<span data-ttu-id="475df-119">可以通过使用 [基于注释的帮助](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) 或 XML 帮助文件中介绍的方式记录函数。</span><span class="sxs-lookup"><span data-stu-id="475df-119">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="475df-120">在 XML 文件中记录函数时，该函数必须有一个 `.ExternalHelp` comment 关键字，该关键字将函数与 XML 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="475df-120">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="475df-121">否则，此 `Get-Help` cmdlet 将无法找到帮助文件。</span><span class="sxs-lookup"><span data-stu-id="475df-121">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="475df-122">函数帮助文件的名称没有技术要求。</span><span class="sxs-lookup"><span data-stu-id="475df-122">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="475df-123">但是，最佳做法是为定义该函数的脚本模块命名帮助文件。</span><span class="sxs-lookup"><span data-stu-id="475df-123">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="475df-124">例如，以下函数是在文件中定义的 `MyModule.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="475df-124">For example, the following function is defined in the `MyModule.psm1` file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="475df-125">CIM 命令帮助文件</span><span class="sxs-lookup"><span data-stu-id="475df-125">CIM Command Help Files</span></span>

<span data-ttu-id="475df-126">CIM 命令的帮助文件必须为在其中定义 CIM 命令的 CDXML 文件命名。</span><span class="sxs-lookup"><span data-stu-id="475df-126">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="475df-127">使用以下文件名格式：</span><span class="sxs-lookup"><span data-stu-id="475df-127">Use the following filename format:</span></span>

`<FileName>.cdxml-help.xml`

<span data-ttu-id="475df-128">CIM 命令在 CDXML 文件中定义，这些文件可以作为嵌套模块包含在模块中。</span><span class="sxs-lookup"><span data-stu-id="475df-128">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="475df-129">如果将 CIM 命令作为函数导入到会话中，则 PowerShell 会将 `.ExternalHelp` comment 关键字添加到函数定义中，该函数将函数与为其定义 CIM 命令的 CDXML 文件命名的 XML 帮助文件相关联。</span><span class="sxs-lookup"><span data-stu-id="475df-129">When the CIM command is imported into the session as a function, PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="475df-130">脚本工作流帮助文件</span><span class="sxs-lookup"><span data-stu-id="475df-130">Script Workflow Help Files</span></span>

<span data-ttu-id="475df-131">可在基于 XML 的帮助文件中记录模块中包含的脚本工作流。</span><span class="sxs-lookup"><span data-stu-id="475df-131">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="475df-132">帮助文件的名称没有技术要求。</span><span class="sxs-lookup"><span data-stu-id="475df-132">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="475df-133">但是，最佳做法是将定义脚本工作流的脚本模块的帮助文件命名为。</span><span class="sxs-lookup"><span data-stu-id="475df-133">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="475df-134">例如：</span><span class="sxs-lookup"><span data-stu-id="475df-134">For example:</span></span>

`<ScriptModule>.psm1-help.xml`

<span data-ttu-id="475df-135">与其他脚本化命令不同，脚本工作流不需要 `.ExternalHelp` 使用 comment 关键字将它们与帮助文件相关联。</span><span class="sxs-lookup"><span data-stu-id="475df-135">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="475df-136">相反，PowerShell 会在特定于 XML 的帮助文件的模块目录的 UI 区域性特定子目录中搜索，并在所有文件中查找脚本工作流的帮助。</span><span class="sxs-lookup"><span data-stu-id="475df-136">Instead, PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="475df-137">`.ExternalHelp` comment 关键字被忽略。</span><span class="sxs-lookup"><span data-stu-id="475df-137">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="475df-138">由于 `.ExternalHelp` 忽略了 comment 关键字，因此， `Get-Help` 仅当模块中包含脚本工作流时，cmdlet 才能找到这些脚本工作流的帮助。</span><span class="sxs-lookup"><span data-stu-id="475df-138">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>
