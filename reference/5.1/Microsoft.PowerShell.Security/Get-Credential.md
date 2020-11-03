---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 26c4f8c8dcc1fbd56e29f55a6a8c2e6aa37a2842
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "93200731"
---
# <span data-ttu-id="03a4f-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="03a4f-103">Get-Credential</span></span>

## <span data-ttu-id="03a4f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="03a4f-104">SYNOPSIS</span></span>
<span data-ttu-id="03a4f-105">获取基于用户名和密码的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="03a4f-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="03a4f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03a4f-106">SYNTAX</span></span>

### <span data-ttu-id="03a4f-107">CredentialSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="03a4f-107">CredentialSet (Default)</span></span>

```
Get-Credential [-Credential] <PSCredential> [<CommonParameters>]
```

### <span data-ttu-id="03a4f-108">MessageSet</span><span class="sxs-lookup"><span data-stu-id="03a4f-108">MessageSet</span></span>

```
Get-Credential -Message <String> [[-UserName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="03a4f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03a4f-109">DESCRIPTION</span></span>

<span data-ttu-id="03a4f-110">`Get-Credential`Cmdlet 将为指定的用户名和密码创建凭据对象。</span><span class="sxs-lookup"><span data-stu-id="03a4f-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="03a4f-111">你可以在安全操作中使用凭据对象。</span><span class="sxs-lookup"><span data-stu-id="03a4f-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="03a4f-112">从 PowerShell 3.0 开始，可以使用 **Message** 参数在提示用户输入其名称和密码的对话框中指定自定义消息。</span><span class="sxs-lookup"><span data-stu-id="03a4f-112">Beginning in PowerShell 3.0, you can use the **Message** parameter to specify a customized message on the dialog box that prompts the user for their name and password.</span></span>

<span data-ttu-id="03a4f-113">该 `Get-Credential` cmdlet 会提示用户输入密码或用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="03a4f-113">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="03a4f-114">默认情况下，将显示一个身份验证对话框来提示用户。</span><span class="sxs-lookup"><span data-stu-id="03a4f-114">By default, an authentication dialog box appears to prompt the user.</span></span> <span data-ttu-id="03a4f-115">但是，在某些主机程序（例如 PowerShell 控制台）中，你可以通过更改注册表项来在命令行处提示用户。</span><span class="sxs-lookup"><span data-stu-id="03a4f-115">However, in some host programs, such as the PowerShell console, you can prompt the user at the command line by changing a registry entry.</span></span> <span data-ttu-id="03a4f-116">有关此注册表项的详细信息，请参阅说明和示例。</span><span class="sxs-lookup"><span data-stu-id="03a4f-116">For more information about this registry entry, see the notes and examples.</span></span>

## <span data-ttu-id="03a4f-117">示例</span><span class="sxs-lookup"><span data-stu-id="03a4f-117">EXAMPLES</span></span>

### <span data-ttu-id="03a4f-118">示例 1</span><span class="sxs-lookup"><span data-stu-id="03a4f-118">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="03a4f-119">此命令将获取凭据对象，并将其保存在 `$c` 变量中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-119">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="03a4f-120">当你输入命令时，将显示一个请求输入用户名和密码的对话框。</span><span class="sxs-lookup"><span data-stu-id="03a4f-120">When you enter the command, a dialog box appears requesting a user name and password.</span></span> <span data-ttu-id="03a4f-121">输入所需的信息时，该 cmdlet 将创建一个表示用户凭据的 **PSCredential** 对象，并将其保存在 `$c` 变量中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-121">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="03a4f-122">你可以将对象用作请求用户身份验证的 cmdlet（例如，具有 **Credential** 参数的 cmdlet）的输入。</span><span class="sxs-lookup"><span data-stu-id="03a4f-122">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="03a4f-123">但是，某些随 PowerShell 一起安装的提供程序不支持 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="03a4f-123">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="03a4f-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="03a4f-124">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="03a4f-125">这些命令使用 cmdlet 返回的凭据对象对 `Get-Credential` 远程计算机上的用户进行身份验证，以便它们可以使用 Windows Management Instrumentation (WMI) 来管理计算机。</span><span class="sxs-lookup"><span data-stu-id="03a4f-125">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="03a4f-126">第一个命令将获取凭据对象，并将其保存在 `$c` 变量中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-126">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="03a4f-127">第二个命令使用命令中的凭据对象 `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-127">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="03a4f-128">此命令将获取 Server01 计算机上有关磁盘驱动器的信息。</span><span class="sxs-lookup"><span data-stu-id="03a4f-128">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="03a4f-129">示例 3</span><span class="sxs-lookup"><span data-stu-id="03a4f-129">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="03a4f-130">此命令显示如何将命令包含 `Get-Credential` 在命令中  `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-130">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="03a4f-131">此命令使用 `Get-CimInstance` cmdlet 来获取有关 Server01 计算机上的 BIOS 的信息。</span><span class="sxs-lookup"><span data-stu-id="03a4f-131">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="03a4f-132">它使用 **credential** 参数对 user、Domain01\User01 和 `Get-Credential` command 作为 **Credential** 参数的值进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="03a4f-132">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="03a4f-133">示例 4</span><span class="sxs-lookup"><span data-stu-id="03a4f-133">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="03a4f-134">此示例将创建一个包含用户名（不带域名）的凭据。</span><span class="sxs-lookup"><span data-stu-id="03a4f-134">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="03a4f-135">第一个命令获取用户名为 User01 的凭据，并将其存储在 `$c` 变量中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-135">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="03a4f-136">第二个命令将显示生成的凭据对象的 **Username** 属性值。</span><span class="sxs-lookup"><span data-stu-id="03a4f-136">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="03a4f-137">示例 5</span><span class="sxs-lookup"><span data-stu-id="03a4f-137">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="03a4f-138">此命令使用 **PromptForCredential** 方法提示用户输入其用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="03a4f-138">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="03a4f-139">该命令将生成的凭据保存在 `$Credential` 变量中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-139">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="03a4f-140">**PromptForCredential** 方法是使用 cmdlet 的替代方法 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-140">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="03a4f-141">使用 **PromptForCredential** 时，你可以指定要在消息框中显示的标题、消息和用户名。</span><span class="sxs-lookup"><span data-stu-id="03a4f-141">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the message box.</span></span>

