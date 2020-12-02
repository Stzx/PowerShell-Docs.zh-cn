---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: b6147b35a8818cf448b1e23f5458550d1c6e5c50
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "93199194"
---
# <span data-ttu-id="2c48b-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="2c48b-103">Start-Process</span></span>

## <span data-ttu-id="2c48b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2c48b-104">SYNOPSIS</span></span>
<span data-ttu-id="2c48b-105">启动本地计算机上的一个或多个进程。</span><span class="sxs-lookup"><span data-stu-id="2c48b-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="2c48b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c48b-106">SYNTAX</span></span>

### <span data-ttu-id="2c48b-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="2c48b-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [<CommonParameters>]
```

### <span data-ttu-id="2c48b-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="2c48b-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [<CommonParameters>]
```

## <span data-ttu-id="2c48b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c48b-109">DESCRIPTION</span></span>

<span data-ttu-id="2c48b-110">`Start-Process`Cmdlet 启动本地计算机上的一个或多个进程。</span><span class="sxs-lookup"><span data-stu-id="2c48b-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="2c48b-111">默认情况下， `Start-Process` 将创建一个新进程，该进程继承在当前进程中定义的所有环境变量。</span><span class="sxs-lookup"><span data-stu-id="2c48b-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="2c48b-112">若要指定在进程中运行的程序，请输入可执行文件或脚本文件，或者可使用计算机上的程序打开的文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="2c48b-113">如果指定不可执行文件，则将 `Start-Process` 启动与该文件关联的程序，类似于 `Invoke-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c48b-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="2c48b-114">您可以使用的参数 `Start-Process` 指定选项，例如加载用户配置文件、在新窗口中启动进程或使用备用凭据。</span><span class="sxs-lookup"><span data-stu-id="2c48b-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="2c48b-115">示例</span><span class="sxs-lookup"><span data-stu-id="2c48b-115">EXAMPLES</span></span>

### <span data-ttu-id="2c48b-116">示例 1：启动使用默认值的进程</span><span class="sxs-lookup"><span data-stu-id="2c48b-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="2c48b-117">此示例将启动一个进程，该进程使用 `Sort.exe` 当前文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="2c48b-118">此命令使用所有默认值，包括默认窗口样式、工作文件夹和凭据。</span><span class="sxs-lookup"><span data-stu-id="2c48b-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="2c48b-119">示例 2：打印文本文件</span><span class="sxs-lookup"><span data-stu-id="2c48b-119">Example 2: Print a text file</span></span>

<span data-ttu-id="2c48b-120">此示例启动打印文件的进程 `C:\PS-Test\MyFile.txt` 。</span><span class="sxs-lookup"><span data-stu-id="2c48b-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="2c48b-121">示例 3：启动一个进程，以对项进行排序并返回到新文件</span><span class="sxs-lookup"><span data-stu-id="2c48b-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="2c48b-122">此示例启动一个进程，该进程对文件中的项进行排序 `Testsort.txt` ，并返回文件中的已排序项 `Sorted.txt` 。</span><span class="sxs-lookup"><span data-stu-id="2c48b-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="2c48b-123">任何错误都将写入 `SortError.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="2c48b-124">**UseNewEnvironment** 参数指定进程以其自己的环境变量运行。</span><span class="sxs-lookup"><span data-stu-id="2c48b-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="2c48b-125">示例 4：在最大化窗口中启动进程</span><span class="sxs-lookup"><span data-stu-id="2c48b-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="2c48b-126">此示例将启动 `Notepad.exe` 进程。</span><span class="sxs-lookup"><span data-stu-id="2c48b-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="2c48b-127">它将最大化窗口并在该进程完成之前一直保留该窗口。</span><span class="sxs-lookup"><span data-stu-id="2c48b-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="2c48b-128">示例5：以管理员身份启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c48b-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="2c48b-129">此示例使用 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2c48b-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="2c48b-130">示例 6：使用不同动词来启动进程</span><span class="sxs-lookup"><span data-stu-id="2c48b-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="2c48b-131">此示例显示了如何查找启动进程时可以使用的谓词。</span><span class="sxs-lookup"><span data-stu-id="2c48b-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="2c48b-132">可用谓词由进程中运行的文件的文件扩展名确定。</span><span class="sxs-lookup"><span data-stu-id="2c48b-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="2c48b-133">该示例使用 `New-Object` 为 **PowerShell.exe**（在 PowerShell 进程中运行的文件）创建 **ProcessStartInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="2c48b-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe**, the file that runs in the PowerShell process.</span></span> <span data-ttu-id="2c48b-134">**ProcessStartInfo** 对象的 **谓词** 属性显示，您可以将 **Open** 和 **RunAs** 谓词与一起使用 `PowerShell.exe` ，也可以与运行文件的任何进程一起使用 `.exe` 。</span><span class="sxs-lookup"><span data-stu-id="2c48b-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="2c48b-135">示例7：指定进程的参数</span><span class="sxs-lookup"><span data-stu-id="2c48b-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="2c48b-136">这两个命令都启动 Windows 命令解释器，并对 `dir` 该文件夹发出命令 `Program Files` 。</span><span class="sxs-lookup"><span data-stu-id="2c48b-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="2c48b-137">由于此文件夹名包含空格，因此值需要用转义引号括起来。</span><span class="sxs-lookup"><span data-stu-id="2c48b-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="2c48b-138">请注意，第一个命令将字符串指定为 **ArgumentList**。</span><span class="sxs-lookup"><span data-stu-id="2c48b-138">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="2c48b-139">第二个命令是字符串数组。</span><span class="sxs-lookup"><span data-stu-id="2c48b-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="2c48b-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c48b-140">PARAMETERS</span></span>

