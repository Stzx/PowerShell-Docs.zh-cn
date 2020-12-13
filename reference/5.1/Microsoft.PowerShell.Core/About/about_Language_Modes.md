---
description: 说明语言模式及其对 PowerShell 会话的影响。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 91e3021c854945d86822c5d8219542eff7118aa7
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625646"
---
# <a name="about-language-modes"></a><span data-ttu-id="3a014-104">关于语言模式</span><span class="sxs-lookup"><span data-stu-id="3a014-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="3a014-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="3a014-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3a014-106">说明语言模式及其对 PowerShell 会话的影响。</span><span class="sxs-lookup"><span data-stu-id="3a014-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="3a014-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="3a014-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3a014-108">PowerShell 会话的语言模式确定可以在会话中使用 PowerShell 语言的哪些元素。</span><span class="sxs-lookup"><span data-stu-id="3a014-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="3a014-109">PowerShell 支持以下语言模式：</span><span class="sxs-lookup"><span data-stu-id="3a014-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="3a014-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="3a014-110">FullLanguage</span></span>
- <span data-ttu-id="3a014-111">PowerShell 3.0) 中引入的 ConstrainedLanguage (</span><span class="sxs-lookup"><span data-stu-id="3a014-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="3a014-112">RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="3a014-112">RestrictedLanguage</span></span>
- <span data-ttu-id="3a014-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="3a014-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="3a014-114">什么是语言模式？</span><span class="sxs-lookup"><span data-stu-id="3a014-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="3a014-115">语言模式决定了会话中允许使用的语言元素。</span><span class="sxs-lookup"><span data-stu-id="3a014-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="3a014-116">语言模式实际上是会话配置的属性 (或用于创建会话的 "终结点" ) 。</span><span class="sxs-lookup"><span data-stu-id="3a014-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="3a014-117">使用特定会话配置的所有会话都具有会话配置的语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="3a014-118">所有 PowerShell 会话都具有一种语言模式，其中包括使用 cmdlet 创建的 Pssession `New-PSSession` 、使用 ComputerName 参数的临时会话以及启动 PowerShell 时显示的默认会话。</span><span class="sxs-lookup"><span data-stu-id="3a014-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="3a014-119">远程会话是使用远程计算机上的会话配置创建的。</span><span class="sxs-lookup"><span data-stu-id="3a014-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="3a014-120">会话配置中设置的语言模式确定会话的语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="3a014-121">若要指定 PSSession 的会话配置，请使用创建会话的 cmdlet 的 ConfigurationName 参数。</span><span class="sxs-lookup"><span data-stu-id="3a014-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="3a014-122">语言模式</span><span class="sxs-lookup"><span data-stu-id="3a014-122">LANGUAGE MODES</span></span>

<span data-ttu-id="3a014-123">本部分介绍 PowerShell 会话中的语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="3a014-124">完整语言 (FullLanguage) </span><span class="sxs-lookup"><span data-stu-id="3a014-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="3a014-125">FullLanguage 模式允许会话中的所有语言元素。</span><span class="sxs-lookup"><span data-stu-id="3a014-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="3a014-126">FullLanguage 是所有 Windows 版本（Windows RT 除外）上默认会话的默认语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="3a014-127">受限语言 (RestrictedLanguage) </span><span class="sxs-lookup"><span data-stu-id="3a014-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="3a014-128">在 RestrictedLanguage 模式下，用户可以运行 (cmdlet、函数、CIM 命令和工作流的命令) 但不允许使用脚本块。</span><span class="sxs-lookup"><span data-stu-id="3a014-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="3a014-129">默认情况下，在 RestrictedLanguage 模式下仅允许使用以下变量：</span><span class="sxs-lookup"><span data-stu-id="3a014-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="3a014-130">仅允许以下比较运算符：</span><span class="sxs-lookup"><span data-stu-id="3a014-130">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="3a014-131">`-eq` (等于) </span><span class="sxs-lookup"><span data-stu-id="3a014-131">`-eq` (equal)</span></span>
- <span data-ttu-id="3a014-132">`-gt` (大于) </span><span class="sxs-lookup"><span data-stu-id="3a014-132">`-gt` (greater-than)</span></span>
- <span data-ttu-id="3a014-133">`-lt` (小于) </span><span class="sxs-lookup"><span data-stu-id="3a014-133">`-lt` (less-than)</span></span>

<span data-ttu-id="3a014-134">不允许使用赋值语句、属性引用和方法调用。</span><span class="sxs-lookup"><span data-stu-id="3a014-134">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="3a014-135">无语言 (NoLanguage) </span><span class="sxs-lookup"><span data-stu-id="3a014-135">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="3a014-136">仅可通过 API 使用 NoLanguage 模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-136">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="3a014-137">NoLanguage 模式表示不允许任何格式的脚本文本。</span><span class="sxs-lookup"><span data-stu-id="3a014-137">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="3a014-138">这将排除使用 **AddScript ( # B1** 方法，该方法发送要分析和执行的 PowerShell 脚本片段。</span><span class="sxs-lookup"><span data-stu-id="3a014-138">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="3a014-139">只能使用 **AddCommand ( # B1** 和 **AddParameter ( # B3** ，而不会经历分析器。</span><span class="sxs-lookup"><span data-stu-id="3a014-139">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="3a014-140">受约束语言 (约束语言) </span><span class="sxs-lookup"><span data-stu-id="3a014-140">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="3a014-141">ConstrainedLanguage 模式允许所有 cmdlet 和所有 PowerShell 语言元素，但它会限制允许的类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-141">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="3a014-142">ConstrainedLanguage 模式旨在支持 Windows RT 上的用户模式代码完整性 (UMCI) 。</span><span class="sxs-lookup"><span data-stu-id="3a014-142">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="3a014-143">它在 Windows RT 上是唯一受支持的语言模式，但在所有支持的系统上都可用。</span><span class="sxs-lookup"><span data-stu-id="3a014-143">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="3a014-144">UMCI 通过仅允许在基于 Windows RT 的设备上安装经过 Microsoft 签名和 Microsoft 认证的应用来保护 ARM 设备。</span><span class="sxs-lookup"><span data-stu-id="3a014-144">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="3a014-145">ConstrainedLanguage 模式阻止用户使用 PowerShell 来绕过或违反 UMCI。</span><span class="sxs-lookup"><span data-stu-id="3a014-145">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="3a014-146">ConstrainedLanguage 模式的功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a014-146">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="3a014-147">除了前面所述，Windows 模块中的所有 cmdlet 和其他 UMCI 批准的 cmdlet 均可完全正常运行，并且具有对系统资源的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="3a014-147">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="3a014-148">允许使用 PowerShell 脚本语言的所有元素。</span><span class="sxs-lookup"><span data-stu-id="3a014-148">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="3a014-149">可以导入 Windows 中包括的所有模块，以及模块导出在会话中运行的所有命令。</span><span class="sxs-lookup"><span data-stu-id="3a014-149">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="3a014-150">在 PowerShell 工作流中，你可以编写和运行 (以 PowerShell 语言) 编写的工作流的脚本工作流。</span><span class="sxs-lookup"><span data-stu-id="3a014-150">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="3a014-151">不支持基于 XAML 的工作流，并且不能在脚本工作流中运行 XAML，如使用 `Invoke-Expression -Language XAML` 。</span><span class="sxs-lookup"><span data-stu-id="3a014-151">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="3a014-152">此外，尽管允许嵌套工作流，但工作流不能调用其他工作流。</span><span class="sxs-lookup"><span data-stu-id="3a014-152">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="3a014-153">`Add-Type`Cmdlet 可以加载签名的程序集，但无法加载任意 c # 代码或 Win32 api。</span><span class="sxs-lookup"><span data-stu-id="3a014-153">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="3a014-154">`New-Object`Cmdlet 仅可用于) 下面列出 (允许的类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-154">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="3a014-155">只能在 PowerShell 中使用) 下面 (允许的类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-155">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="3a014-156">不允许使用其他类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-156">Other types are not permitted.</span></span>

- <span data-ttu-id="3a014-157">允许类型转换，但仅当结果为允许的类型时。</span><span class="sxs-lookup"><span data-stu-id="3a014-157">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="3a014-158">仅当生成的类型为允许的类型时，才会使用 Cmdlet 参数将字符串输入转换为类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-158">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="3a014-159">可以调用 **( # B1** 方法和 (下面列出的允许的类型的 .net 方法) 。</span><span class="sxs-lookup"><span data-stu-id="3a014-159">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="3a014-160">无法调用其他方法。</span><span class="sxs-lookup"><span data-stu-id="3a014-160">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="3a014-161">用户可以获取允许类型的所有属性。</span><span class="sxs-lookup"><span data-stu-id="3a014-161">Users can get all properties of allowed types.</span></span> <span data-ttu-id="3a014-162">用户只能在核心类型上设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="3a014-162">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="3a014-163">仅允许下列 COM 对象：</span><span class="sxs-lookup"><span data-stu-id="3a014-163">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="3a014-164">**脚本编写。字典**</span><span class="sxs-lookup"><span data-stu-id="3a014-164">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="3a014-165">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="3a014-165">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="3a014-166">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="3a014-166">**VBScript.RegExp**</span></span>

<span data-ttu-id="3a014-167">在 ConstrainedLanguage 模式下允许使用以下类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-167">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="3a014-168">用户可以获取属性、调用方法以及将对象转换为这些类型。</span><span class="sxs-lookup"><span data-stu-id="3a014-168">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="3a014-169">允许的类型：</span><span class="sxs-lookup"><span data-stu-id="3a014-169">Allowed Types:</span></span>

- <span data-ttu-id="3a014-170">AliasAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-170">AliasAttribute</span></span>
- <span data-ttu-id="3a014-171">AllowEmptyCollectionAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-171">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="3a014-172">AllowEmptyStringAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-172">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="3a014-173">AllowNullAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-173">AllowNullAttribute</span></span>
- <span data-ttu-id="3a014-174">Array</span><span class="sxs-lookup"><span data-stu-id="3a014-174">Array</span></span>
- <span data-ttu-id="3a014-175">Bool</span><span class="sxs-lookup"><span data-stu-id="3a014-175">Bool</span></span>
- <span data-ttu-id="3a014-176">字节</span><span class="sxs-lookup"><span data-stu-id="3a014-176">byte</span></span>
- <span data-ttu-id="3a014-177">char</span><span class="sxs-lookup"><span data-stu-id="3a014-177">char</span></span>
- <span data-ttu-id="3a014-178">CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-178">CmdletBindingAttribute</span></span>
- <span data-ttu-id="3a014-179">DateTime</span><span class="sxs-lookup"><span data-stu-id="3a014-179">DateTime</span></span>
- <span data-ttu-id="3a014-180">Decimal</span><span class="sxs-lookup"><span data-stu-id="3a014-180">decimal</span></span>
- <span data-ttu-id="3a014-181">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="3a014-181">DirectoryEntry</span></span>
- <span data-ttu-id="3a014-182">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="3a014-182">DirectorySearcher</span></span>
- <span data-ttu-id="3a014-183">double</span><span class="sxs-lookup"><span data-stu-id="3a014-183">double</span></span>
- <span data-ttu-id="3a014-184">FLOAT</span><span class="sxs-lookup"><span data-stu-id="3a014-184">float</span></span>
- <span data-ttu-id="3a014-185">Guid</span><span class="sxs-lookup"><span data-stu-id="3a014-185">Guid</span></span>
- <span data-ttu-id="3a014-186">Hashtable</span><span class="sxs-lookup"><span data-stu-id="3a014-186">Hashtable</span></span>
- <span data-ttu-id="3a014-187">int</span><span class="sxs-lookup"><span data-stu-id="3a014-187">int</span></span>
- <span data-ttu-id="3a014-188">Int16</span><span class="sxs-lookup"><span data-stu-id="3a014-188">Int16</span></span>
- <span data-ttu-id="3a014-189">long</span><span class="sxs-lookup"><span data-stu-id="3a014-189">long</span></span>
- <span data-ttu-id="3a014-190">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="3a014-190">ManagementClass</span></span>
- <span data-ttu-id="3a014-191">System.management.managementobject</span><span class="sxs-lookup"><span data-stu-id="3a014-191">ManagementObject</span></span>
- <span data-ttu-id="3a014-192">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="3a014-192">ManagementObjectSearcher</span></span>
- <span data-ttu-id="3a014-193">NullString</span><span class="sxs-lookup"><span data-stu-id="3a014-193">NullString</span></span>
- <span data-ttu-id="3a014-194">OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-194">OutputTypeAttribute</span></span>
- <span data-ttu-id="3a014-195">ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-195">ParameterAttribute</span></span>
- <span data-ttu-id="3a014-196">PSCredential</span><span class="sxs-lookup"><span data-stu-id="3a014-196">PSCredential</span></span>
- <span data-ttu-id="3a014-197">PSDefaultValueAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-197">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="3a014-198">PSListModifier</span><span class="sxs-lookup"><span data-stu-id="3a014-198">PSListModifier</span></span>
- <span data-ttu-id="3a014-199">PSObject</span><span class="sxs-lookup"><span data-stu-id="3a014-199">PSObject</span></span>
- <span data-ttu-id="3a014-200">PSPrimitiveDictionary</span><span class="sxs-lookup"><span data-stu-id="3a014-200">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="3a014-201">PSReference</span><span class="sxs-lookup"><span data-stu-id="3a014-201">PSReference</span></span>
- <span data-ttu-id="3a014-202">PSTypeNameAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-202">PSTypeNameAttribute</span></span>
- <span data-ttu-id="3a014-203">正则表达式</span><span class="sxs-lookup"><span data-stu-id="3a014-203">Regex</span></span>
- <span data-ttu-id="3a014-204">SByte</span><span class="sxs-lookup"><span data-stu-id="3a014-204">SByte</span></span>
- <span data-ttu-id="3a014-205">字符串</span><span class="sxs-lookup"><span data-stu-id="3a014-205">string</span></span>
- <span data-ttu-id="3a014-206">SupportsWildcardsAttribute</span><span class="sxs-lookup"><span data-stu-id="3a014-206">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="3a014-207">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3a014-207">SwitchParameter</span></span>
- <span data-ttu-id="3a014-208">System.Globalization.CultureInfo</span><span class="sxs-lookup"><span data-stu-id="3a014-208">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="3a014-209">系统 .Net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="3a014-209">System.Net.IPAddress</span></span>
- <span data-ttu-id="3a014-210">系统 MailAddress</span><span class="sxs-lookup"><span data-stu-id="3a014-210">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="3a014-211">BigInteger</span><span class="sxs-lookup"><span data-stu-id="3a014-211">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="3a014-212">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="3a014-212">System.Security.SecureString</span></span>
- <span data-ttu-id="3a014-213">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="3a014-213">TimeSpan</span></span>
- <span data-ttu-id="3a014-214">UInt16</span><span class="sxs-lookup"><span data-stu-id="3a014-214">UInt16</span></span>
- <span data-ttu-id="3a014-215">UInt32</span><span class="sxs-lookup"><span data-stu-id="3a014-215">UInt32</span></span>
- <span data-ttu-id="3a014-216">UInt64</span><span class="sxs-lookup"><span data-stu-id="3a014-216">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="3a014-217">查找会话配置的语言模式</span><span class="sxs-lookup"><span data-stu-id="3a014-217">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="3a014-218">使用会话配置文件创建会话配置时，会话配置将具有 LanguageMode 属性。</span><span class="sxs-lookup"><span data-stu-id="3a014-218">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="3a014-219">可以通过获取 LanguageMode 属性的值来找到语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-219">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="3a014-220">在其他会话配置中，你可以通过查找使用会话配置创建的会话的语言模式来间接查找语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-220">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="3a014-221">查找会话的语言模式</span><span class="sxs-lookup"><span data-stu-id="3a014-221">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="3a014-222">可以通过获取会话状态的 LanguageMode 属性的值来找到 FullLanguage 或 ConstrainedLanguage 会话的语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-222">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="3a014-223">例如：</span><span class="sxs-lookup"><span data-stu-id="3a014-223">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="3a014-224">但是，在 RestrictedLanguage 模式和 NoLanguage 模式下，不能使用点方法来获取属性值。</span><span class="sxs-lookup"><span data-stu-id="3a014-224">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="3a014-225">相反，错误消息会显示语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-225">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="3a014-226">`$ExecutionContext.SessionState.LanguageMode`在 RestrictedLanguage 会话中运行命令时，PowerShell 将返回 PropertyReferenceNotSupportedInDataSection 和 VariableReferenceNotSupportedInDataSection 错误消息。</span><span class="sxs-lookup"><span data-stu-id="3a014-226">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="3a014-227">PropertyReferenceNotSupportedInDataSection：在受限语言模式或 Data 节中不允许使用属性引用。</span><span class="sxs-lookup"><span data-stu-id="3a014-227">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="3a014-228">VariableReferenceNotSupportedInDataSection 在被限制语言模式下无法引用的变量或正在引用的数据节。</span><span class="sxs-lookup"><span data-stu-id="3a014-228">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="3a014-229">在 `$ExecutionContext.SessionState.LanguageMode` NoLanguage 会话中运行命令时，PowerShell 将返回 ScriptsNotAllowed 错误消息。</span><span class="sxs-lookup"><span data-stu-id="3a014-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="3a014-230">ScriptsNotAllowed：此运行空间不支持语法。</span><span class="sxs-lookup"><span data-stu-id="3a014-230">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="3a014-231">这可能是因为它不是语言模式。</span><span class="sxs-lookup"><span data-stu-id="3a014-231">This might be because it is in no-language mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a014-232">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a014-232">SEE ALSO</span></span>

- [<span data-ttu-id="3a014-233">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="3a014-233">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="3a014-234">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="3a014-234">about_Session_Configurations</span></span>](about_Session_Configurations.md)
