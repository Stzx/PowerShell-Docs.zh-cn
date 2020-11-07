---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 277dd2678b54c9e708d09f6ca27d82ab9afd4c1c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347612"
---
# <span data-ttu-id="6662b-103">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="6662b-103">Get-HotFix</span></span>

## <span data-ttu-id="6662b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6662b-104">SYNOPSIS</span></span>
<span data-ttu-id="6662b-105">获取本地或远程计算机上安装的修补程序。</span><span class="sxs-lookup"><span data-stu-id="6662b-105">Gets the hotfixes that are installed on local or remote computers.</span></span>

## <span data-ttu-id="6662b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6662b-106">SYNTAX</span></span>

### <span data-ttu-id="6662b-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="6662b-107">Default (Default)</span></span>

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### <span data-ttu-id="6662b-108">说明</span><span class="sxs-lookup"><span data-stu-id="6662b-108">Description</span></span>

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## <span data-ttu-id="6662b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6662b-109">DESCRIPTION</span></span>

<span data-ttu-id="6662b-110">`Get-Hotfix`Cmdlet 可获取本地计算机或指定远程计算机上安装的修补程序或更新。</span><span class="sxs-lookup"><span data-stu-id="6662b-110">The `Get-Hotfix` cmdlet gets hotfixes, or updates, that are installed on the local computer or specified remote computers.</span></span> <span data-ttu-id="6662b-111">可以 Windows 更新、Microsoft 更新、Windows Server Update Services 或手动安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="6662b-111">The updates can be installed by Windows Update, Microsoft Update, Windows Server Update Services, or manually installed.</span></span>

## <span data-ttu-id="6662b-112">示例</span><span class="sxs-lookup"><span data-stu-id="6662b-112">EXAMPLES</span></span>

### <span data-ttu-id="6662b-113">示例1：获取本地计算机上的所有修补程序</span><span class="sxs-lookup"><span data-stu-id="6662b-113">Example 1: Get all hotfixes on the local computer</span></span>

<span data-ttu-id="6662b-114">`Get-Hotfix`Cmdlet 将获取在本地计算机上安装的所有修补程序。</span><span class="sxs-lookup"><span data-stu-id="6662b-114">The `Get-Hotfix` cmdlet gets all hotfixes installed on the local computer.</span></span>

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### <span data-ttu-id="6662b-115">示例2：从由字符串筛选的多台计算机获取修补程序</span><span class="sxs-lookup"><span data-stu-id="6662b-115">Example 2: Get hotfixes from multiple computers filtered by a string</span></span>

<span data-ttu-id="6662b-116">该 `Get-Hotfix` 命令使用参数获取远程计算机上安装的修补程序。</span><span class="sxs-lookup"><span data-stu-id="6662b-116">The `Get-Hotfix` command uses parameters to get hotfixes installed on remote computers.</span></span> <span data-ttu-id="6662b-117">结果按指定的描述字符串进行筛选。</span><span class="sxs-lookup"><span data-stu-id="6662b-117">The results are filtered by a specified description string.</span></span>

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

<span data-ttu-id="6662b-118">`Get-Hotfix` 用 **Description** 参数和包含星号 () 通配符的字符串 **安全** 筛选输出 `*` 。</span><span class="sxs-lookup"><span data-stu-id="6662b-118">`Get-Hotfix` filters the output with the **Description** parameter and the string **Security** that includes the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="6662b-119">**ComputerName** 参数包含以逗号分隔的远程计算机名字符串。</span><span class="sxs-lookup"><span data-stu-id="6662b-119">The **ComputerName** parameter includes a comma-separated string of remote computer names.</span></span> <span data-ttu-id="6662b-120">**Credential** 参数指定有权访问远程计算机并运行命令的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6662b-120">The **Credential** parameter specifies a user account that has permission to access the remote computers and run commands.</span></span>

### <span data-ttu-id="6662b-121">示例3：验证是否已安装更新并将计算机名称写入文件</span><span class="sxs-lookup"><span data-stu-id="6662b-121">Example 3: Verify if an update is installed and write computer names to a file</span></span>

<span data-ttu-id="6662b-122">此示例中的命令验证是否安装了特定更新。</span><span class="sxs-lookup"><span data-stu-id="6662b-122">The commands in this example verify whether a particular update installed.</span></span> <span data-ttu-id="6662b-123">如果未安装该更新，则会将计算机名称写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="6662b-123">If the update isn't installed, the computer name is written to a text file.</span></span>

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