### <span data-ttu-id="2c48b-141">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="2c48b-141">-ArgumentList</span></span>

<span data-ttu-id="2c48b-142">指定此 cmdlet 启动进程时要使用的参数或参数值。</span><span class="sxs-lookup"><span data-stu-id="2c48b-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="2c48b-143">参数可以作为单个字符串接受，其中的参数由空格分隔，或者作为以逗号分隔的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="2c48b-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="2c48b-144">如果参数或参数值包含空格，则必须用转义双引号将其引起来。</span><span class="sxs-lookup"><span data-stu-id="2c48b-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="2c48b-145">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="2c48b-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="2c48b-146">-Credential</span></span>

<span data-ttu-id="2c48b-147">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2c48b-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2c48b-148">默认情况下，该 cmdlet 使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="2c48b-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="2c48b-149">键入用户名（如 **User01** 或 **Domain01\User01**），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="2c48b-149">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2c48b-150">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="2c48b-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="2c48b-151">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="2c48b-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2c48b-152">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="2c48b-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2c48b-153">-FilePath</span></span>

<span data-ttu-id="2c48b-154">指定在进程中运行的程序的可选路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="2c48b-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="2c48b-155">输入 `.txt` `.doc` 与计算机上的程序相关联的可执行文件或文档（如或文件）的名称。</span><span class="sxs-lookup"><span data-stu-id="2c48b-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="2c48b-156">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="2c48b-156">This parameter is required.</span></span>

<span data-ttu-id="2c48b-157">如果仅指定文件名，请使用 **WorkingDirectory** 参数来指定路径。</span><span class="sxs-lookup"><span data-stu-id="2c48b-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-158">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="2c48b-158">-LoadUserProfile</span></span>

<span data-ttu-id="2c48b-159">指示此 cmdlet 为当前用户加载存储在注册表项中的 Windows 用户配置文件 `HKEY_USERS` 。</span><span class="sxs-lookup"><span data-stu-id="2c48b-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span>

<span data-ttu-id="2c48b-160">此参数不会影响 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-160">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="2c48b-161">有关详细信息，请参阅 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="2c48b-161">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-162">-NoNewWindow</span><span class="sxs-lookup"><span data-stu-id="2c48b-162">-NoNewWindow</span></span>

<span data-ttu-id="2c48b-163">在当前控制台窗口中启动新进程。</span><span class="sxs-lookup"><span data-stu-id="2c48b-163">Start the new process in the current console window.</span></span> <span data-ttu-id="2c48b-164">默认情况下，PowerShell 会打开一个新窗口。</span><span class="sxs-lookup"><span data-stu-id="2c48b-164">By default PowerShell opens a new window.</span></span>

<span data-ttu-id="2c48b-165">不能在同一命令中使用 **NoNewWindow** 参数和 **WindowStyle** 参数。</span><span class="sxs-lookup"><span data-stu-id="2c48b-165">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-166">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2c48b-166">-PassThru</span></span>

<span data-ttu-id="2c48b-167">为 cmdlet 启动的每个进程返回一个进程对象。</span><span class="sxs-lookup"><span data-stu-id="2c48b-167">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="2c48b-168">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="2c48b-168">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-169">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="2c48b-169">-RedirectStandardError</span></span>

