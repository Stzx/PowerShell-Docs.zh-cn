---
title: 命名帮助文件
ms.date: 09/12/2016
ms.openlocfilehash: ea95e6d6c87e553ed11fe6e3f058fc9a1b3d03f8
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893265"
---
# <a name="naming-help-files"></a><span data-ttu-id="bf00c-102">命名帮助文件</span><span class="sxs-lookup"><span data-stu-id="bf00c-102">Naming Help Files</span></span>

<span data-ttu-id="bf00c-103">本主题说明如何命名基于 XML 的帮助文件，以便[get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet 可以找到它。</span><span class="sxs-lookup"><span data-stu-id="bf00c-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="bf00c-104">每个命令类型的名称要求不同。</span><span class="sxs-lookup"><span data-stu-id="bf00c-104">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="bf00c-105">Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="bf00c-105">Cmdlet Help Files</span></span>

<span data-ttu-id="bf00c-106">必须为在其中定义 cmdlet 的程序集命名 c # cmdlet 的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="bf00c-106">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="bf00c-107">使用以下文件名格式：</span><span class="sxs-lookup"><span data-stu-id="bf00c-107">Use the following filename format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="bf00c-108">程序集名称格式是必需的，即使程序集是嵌套模块也是如此。</span><span class="sxs-lookup"><span data-stu-id="bf00c-108">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="bf00c-109">例如， [get-winevent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet 是在 Microsoft.PowerShell.Diagnostics.dll 程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="bf00c-109">For example, the [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="bf00c-110">此 `Get-Help` cmdlet `Get-WinEvent` 仅在模块目录的文件中查找有关该 cmdlet 的帮助主题 `Microsoft.PowerShell.Diagnostics.dll-help.xml` 。</span><span class="sxs-lookup"><span data-stu-id="bf00c-110">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the `Microsoft.PowerShell.Diagnostics.dll-help.xml` file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="bf00c-111">提供程序帮助文件</span><span class="sxs-lookup"><span data-stu-id="bf00c-111">Provider Help files</span></span>

<span data-ttu-id="bf00c-112">对于在其中定义提供程序的程序集，必须为 PowerShell 提供程序的帮助文件命名。</span><span class="sxs-lookup"><span data-stu-id="bf00c-112">The help file for a PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="bf00c-113">使用以下文件名格式：</span><span class="sxs-lookup"><span data-stu-id="bf00c-113">Use the following filename format:</span></span>

`<AssemblyName>.dll-help.xml`

<span data-ttu-id="bf00c-114">程序集名称格式是必需的，即使程序集是嵌套模块也是如此。</span><span class="sxs-lookup"><span data-stu-id="bf00c-114">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="bf00c-115">例如，证书提供程序是在 `Microsoft.PowerShell.Security.dll` 程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="bf00c-115">For example, the Certificate provider is defined in the `Microsoft.PowerShell.Security.dll` assembly.</span></span> <span data-ttu-id="bf00c-116">此 `Get-Help` cmdlet 仅在模块目录的文件中查找证书提供程序的帮助主题 `Microsoft.PowerShell.Security.dll-help.xml` 。</span><span class="sxs-lookup"><span data-stu-id="bf00c-116">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the `Microsoft.PowerShell.Security.dll-help.xml` file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="bf00c-117">函数帮助文件</span><span class="sxs-lookup"><span data-stu-id="bf00c-117">Function Help Files</span></span>

<span data-ttu-id="bf00c-118">可以通过使用[基于注释的帮助](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)或 XML 帮助文件中介绍的方式记录函数。</span><span class="sxs-lookup"><span data-stu-id="bf00c-118">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="bf00c-119">在 XML 文件中记录函数时，该函数必须有一个 `.ExternalHelp` comment 关键字，该关键字将函数与 XML 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="bf00c-119">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="bf00c-120">否则，此 `Get-Help` cmdlet 将无法找到帮助文件。</span><span class="sxs-lookup"><span data-stu-id="bf00c-120">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="bf00c-121">函数帮助文件的名称没有技术要求。</span><span class="sxs-lookup"><span data-stu-id="bf00c-121">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="bf00c-122">但是，最佳做法是为定义该函数的脚本模块命名帮助文件。</span><span class="sxs-lookup"><span data-stu-id="bf00c-122">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="bf00c-123">例如，以下函数是在文件中定义的 `MyModule.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="bf00c-123">For example, the following function is defined in the `MyModule.psm1` file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="bf00c-124">CIM 命令帮助文件</span><span class="sxs-lookup"><span data-stu-id="bf00c-124">CIM Command Help Files</span></span>

<span data-ttu-id="bf00c-125">CIM 命令的帮助文件必须为在其中定义 CIM 命令的 CDXML 文件命名。</span><span class="sxs-lookup"><span data-stu-id="bf00c-125">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="bf00c-126">使用以下文件名格式：</span><span class="sxs-lookup"><span data-stu-id="bf00c-126">Use the following filename format:</span></span>

`<FileName>.cdxml-help.xml`

<span data-ttu-id="bf00c-127">CIM 命令在 CDXML 文件中定义，这些文件可以作为嵌套模块包含在模块中。</span><span class="sxs-lookup"><span data-stu-id="bf00c-127">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="bf00c-128">如果将 CIM 命令作为函数导入到会话中，则 PowerShell 会将 `.ExternalHelp` comment 关键字添加到函数定义中，该函数将函数与为其定义 CIM 命令的 CDXML 文件命名的 XML 帮助文件相关联。</span><span class="sxs-lookup"><span data-stu-id="bf00c-128">When the CIM command is imported into the session as a function, PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="bf00c-129">脚本工作流帮助文件</span><span class="sxs-lookup"><span data-stu-id="bf00c-129">Script Workflow Help Files</span></span>

<span data-ttu-id="bf00c-130">可在基于 XML 的帮助文件中记录模块中包含的脚本工作流。</span><span class="sxs-lookup"><span data-stu-id="bf00c-130">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="bf00c-131">帮助文件的名称没有技术要求。</span><span class="sxs-lookup"><span data-stu-id="bf00c-131">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="bf00c-132">但是，最佳做法是将定义脚本工作流的脚本模块的帮助文件命名为。</span><span class="sxs-lookup"><span data-stu-id="bf00c-132">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="bf00c-133">例如：</span><span class="sxs-lookup"><span data-stu-id="bf00c-133">For example:</span></span>

`<ScriptModule>.psm1-help.xml`

<span data-ttu-id="bf00c-134">与其他脚本化命令不同，脚本工作流不需要 `.ExternalHelp` 使用 comment 关键字将它们与帮助文件相关联。</span><span class="sxs-lookup"><span data-stu-id="bf00c-134">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="bf00c-135">相反，PowerShell 会在特定于 XML 的帮助文件的模块目录的 UI 区域性特定子目录中搜索，并在所有文件中查找脚本工作流的帮助。</span><span class="sxs-lookup"><span data-stu-id="bf00c-135">Instead, PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="bf00c-136">`.ExternalHelp`comment 关键字被忽略。</span><span class="sxs-lookup"><span data-stu-id="bf00c-136">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="bf00c-137">由于 `.ExternalHelp` 忽略了 comment 关键字，因此， `Get-Help` 仅当模块中包含脚本工作流时，cmdlet 才能找到这些脚本工作流的帮助。</span><span class="sxs-lookup"><span data-stu-id="bf00c-137">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>