<span data-ttu-id="6662b-124">`$A`变量包含通过文本文件获取的计算机名称 `Get-Content` 。</span><span class="sxs-lookup"><span data-stu-id="6662b-124">The `$A` variable contains computer names that were obtained by `Get-Content` from a text file.</span></span> <span data-ttu-id="6662b-125">中的对象 `$A` 将向下发送到 `ForEach-Object` 。</span><span class="sxs-lookup"><span data-stu-id="6662b-125">The objects in `$A` are sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="6662b-126">`if`语句将 cmdlet 用于 `Get-Hotfix` **Id** 参数，并为每个计算机名称使用特定 id 号。</span><span class="sxs-lookup"><span data-stu-id="6662b-126">An `if` statement uses the `Get-Hotfix` cmdlet with the **Id** parameter and a specific Id number for each computer name.</span></span> <span data-ttu-id="6662b-127">如果计算机未安装指定的修补程序 Id，则该 `Add-Content` cmdlet 会将计算机名称写入文件。</span><span class="sxs-lookup"><span data-stu-id="6662b-127">If a computer doesn't have the specified hotfix Id installed, the `Add-Content` cmdlet writes the computer name to a file.</span></span>

### <span data-ttu-id="6662b-128">示例4：获取本地计算机上的最新修补程序</span><span class="sxs-lookup"><span data-stu-id="6662b-128">Example 4: Get the most recent hotfix on the local computer</span></span>

<span data-ttu-id="6662b-129">此示例获取计算机上安装的最新修补程序。</span><span class="sxs-lookup"><span data-stu-id="6662b-129">This example gets the most recent hotfix installed on a computer.</span></span>

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

<span data-ttu-id="6662b-130">`Get-Hotfix` 将对象向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6662b-130">`Get-Hotfix` sends the objects down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="6662b-131">`Sort-Object` 按升序对对象排序，并使用 **Property** 参数来评估每个 **InstalledOn** 日期。</span><span class="sxs-lookup"><span data-stu-id="6662b-131">`Sort-Object` sorts objects by ascending order and uses the **Property** parameter to evaluate each **InstalledOn** date.</span></span> <span data-ttu-id="6662b-132">数组表示法 `[-1]` 选择最新安装的修补程序。</span><span class="sxs-lookup"><span data-stu-id="6662b-132">The array notation `[-1]` selects the most recent installed hotfix.</span></span>

## <span data-ttu-id="6662b-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6662b-133">PARAMETERS</span></span>

### <span data-ttu-id="6662b-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6662b-134">-ComputerName</span></span>

<span data-ttu-id="6662b-135">指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="6662b-135">Specifies a remote computer.</span></span> <span data-ttu-id="6662b-136">键入远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6662b-136">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>

<span data-ttu-id="6662b-137">当 **ComputerName** 参数未指定时， `Get-Hotfix` 将在本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="6662b-137">When the **ComputerName** parameter isn't specified, `Get-Hotfix` runs on the local computer.</span></span>

<span data-ttu-id="6662b-138">**ComputerName** 参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="6662b-138">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="6662b-139">如果你的计算机未配置为运行远程命令，请使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="6662b-139">If your computer isn't configured to run remote commands, use the **ComputerName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6662b-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="6662b-140">-Credential</span></span>

<span data-ttu-id="6662b-141">指定有权访问计算机并运行命令的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6662b-141">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="6662b-142">默认值为当前用户</span><span class="sxs-lookup"><span data-stu-id="6662b-142">The default is the current user</span></span>

<span data-ttu-id="6662b-143">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="6662b-143">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="6662b-144">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="6662b-144">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="6662b-145">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="6662b-145">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="6662b-146">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="6662b-146">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6662b-147">-Description</span><span class="sxs-lookup"><span data-stu-id="6662b-147">-Description</span></span>

<span data-ttu-id="6662b-148">`Get-HotFix` 使用 **Description** 参数指定修补程序类型。</span><span class="sxs-lookup"><span data-stu-id="6662b-148">`Get-HotFix` uses the **Description** parameter to specify hotfix types.</span></span> <span data-ttu-id="6662b-149">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="6662b-149">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6662b-150">-Id</span><span class="sxs-lookup"><span data-stu-id="6662b-150">-Id</span></span>