<span data-ttu-id="2c48b-170">指定文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-170">Specifies a file.</span></span> <span data-ttu-id="2c48b-171">此 cmdlet 将进程产生的所有错误发送给指定的文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-171">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="2c48b-172">输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="2c48b-172">Enter the path and filename.</span></span> <span data-ttu-id="2c48b-173">默认情况下，在控制台中显示这些错误。</span><span class="sxs-lookup"><span data-stu-id="2c48b-173">By default, the errors are displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-174">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="2c48b-174">-RedirectStandardInput</span></span>

<span data-ttu-id="2c48b-175">指定文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-175">Specifies a file.</span></span> <span data-ttu-id="2c48b-176">此 cmdlet 从指定文件读取输入。</span><span class="sxs-lookup"><span data-stu-id="2c48b-176">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="2c48b-177">输入输入文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="2c48b-177">Enter the path and filename of the input file.</span></span> <span data-ttu-id="2c48b-178">默认情况下，进程从键盘获取其输入。</span><span class="sxs-lookup"><span data-stu-id="2c48b-178">By default, the process gets its input from the keyboard.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-179">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="2c48b-179">-RedirectStandardOutput</span></span>

<span data-ttu-id="2c48b-180">指定文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-180">Specifies a file.</span></span> <span data-ttu-id="2c48b-181">此 cmdlet 将进程产生的输出发送给指定的文件。</span><span class="sxs-lookup"><span data-stu-id="2c48b-181">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="2c48b-182">输入路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="2c48b-182">Enter the path and filename.</span></span> <span data-ttu-id="2c48b-183">默认情况下，在控制台中显示该输出。</span><span class="sxs-lookup"><span data-stu-id="2c48b-183">By default, the output is displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-184">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="2c48b-184">-UseNewEnvironment</span></span>

<span data-ttu-id="2c48b-185">指示此 cmdlet 使用为进程指定的新环境变量。</span><span class="sxs-lookup"><span data-stu-id="2c48b-185">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="2c48b-186">默认情况下，启动的进程使用继承自父进程的环境变量运行。</span><span class="sxs-lookup"><span data-stu-id="2c48b-186">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-187">-Verb</span><span class="sxs-lookup"><span data-stu-id="2c48b-187">-Verb</span></span>

<span data-ttu-id="2c48b-188">指定此 cmdlet 启动进程时要使用的动词。</span><span class="sxs-lookup"><span data-stu-id="2c48b-188">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="2c48b-189">可用的动词取决于进程中运行的文件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="2c48b-189">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="2c48b-190">下表列出了适用于某些常用进程文件类型的动词。</span><span class="sxs-lookup"><span data-stu-id="2c48b-190">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="2c48b-191">文件类型</span><span class="sxs-lookup"><span data-stu-id="2c48b-191">File type</span></span> |                <span data-ttu-id="2c48b-192">动词</span><span class="sxs-lookup"><span data-stu-id="2c48b-192">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="2c48b-193">.cmd</span><span class="sxs-lookup"><span data-stu-id="2c48b-193">.cmd</span></span>      | <span data-ttu-id="2c48b-194">Edit、Open、Print、RunAs、RunAsUser</span><span class="sxs-lookup"><span data-stu-id="2c48b-194">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="2c48b-195">.exe</span><span class="sxs-lookup"><span data-stu-id="2c48b-195">.exe</span></span>      | <span data-ttu-id="2c48b-196">Open、RunAs、RunAsUser</span><span class="sxs-lookup"><span data-stu-id="2c48b-196">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="2c48b-197">.txt</span><span class="sxs-lookup"><span data-stu-id="2c48b-197">.txt</span></span>      | <span data-ttu-id="2c48b-198">Open、Print、PrintTo</span><span class="sxs-lookup"><span data-stu-id="2c48b-198">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="2c48b-199">.wav</span><span class="sxs-lookup"><span data-stu-id="2c48b-199">.wav</span></span>      | <span data-ttu-id="2c48b-200">打开、播放</span><span class="sxs-lookup"><span data-stu-id="2c48b-200">Open, Play</span></span>                          |

<span data-ttu-id="2c48b-201">若要查找可用于进程中运行的文件的谓词，请使用 `New-Object` cmdlet 为该文件创建 **ProcessStartInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="2c48b-201">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="2c48b-202">可用谓词位于 **ProcessStartInfo** 对象的 **谓词** 属性中。</span><span class="sxs-lookup"><span data-stu-id="2c48b-202">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="2c48b-203">有关详细信息，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="2c48b-203">For details, see the examples.</span></span>

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-204">-Wait</span><span class="sxs-lookup"><span data-stu-id="2c48b-204">-Wait</span></span>

