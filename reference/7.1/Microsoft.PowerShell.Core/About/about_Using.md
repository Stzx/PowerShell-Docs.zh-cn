---
description: 允许你指示在会话中使用的命名空间。
Locale: en-US
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: bbea815f93ba503fcce550dec28736630fec5a51
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890757"
---
# <a name="about-using"></a><span data-ttu-id="9d601-103">关于使用</span><span class="sxs-lookup"><span data-stu-id="9d601-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="9d601-104">简短说明</span><span class="sxs-lookup"><span data-stu-id="9d601-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9d601-105">允许你指示在会话中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9d601-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="9d601-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="9d601-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="9d601-107">`using`语句允许您指定在会话中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9d601-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="9d601-108">添加命名空间可简化 .NET 类和成员的使用，并允许你从脚本模块和程序集导入类。</span><span class="sxs-lookup"><span data-stu-id="9d601-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="9d601-109">`using`语句必须位于脚本中的任何其他语句之前。</span><span class="sxs-lookup"><span data-stu-id="9d601-109">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="9d601-110">`using`语句不应与 `using:` 变量的作用域修饰符混淆。</span><span class="sxs-lookup"><span data-stu-id="9d601-110">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="9d601-111">有关详细信息，请参阅 [about_Remote_Variables](about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="9d601-111">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="9d601-112">命名空间语法</span><span class="sxs-lookup"><span data-stu-id="9d601-112">Namespace syntax</span></span>

<span data-ttu-id="9d601-113">指定要从中解析类型的 .NET 命名空间：</span><span class="sxs-lookup"><span data-stu-id="9d601-113">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="9d601-114">通过指定命名空间，可以更容易地按简称引用类型。</span><span class="sxs-lookup"><span data-stu-id="9d601-114">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="9d601-115">模块语法</span><span class="sxs-lookup"><span data-stu-id="9d601-115">Module syntax</span></span>

<span data-ttu-id="9d601-116">从 PowerShell 模块加载类：</span><span class="sxs-lookup"><span data-stu-id="9d601-116">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="9d601-117">的值 `<module-name>` 可以是模块名称、完整的模块规范或模块文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9d601-117">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="9d601-118">当 `<module-name>` 是路径时，路径可以是完全限定路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="9d601-118">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="9d601-119">相对路径是相对于包含 using 语句的脚本进行解析的。</span><span class="sxs-lookup"><span data-stu-id="9d601-119">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="9d601-120">当 `<module-name>` 是名称或模块规范时，PowerShell 将在 **PSModulePath** 中搜索指定的模块。</span><span class="sxs-lookup"><span data-stu-id="9d601-120">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="9d601-121">模块规范是一个包含以下键的哈希表。</span><span class="sxs-lookup"><span data-stu-id="9d601-121">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="9d601-122">`ModuleName` - **必需** 指定模块名称。</span><span class="sxs-lookup"><span data-stu-id="9d601-122">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="9d601-123">`GUID` - **可选** 指定模块的 GUID。</span><span class="sxs-lookup"><span data-stu-id="9d601-123">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="9d601-124">还 **需要** 指定以下三个键中的一个。</span><span class="sxs-lookup"><span data-stu-id="9d601-124">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="9d601-125">这些密钥不能一起使用。</span><span class="sxs-lookup"><span data-stu-id="9d601-125">These keys can't be used together.</span></span>
  - <span data-ttu-id="9d601-126">`ModuleVersion` -指定模块的最低可接受版本。</span><span class="sxs-lookup"><span data-stu-id="9d601-126">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="9d601-127">`RequiredVersion` -指定模块的准确的必需版本。</span><span class="sxs-lookup"><span data-stu-id="9d601-127">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="9d601-128">`MaximumVersion` -指定模块可接受的最大版本。</span><span class="sxs-lookup"><span data-stu-id="9d601-128">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="9d601-129">程序集语法</span><span class="sxs-lookup"><span data-stu-id="9d601-129">Assembly syntax</span></span>

<span data-ttu-id="9d601-130">若要预加载 .NET 程序集中的类型：</span><span class="sxs-lookup"><span data-stu-id="9d601-130">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="9d601-131">加载程序集时，将从该程序集将 .NET 类型预加载到脚本中的分析时。</span><span class="sxs-lookup"><span data-stu-id="9d601-131">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="9d601-132">这允许你创建新的 PowerShell 类，它们使用预先加载的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="9d601-132">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="9d601-133">如果未创建新的 PowerShell 类，请改用 `Add-Type` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9d601-133">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="9d601-134">有关详细信息，请参阅 [添加类型](xref:Microsoft.PowerShell.Utility.Add-Type)。</span><span class="sxs-lookup"><span data-stu-id="9d601-134">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="9d601-135">示例</span><span class="sxs-lookup"><span data-stu-id="9d601-135">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="9d601-136">示例 1-为 typename 解析添加命名空间</span><span class="sxs-lookup"><span data-stu-id="9d601-136">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="9d601-137">下面的脚本获取 "Hello World" 字符串的加密哈希。</span><span class="sxs-lookup"><span data-stu-id="9d601-137">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="9d601-138">请注意 `using namespace System.Text` 和如何 `using namespace System.IO` 简化对中 `[UnicodeEncoding]` `System.Text` 和和的引用 `[Stream]` `[MemoryStream]` `System.IO` 。</span><span class="sxs-lookup"><span data-stu-id="9d601-138">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="9d601-139">示例 2-从脚本模块加载类</span><span class="sxs-lookup"><span data-stu-id="9d601-139">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="9d601-140">在此示例中，有一个名为 **CardGames** 的 PowerShell 脚本模块，用于定义以下类：</span><span class="sxs-lookup"><span data-stu-id="9d601-140">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="9d601-141">**CardGames**</span><span class="sxs-lookup"><span data-stu-id="9d601-141">**CardGames.Deck**</span></span>
- <span data-ttu-id="9d601-142">**CardGames 卡**</span><span class="sxs-lookup"><span data-stu-id="9d601-142">**CardGames.Card**</span></span>

<span data-ttu-id="9d601-143">`Import-Module``#requires`语句仅导入模块定义的模块函数、别名和变量。</span><span class="sxs-lookup"><span data-stu-id="9d601-143">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="9d601-144">不导入类。</span><span class="sxs-lookup"><span data-stu-id="9d601-144">Classes are not imported.</span></span> <span data-ttu-id="9d601-145">`using module`命令导入模块，同时加载类定义。</span><span class="sxs-lookup"><span data-stu-id="9d601-145">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="9d601-146">示例 3-从程序集加载类</span><span class="sxs-lookup"><span data-stu-id="9d601-146">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="9d601-147">此示例将加载一个程序集，以便可以使用该程序集的类来创建新的 PowerShell 类。</span><span class="sxs-lookup"><span data-stu-id="9d601-147">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="9d601-148">下面的脚本创建一个派生自 **DirectoryContext** 类的新 PowerShell 类。</span><span class="sxs-lookup"><span data-stu-id="9d601-148">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```