<span data-ttu-id="6662b-151">筛选 `Get-HotFix` 特定修补程序 id 的结果。</span><span class="sxs-lookup"><span data-stu-id="6662b-151">Filters the `Get-HotFix` results for specific hotfix Ids.</span></span> <span data-ttu-id="6662b-152">不接受通配符。</span><span class="sxs-lookup"><span data-stu-id="6662b-152">Wildcards aren't accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6662b-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6662b-153">CommonParameters</span></span>

<span data-ttu-id="6662b-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6662b-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6662b-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6662b-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6662b-156">输入</span><span class="sxs-lookup"><span data-stu-id="6662b-156">INPUTS</span></span>

### <span data-ttu-id="6662b-157">字符串</span><span class="sxs-lookup"><span data-stu-id="6662b-157">String</span></span>

<span data-ttu-id="6662b-158">可以通过管道将一个或多个计算机名称传递给修补程序。</span><span class="sxs-lookup"><span data-stu-id="6662b-158">You can pipe one or more computer names to Get-HotFix.</span></span>

## <span data-ttu-id="6662b-159">输出</span><span class="sxs-lookup"><span data-stu-id="6662b-159">OUTPUTS</span></span>

### <span data-ttu-id="6662b-160">System.management.managementobject # root\CIMV2\ Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="6662b-160">System.Management.ManagementObject#root\CIMV2\Win32_QuickFixEngineering</span></span>

<span data-ttu-id="6662b-161">`Get-HotFix` 返回表示计算机上的修补程序的对象。</span><span class="sxs-lookup"><span data-stu-id="6662b-161">`Get-HotFix` returns objects that represent the hotfixes on the computer.</span></span>

## <span data-ttu-id="6662b-162">注释</span><span class="sxs-lookup"><span data-stu-id="6662b-162">NOTES</span></span>

<span data-ttu-id="6662b-163">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="6662b-163">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="6662b-164">**Win32_QuickFixEngineering** [WMI 类](/windows/desktop/WmiSdk/retrieving-a-class)表示系统范围较小的更新，通常称为 "快速修补工程"， (QFE) update，应用于当前操作系统。</span><span class="sxs-lookup"><span data-stu-id="6662b-164">The **Win32_QuickFixEngineering** [WMI class](/windows/desktop/WmiSdk/retrieving-a-class) represents a small system-wide update, commonly referred to as a quick-fix engineering (QFE) update, applied to the current operating system.</span></span> <span data-ttu-id="6662b-165">此类仅返回由基于组件的服务所提供的更新 (CBS) 。</span><span class="sxs-lookup"><span data-stu-id="6662b-165">This class returns only the updates supplied by Component Based Servicing (CBS).</span></span> <span data-ttu-id="6662b-166">注册表中未列出这些更新。</span><span class="sxs-lookup"><span data-stu-id="6662b-166">These updates are not listed in the registry.</span></span> <span data-ttu-id="6662b-167">**Win32_QuickFixEngineering** 未返回 MICROSOFT WINDOWS INSTALLER (MSI) 或 [Windows 更新](https://update.microsoft.com)站点提供的更新。</span><span class="sxs-lookup"><span data-stu-id="6662b-167">Updates supplied by Microsoft Windows Installer (MSI) or the [Windows Update](https://update.microsoft.com) site are not returned by **Win32_QuickFixEngineering**.</span></span> <span data-ttu-id="6662b-168">有关详细信息，请参阅 [Win32_QuickFixEngineering 类](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)。</span><span class="sxs-lookup"><span data-stu-id="6662b-168">For more information, see [Win32_QuickFixEngineering class](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span></span>

<span data-ttu-id="6662b-169">`Get-HotFix`不同操作系统上的输出可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="6662b-169">The `Get-HotFix` output might vary on different operating systems.</span></span>

## <span data-ttu-id="6662b-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="6662b-170">RELATED LINKS</span></span>

[<span data-ttu-id="6662b-171">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="6662b-171">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="6662b-172">Add-Content</span><span class="sxs-lookup"><span data-stu-id="6662b-172">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="6662b-173">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="6662b-173">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="6662b-174">Win32_QuickFixEngineering 类</span><span class="sxs-lookup"><span data-stu-id="6662b-174">Win32_QuickFixEngineering class</span></span>](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