<span data-ttu-id="2c48b-205">指示此 cmdlet 等待指定的进程及其子代完成，然后再接受更多输入。</span><span class="sxs-lookup"><span data-stu-id="2c48b-205">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="2c48b-206">此参数禁止显示命令提示符，或在进程完成之前一直保留窗口。</span><span class="sxs-lookup"><span data-stu-id="2c48b-206">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-207">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="2c48b-207">-WindowStyle</span></span>

<span data-ttu-id="2c48b-208">指定用于新进程的窗口的状态。</span><span class="sxs-lookup"><span data-stu-id="2c48b-208">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="2c48b-209">此参数可接受的值包括： **普通**、 **隐藏**、 **最小化** 和 **最大化**。</span><span class="sxs-lookup"><span data-stu-id="2c48b-209">The acceptable values for this parameter are: **Normal**, **Hidden**, **Minimized**, and **Maximized**.</span></span> <span data-ttu-id="2c48b-210">默认值为 " **正常**"。</span><span class="sxs-lookup"><span data-stu-id="2c48b-210">The default value is **Normal**.</span></span>

<span data-ttu-id="2c48b-211">不能在同一命令中使用 **WindowStyle** 参数和 **NoNewWindow** 参数。</span><span class="sxs-lookup"><span data-stu-id="2c48b-211">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-212">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="2c48b-212">-WorkingDirectory</span></span>

<span data-ttu-id="2c48b-213">指定新进程的开始位置。</span><span class="sxs-lookup"><span data-stu-id="2c48b-213">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="2c48b-214">默认值是要启动的可执行文件或文档的位置。</span><span class="sxs-lookup"><span data-stu-id="2c48b-214">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="2c48b-215">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="2c48b-215">Wildcards are not supported.</span></span> <span data-ttu-id="2c48b-216">路径名不能包含将解释为通配符的字符。</span><span class="sxs-lookup"><span data-stu-id="2c48b-216">The path name must not contain characters that would be interpreted as wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c48b-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c48b-217">CommonParameters</span></span>

<span data-ttu-id="2c48b-218">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2c48b-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c48b-219">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2c48b-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c48b-220">输入</span><span class="sxs-lookup"><span data-stu-id="2c48b-220">INPUTS</span></span>

### <span data-ttu-id="2c48b-221">无</span><span class="sxs-lookup"><span data-stu-id="2c48b-221">None</span></span>

<span data-ttu-id="2c48b-222">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c48b-222">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2c48b-223">输出</span><span class="sxs-lookup"><span data-stu-id="2c48b-223">OUTPUTS</span></span>

### <span data-ttu-id="2c48b-224">无、System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="2c48b-224">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="2c48b-225">如果指定 PassThru 参数，则此 cmdlet 会生成 **System.Diagnostics.Process**。</span><span class="sxs-lookup"><span data-stu-id="2c48b-225">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="2c48b-226">否则，此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="2c48b-226">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="2c48b-227">注释</span><span class="sxs-lookup"><span data-stu-id="2c48b-227">NOTES</span></span>

- <span data-ttu-id="2c48b-228">此 cmdlet 通过使用 system.exception 类的 **Start** 方法来实现 **。**</span><span class="sxs-lookup"><span data-stu-id="2c48b-228">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="2c48b-229">有关此方法的详细信息，请参阅 [Process： Start 方法](/dotnet/api/system.diagnostics.process.start#overloads)。</span><span class="sxs-lookup"><span data-stu-id="2c48b-229">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="2c48b-230">在 Windows 上，当你使用 **UseNewEnvironment** 时，新进程将仅开始包含为 **计算机** 范围定义的默认环境变量。</span><span class="sxs-lookup"><span data-stu-id="2c48b-230">On Windows, when you use **UseNewEnvironment**, the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="2c48b-231">这会影响 `$env:USERNAME` 设置为 **SYSTEM**。</span><span class="sxs-lookup"><span data-stu-id="2c48b-231">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="2c48b-232">不包含 **用户** 范围中的任何变量。</span><span class="sxs-lookup"><span data-stu-id="2c48b-232">None of the variables from the **User** scope are included.</span></span>

## <span data-ttu-id="2c48b-233">相关链接</span><span class="sxs-lookup"><span data-stu-id="2c48b-233">RELATED LINKS</span></span>

[<span data-ttu-id="2c48b-234">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="2c48b-234">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="2c48b-235">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="2c48b-235">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="2c48b-236">Get-Process</span><span class="sxs-lookup"><span data-stu-id="2c48b-236">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="2c48b-237">Start-Service</span><span class="sxs-lookup"><span data-stu-id="2c48b-237">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="2c48b-238">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="2c48b-238">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="2c48b-239">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="2c48b-239">Wait-Process</span></span>](Wait-Process.md)