<span data-ttu-id="03a4f-142">有关详细信息，请参阅 SDK 中的 [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) 文档。</span><span class="sxs-lookup"><span data-stu-id="03a4f-142">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="03a4f-143">示例 6</span><span class="sxs-lookup"><span data-stu-id="03a4f-143">Example 6</span></span>

```powershell
Set-ItemProperty "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds" -Name ConsolePrompting -Value $true
```

<span data-ttu-id="03a4f-144">此示例显示了如何修改注册表，以便在命令行处（而不是使用对话框）提示用户。</span><span class="sxs-lookup"><span data-stu-id="03a4f-144">This example shows how to modify the registry so that the user is prompted at the command line, instead of by using a dialog box.</span></span>

<span data-ttu-id="03a4f-145">该命令将创建 **ConsolePrompting** 注册表项，并将其值设置为 True。</span><span class="sxs-lookup"><span data-stu-id="03a4f-145">The command creates the **ConsolePrompting** registry entry and sets its value to True.</span></span> <span data-ttu-id="03a4f-146">若要运行此命令，请以 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03a4f-146">To run this command, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="03a4f-147">若要将对话框用于提示，请将 ConsolePrompting 的值设置为 false ($false) 或使用 cmdlet 将 `Remove-ItemProperty` 其删除。</span><span class="sxs-lookup"><span data-stu-id="03a4f-147">To use a dialog box for prompting, set the value of the ConsolePrompting to false ($false) or use the `Remove-ItemProperty` cmdlet to delete it.</span></span>

<span data-ttu-id="03a4f-148">ConsolePrompting 注册表项在某些主机程序（例如 PowerShell 控制台）中有效。</span><span class="sxs-lookup"><span data-stu-id="03a4f-148">The ConsolePrompting registry entry works in some host programs, such as the PowerShell console.</span></span> <span data-ttu-id="03a4f-149">它并非在所有主机程序中都有效。</span><span class="sxs-lookup"><span data-stu-id="03a4f-149">It might not work in all host programs.</span></span>

### <span data-ttu-id="03a4f-150">示例 7</span><span class="sxs-lookup"><span data-stu-id="03a4f-150">Example 7</span></span>

<span data-ttu-id="03a4f-151">此示例演示如何创建一个与不提示用户就返回的对象完全相同的凭据对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-151">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="03a4f-152">此方法要求输入纯文本密码，这可能会违反某些企业内的安全标准。</span><span class="sxs-lookup"><span data-stu-id="03a4f-152">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="03a4f-153">第一个命令将用户帐户名称保存在 `$User` 参数中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-153">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="03a4f-154">该值必须具有“Domain\User”或“ComputerName\User”格式。</span><span class="sxs-lookup"><span data-stu-id="03a4f-154">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="03a4f-155">第二个命令使用 `ConvertTo-SecureString` cmdlet 从纯文本密码创建一个安全字符串。</span><span class="sxs-lookup"><span data-stu-id="03a4f-155">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="03a4f-156">该命令使用 **AsPlainText** 参数来指示该字符串为纯文本，并使用 **Force** 参数来确认你了解使用纯文本的风险。</span><span class="sxs-lookup"><span data-stu-id="03a4f-156">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="03a4f-157">第三个命令使用 `New-Object` cmdlet 从和变量中的值创建 **PSCredential** 对象 `$User` `$PWord` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-157">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="03a4f-158">示例 8</span><span class="sxs-lookup"><span data-stu-id="03a4f-158">Example 8</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="03a4f-159">此命令使用 cmdlet 的 **Message** 和 **UserName** 参数 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-159">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="03a4f-160">此命令格式旨在用于共享的脚本和函数。</span><span class="sxs-lookup"><span data-stu-id="03a4f-160">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="03a4f-161">在此示例中，消息将告知用户为何需要凭据，并使他们能够确信此请求是合法的。</span><span class="sxs-lookup"><span data-stu-id="03a4f-161">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="03a4f-162">示例 9</span><span class="sxs-lookup"><span data-stu-id="03a4f-162">Example 9</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

<span data-ttu-id="03a4f-163">此命令将从 Server01 远程计算机获取凭据。</span><span class="sxs-lookup"><span data-stu-id="03a4f-163">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="03a4f-164">该命令使用 `Invoke-Command` cmdlet `Get-Credential` 在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="03a4f-164">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="03a4f-165">输出显示 `Get-Credential` 在身份验证提示中包含的远程安全消息。</span><span class="sxs-lookup"><span data-stu-id="03a4f-165">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="03a4f-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03a4f-166">PARAMETERS</span></span>

### <span data-ttu-id="03a4f-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="03a4f-167">-Credential</span></span>

<span data-ttu-id="03a4f-168">指定凭据的用户名，例如 **User01** 或 **Domain01\User01** 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-168">Specifies a user name for the credential, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="03a4f-169">参数名称 `-Credential` 是可选的。</span><span class="sxs-lookup"><span data-stu-id="03a4f-169">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="03a4f-170">提交该命令并指定用户名时，系统将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="03a4f-170">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="03a4f-171">如果省略此参数，系统会提示输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="03a4f-171">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="03a4f-172">从 PowerShell 3.0 开始，如果输入的用户名没有域，则不再在 `Get-Credential` 名称之前插入反斜杠。</span><span class="sxs-lookup"><span data-stu-id="03a4f-172">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="03a4f-173">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="03a4f-173">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="03a4f-174">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="03a4f-174">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03a4f-175">-Message</span><span class="sxs-lookup"><span data-stu-id="03a4f-175">-Message</span></span>

<span data-ttu-id="03a4f-176">指定将在身份验证提示中显示的消息。</span><span class="sxs-lookup"><span data-stu-id="03a4f-176">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="03a4f-177">此参数旨在用于函数或脚本。</span><span class="sxs-lookup"><span data-stu-id="03a4f-177">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="03a4f-178">你可以使用该消息向用户说明你为什么要请求凭据以及将如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="03a4f-178">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="03a4f-179">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="03a4f-179">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03a4f-180">-UserName</span><span class="sxs-lookup"><span data-stu-id="03a4f-180">-UserName</span></span>

<span data-ttu-id="03a4f-181">指定用户名。</span><span class="sxs-lookup"><span data-stu-id="03a4f-181">Specifies a user name.</span></span> <span data-ttu-id="03a4f-182">身份验证提示要求输入该用户名对应的密码。</span><span class="sxs-lookup"><span data-stu-id="03a4f-182">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="03a4f-183">默认情况下，用户名为空并且身份验证提示将请求输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="03a4f-183">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="03a4f-184">如果身份验证提示显示在对话框中，用户可以编辑指定的用户名。</span><span class="sxs-lookup"><span data-stu-id="03a4f-184">When the authentication prompt appears in a dialog box, the user can edit the specified user name.</span></span>
<span data-ttu-id="03a4f-185">但是，如果提示显示在命令行处，则用户不能更改用户名。</span><span class="sxs-lookup"><span data-stu-id="03a4f-185">However, the user cannot change the user name when the prompt appears at the command line.</span></span> <span data-ttu-id="03a4f-186">在共享的函数或脚本中使用此参数时，请考虑所有可能的显示情况。</span><span class="sxs-lookup"><span data-stu-id="03a4f-186">When using this parameter in a shared function or script, consider all possible presentations.</span></span>

<span data-ttu-id="03a4f-187">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="03a4f-187">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03a4f-188">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03a4f-188">CommonParameters</span></span>

<span data-ttu-id="03a4f-189">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="03a4f-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03a4f-190">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="03a4f-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03a4f-191">输入</span><span class="sxs-lookup"><span data-stu-id="03a4f-191">INPUTS</span></span>

### <span data-ttu-id="03a4f-192">无</span><span class="sxs-lookup"><span data-stu-id="03a4f-192">None</span></span>

<span data-ttu-id="03a4f-193">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="03a4f-193">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="03a4f-194">输出</span><span class="sxs-lookup"><span data-stu-id="03a4f-194">OUTPUTS</span></span>

### <span data-ttu-id="03a4f-195">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="03a4f-195">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="03a4f-196">`Get-Credential` 返回凭据对象。</span><span class="sxs-lookup"><span data-stu-id="03a4f-196">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="03a4f-197">注释</span><span class="sxs-lookup"><span data-stu-id="03a4f-197">NOTES</span></span>

<span data-ttu-id="03a4f-198">你可以使用 **PSCredential** `Get-Credential` 在请求用户身份验证的 cmdlet （例如，具有 **Credential** 参数的 Cmdlet）中创建的 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="03a4f-198">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="03a4f-199">默认情况下，身份验证提示显示在对话框中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-199">By default, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="03a4f-200">若要在命令行处显示身份验证提示，请添加 **ConsolePrompting** 注册表条目 (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) 并将其值设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-200">To display the authentication prompt at the command line, add the **ConsolePrompting** registry entry (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) and set its value to **True** .</span></span>
<span data-ttu-id="03a4f-201">如果 **ConsolePrompting** 注册表项不存在或者如果其值为 False，则身份验证提示将显示在对话框中。</span><span class="sxs-lookup"><span data-stu-id="03a4f-201">If the **ConsolePrompting** registry entry does not exist or if its value is False, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="03a4f-202">有关说明，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="03a4f-202">For instructions, see the examples.</span></span>

<span data-ttu-id="03a4f-203">**ConsolePrompting** 注册表项在 PowerShell 控制台中运行，但在所有主机程序中都不起作用。</span><span class="sxs-lookup"><span data-stu-id="03a4f-203">The **ConsolePrompting** registry entry works in the PowerShell console, but it does not work in all host programs.</span></span>

<span data-ttu-id="03a4f-204">例如， (ISE) ，它在 PowerShell 集成脚本环境中不起作用。</span><span class="sxs-lookup"><span data-stu-id="03a4f-204">For example, it has no effect in the PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="03a4f-205">有关 **ConsolePrompting** 注册表项的影响的信息，请参阅主机程序的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="03a4f-205">For information about the effect of the **ConsolePrompting** registry entry, see the help topics for the host program.</span></span>

<span data-ttu-id="03a4f-206">与 PowerShell 一起安装的所有提供程序都不支持 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="03a4f-206">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="03a4f-207">从 PowerShell 3.0 开始，在 select cmdlet （如和 cmdlet）上受 `Get-Content` 支持 `New-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="03a4f-207">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="03a4f-208">相关链接</span><span class="sxs-lookup"><span data-stu-id="03a4f-208">RELATED LINKS</span></span>

[<span data-ttu-id="03a4f-209">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="03a4f-209">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
