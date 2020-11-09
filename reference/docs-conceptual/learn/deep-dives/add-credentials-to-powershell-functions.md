---
title: 向 PowerShell 函数添加凭据支持
description: 如何向 PowerShell 脚本、函数和 cmdlet 添加凭据参数。
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: 3e4a3f41ccbca1cf97f2e96fd60f22d89be7bc5a
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354620"
---
# <a name="add-credential-support-to-powershell-functions"></a><span data-ttu-id="8dd42-103">向 PowerShell 函数添加凭据支持</span><span class="sxs-lookup"><span data-stu-id="8dd42-103">Add Credential support to PowerShell functions</span></span>

> [!NOTE]
> <span data-ttu-id="8dd42-104">本文的[原始版本][]发布在 [@joshduffney][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="8dd42-104">The [original version][] of this article appeared on the blog written by [@joshduffney][].</span></span> <span data-ttu-id="8dd42-105">此文已经过编辑，以便发布在本站点中。</span><span class="sxs-lookup"><span data-stu-id="8dd42-105">This article has been edited for inclusion on this site.</span></span> <span data-ttu-id="8dd42-106">PowerShell 团队感谢 Josh 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="8dd42-106">The PowerShell team thanks Josh for sharing this content with us.</span></span> <span data-ttu-id="8dd42-107">若要访问他的博客，请访问 [duffney.io][]。</span><span class="sxs-lookup"><span data-stu-id="8dd42-107">Please check out his blog at [duffney.io][].</span></span>

<span data-ttu-id="8dd42-108">本文介绍了如何向 PowerShell 函数添加凭据以及这样做的理由。</span><span class="sxs-lookup"><span data-stu-id="8dd42-108">This article shows you how to add credential parameters to PowerShell functions and why you'd want to.</span></span> <span data-ttu-id="8dd42-109">凭据参数用于允许你以其他用户的身份运行函数或 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-109">A credential parameter is to allow you to run the function or cmdlet as a different user.</span></span> <span data-ttu-id="8dd42-110">最常见的用途是以提升的用户帐户身份运行函数或 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-110">The most common use is to run the function or cmdlet as an elevated user account.</span></span>

<span data-ttu-id="8dd42-111">例如，cmdlet `New-ADUser` 包含“凭据”参数，你可以在此参数中提供域管理员凭据，以便在域中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="8dd42-111">For example, the cmdlet `New-ADUser` has a **Credential** parameter, which you could provide domain admin credentials to create an account in a domain.</span></span> <span data-ttu-id="8dd42-112">假设你用于运行 PowerShell 会话的常规帐户尚没有上述访问权限。</span><span class="sxs-lookup"><span data-stu-id="8dd42-112">Assuming your normal account running the PowerShell session doesn't have that access already.</span></span>

## <a name="creating-credential-object"></a><span data-ttu-id="8dd42-113">创建凭据对象</span><span class="sxs-lookup"><span data-stu-id="8dd42-113">Creating credential object</span></span>

<span data-ttu-id="8dd42-114">[PSCredential][] 对象表示一组安全凭据，例如用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-114">The [PSCredential][] object represents a set of security credentials such as a user name and password.</span></span> <span data-ttu-id="8dd42-115">此对象可以作为参数传递给函数，以便该函数以此凭据对象中的用户帐户身份运行。</span><span class="sxs-lookup"><span data-stu-id="8dd42-115">The object can be passed as a parameter to a function that runs as the user account in that credential object.</span></span> <span data-ttu-id="8dd42-116">可使用下面的几种方法创建凭据对象。</span><span class="sxs-lookup"><span data-stu-id="8dd42-116">There are a few ways that you can create a credential object.</span></span> <span data-ttu-id="8dd42-117">创建凭据对象的第一种方法是使用 PowerShell cmdlet `Get-Credential`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-117">The first way to create a credential object is to use the PowerShell cmdlet `Get-Credential`.</span></span> <span data-ttu-id="8dd42-118">在未使用参数的情况下运行它时，系统会提示你输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-118">When you run without parameters, it prompts you for a username and password.</span></span> <span data-ttu-id="8dd42-119">你也可以使用一些可选参数来调用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-119">Or you can call the cmdlet with some optional parameters.</span></span>

<span data-ttu-id="8dd42-120">若要预先指定域名和用户名，可以使用“凭据”或“用户名”参数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-120">To specify the domain name and username ahead of time you can use either the **Credential** or **UserName** parameters.</span></span> <span data-ttu-id="8dd42-121">使用“用户名”参数时，你还需要提供“邮件”值。</span><span class="sxs-lookup"><span data-stu-id="8dd42-121">When you use the **UserName** parameter, you're also required to provide a **Message** value.</span></span> <span data-ttu-id="8dd42-122">以下代码演示了如何使用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-122">The code below demonstrates using the cmdlet.</span></span> <span data-ttu-id="8dd42-123">也可以将凭据对象存储在变量中，以便可以多次使用该凭据。</span><span class="sxs-lookup"><span data-stu-id="8dd42-123">You can also store the credential object in a variable so that you can use the credential multiple times.</span></span> <span data-ttu-id="8dd42-124">下面的示例将凭据对象存储到了变量 `$Cred` 中。</span><span class="sxs-lookup"><span data-stu-id="8dd42-124">In the example below, the credential object is stored in the variable `$Cred`.</span></span>

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

<span data-ttu-id="8dd42-125">有时，无法使用上面示例所示的交互式方法创建凭据对象。</span><span class="sxs-lookup"><span data-stu-id="8dd42-125">Sometimes, you can't use the interactive method of creating credential objects shown in the previous example.</span></span> <span data-ttu-id="8dd42-126">大多数自动化工具都需要使用非交互式方法。</span><span class="sxs-lookup"><span data-stu-id="8dd42-126">Most automation tools require a non-interactive method.</span></span> <span data-ttu-id="8dd42-127">若要在无用户交互的情况下创建凭据，请创建一个包含密码的安全字符串。</span><span class="sxs-lookup"><span data-stu-id="8dd42-127">To create a credential without user interaction, create a secure string containing the password.</span></span> <span data-ttu-id="8dd42-128">然后，将安全字符串和用户名传递到 `System.Management.Automation.PSCredential()` 方法。</span><span class="sxs-lookup"><span data-stu-id="8dd42-128">Then pass the secure string and user name to the `System.Management.Automation.PSCredential()` method.</span></span>

<span data-ttu-id="8dd42-129">请使用下面的命令创建一个包含密码的安全字符串：</span><span class="sxs-lookup"><span data-stu-id="8dd42-129">Use the following command to create a secure string containing the password:</span></span>

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

<span data-ttu-id="8dd42-130">需要提供“AsPlainText”和“强制”参数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-130">Both the **AsPlainText** and **Force** parameters are required.</span></span> <span data-ttu-id="8dd42-131">如果没有提供这些参数，你将收到一条警告消息，其中会提示你不得将纯文本传递到安全字符串中。</span><span class="sxs-lookup"><span data-stu-id="8dd42-131">Without those parameters, you receive a message warning that you shouldn't pass plain text into a secure string.</span></span> <span data-ttu-id="8dd42-132">由于纯文本密码会记录在各种日志中，因此 PowerShell 会返回此警告。</span><span class="sxs-lookup"><span data-stu-id="8dd42-132">PowerShell returns this warning because the plain text password gets recorded in various logs.</span></span> <span data-ttu-id="8dd42-133">创建安全字符串后，需要将其传递到 `PSCredential()` 方法，以创建凭据对象。</span><span class="sxs-lookup"><span data-stu-id="8dd42-133">Once you have a secure string created, you need to pass it to the `PSCredential()` method to create the credential object.</span></span> <span data-ttu-id="8dd42-134">在下面的示例中，变量 `$password` 包含安全字符串，`$Cred` 包含凭据对象。</span><span class="sxs-lookup"><span data-stu-id="8dd42-134">In the following example, the variable `$password` contains the secure string `$Cred` contains the credential object.</span></span>

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

<span data-ttu-id="8dd42-135">现在你已了解如何创建凭据对象，接下来就可以向 PowerShell 函数添加凭据参数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-135">Now that you know how to create credential objects, you can add credential parameters to your PowerShell functions.</span></span>

## <a name="adding-a-credential-parameter"></a><span data-ttu-id="8dd42-136">添加凭据参数</span><span class="sxs-lookup"><span data-stu-id="8dd42-136">Adding a Credential Parameter</span></span>

<span data-ttu-id="8dd42-137">就像添加任何其他参数一样，首先要将其添加到函数的 `param` 块中。</span><span class="sxs-lookup"><span data-stu-id="8dd42-137">Just like any other parameter, you start off by adding it in the `param` block of your function.</span></span>
<span data-ttu-id="8dd42-138">建议将此参数命名为 `$Credential`，因为现有的 PowerShell cmdlet 都使用此名称。</span><span class="sxs-lookup"><span data-stu-id="8dd42-138">It's recommended that you name the parameter `$Credential` because that's what existing PowerShell cmdlets use.</span></span> <span data-ttu-id="8dd42-139">此参数的类型应为 `[System.Management.Automation.PSCredential]`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-139">The type of the parameter should be `[System.Management.Automation.PSCredential]`.</span></span>

<span data-ttu-id="8dd42-140">下面的示例显示了名为 `Get-Something` 的函数的参数块。</span><span class="sxs-lookup"><span data-stu-id="8dd42-140">The following example shows the parameter block for a function called `Get-Something`.</span></span> <span data-ttu-id="8dd42-141">该参数块包含两个参数：`$Name` 和 `$Credential`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-141">It has two parameters: `$Name` and `$Credential`.</span></span>

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

<span data-ttu-id="8dd42-142">此示例中的代码足以生成一个可用的凭据参数，不过你还可以添加一些内容来使其更加可靠。</span><span class="sxs-lookup"><span data-stu-id="8dd42-142">The code in this example is enough to have a working credential parameter, however there are a few things you can add to make it more robust.</span></span>

- <span data-ttu-id="8dd42-143">添加 `[ValidateNotNull()]` 验证属性，用于检查要传递给凭据的值。</span><span class="sxs-lookup"><span data-stu-id="8dd42-143">Add the `[ValidateNotNull()]` validation attribute to check that the value being passed to **Credential**.</span></span> <span data-ttu-id="8dd42-144">如果参数值为 null，此属性将阻止函数使用无效的凭据执行。</span><span class="sxs-lookup"><span data-stu-id="8dd42-144">If the parameter value is null, this attribute prevents the function from executing with invalid credentials.</span></span>

- <span data-ttu-id="8dd42-145">添加 `[System.Management.Automation.Credential()]`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-145">Add `[System.Management.Automation.Credential()]`.</span></span> <span data-ttu-id="8dd42-146">它将允许你以字符串形式传入用户名，并可提供交互式密码提示。</span><span class="sxs-lookup"><span data-stu-id="8dd42-146">This allows you to pass in a username as a string and have an interactive prompt for the password.</span></span>

- <span data-ttu-id="8dd42-147">将 `$Credential` 参数的默认值设置为 `[System.Management.Automation.PSCredential]::Empty`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-147">Set a default value for the `$Credential` parameter to `[System.Management.Automation.PSCredential]::Empty`.</span></span> <span data-ttu-id="8dd42-148">你的函数可能会将此 `$Credential` 对象传递到现有的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-148">Your function you might be passing this `$Credential` object to existing PowerShell cmdlets.</span></span> <span data-ttu-id="8dd42-149">向函数调用的 cmdlet 提供 null 值，这会引发错误。</span><span class="sxs-lookup"><span data-stu-id="8dd42-149">Providing a null value to the cmdlet called inside your function causes an error.</span></span> <span data-ttu-id="8dd42-150">提供空凭据对象可以避免此错误。</span><span class="sxs-lookup"><span data-stu-id="8dd42-150">Providing an empty credential object avoids this error.</span></span>

> [!TIP]
> <span data-ttu-id="8dd42-151">某些接受凭据参数的 cmdlet 不能按照预期方式支持 `[System.Management.Automation.PSCredential]::Empty`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-151">Some cmdlets that accept a credential parameter do not support `[System.Management.Automation.PSCredential]::Empty` as they should.</span></span> <span data-ttu-id="8dd42-152">有关解决方法的信息，请参阅[处理旧版 Cmdlet](#dealing-with-legacy-cmdlets) 部分。</span><span class="sxs-lookup"><span data-stu-id="8dd42-152">See the [Dealing with Legacy Cmdlets](#dealing-with-legacy-cmdlets) section for a workaround.</span></span>

## <a name="using-credential-parameters"></a><span data-ttu-id="8dd42-153">使用凭据参数</span><span class="sxs-lookup"><span data-stu-id="8dd42-153">Using credential parameters</span></span>

<span data-ttu-id="8dd42-154">下面的示例演示了凭据参数的用法。</span><span class="sxs-lookup"><span data-stu-id="8dd42-154">The following example demonstrates how to use credential parameters.</span></span> <span data-ttu-id="8dd42-155">此示例显示了一个名为 `Set-RemoteRegistryValue` 的函数，该函数出自 [The Pester Book][]。</span><span class="sxs-lookup"><span data-stu-id="8dd42-155">This example shows a function called `Set-RemoteRegistryValue`, which is out of [The Pester Book][].</span></span> <span data-ttu-id="8dd42-156">此函数使用前面部分所述的技巧定义了凭据参数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-156">This function defines the credential parameter using the techniques describe in the previous section.</span></span> <span data-ttu-id="8dd42-157">此函数使用其创建的 `$Credential` 变量调用 `Invoke-Command`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-157">The function calls `Invoke-Command` using the `$Credential` variable created by the function.</span></span> <span data-ttu-id="8dd42-158">这样即可以更改运行 `Invoke-Command` 的用户。</span><span class="sxs-lookup"><span data-stu-id="8dd42-158">This allows you to change the user who's running `Invoke-Command`.</span></span> <span data-ttu-id="8dd42-159">由于 `$Credential` 的默认值为空凭据，因此可以在不提供凭据的情况下运行该函数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-159">Because the default value of `$Credential` is an empty credential, the function can run without providing credentials.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

<span data-ttu-id="8dd42-160">以下各个部分介绍了向 `Set-RemoteRegistryValue` 提供凭据的不同方法。</span><span class="sxs-lookup"><span data-stu-id="8dd42-160">The following sections show different methods of providing credentials to `Set-RemoteRegistryValue`.</span></span>

### <a name="prompting-for-credentials"></a><span data-ttu-id="8dd42-161">提示输入凭据</span><span class="sxs-lookup"><span data-stu-id="8dd42-161">Prompting for credentials</span></span>

<span data-ttu-id="8dd42-162">运行时在括号 `()` 中使用 `Get-Credential`，这样将优先运行 `Get-credential`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-162">Using `Get-Credential` in parentheses `()` at run time causes the `Get-credential` to run first.</span></span> <span data-ttu-id="8dd42-163">系统提示输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-163">You are prompted for a username and password.</span></span> <span data-ttu-id="8dd42-164">可以使用 `Get-credential` 的“凭据”或“用户名”参数来预填充用户名和域。</span><span class="sxs-lookup"><span data-stu-id="8dd42-164">You could use the **Credential** or **UserName** parameters of `Get-credential` to pre-populate the username and domain.</span></span> <span data-ttu-id="8dd42-165">下面的示例使用展开技术将参数传递给 `Set-RemoteRegistryValue` 函数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-165">The following example uses a technique called splatting to pass parameters to the `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="8dd42-166">有关展开技术的详细信息，请参阅 [about_Splatting][] 一文。</span><span class="sxs-lookup"><span data-stu-id="8dd42-166">For more information about splatting, check out the [about_Splatting][] article.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![在运行时获取凭据](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

<span data-ttu-id="8dd42-168">使用 `(Get-Credential)` 似乎很繁琐。</span><span class="sxs-lookup"><span data-stu-id="8dd42-168">Using `(Get-Credential)` seems cumbersome.</span></span> <span data-ttu-id="8dd42-169">通常，如果仅将凭据参数与一个用户名一起使用时，该 cmdlet 会自动提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-169">Normally, when you use the **Credential** parameter with only a username, the cmdlet automatically prompts for the password.</span></span> <span data-ttu-id="8dd42-170">`[System.Management.Automation.Credential()]` 属性将实现此行为。</span><span class="sxs-lookup"><span data-stu-id="8dd42-170">The `[System.Management.Automation.Credential()]` attribute enables this behavior.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![提示输入凭据](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> <span data-ttu-id="8dd42-172">这些示例假定你已安装 Windows 的 Web 服务器功能，以便可以设置所显示的注册表值。</span><span class="sxs-lookup"><span data-stu-id="8dd42-172">To set the registry value shown, these examples assume you have the **Web Server** features of Windows installed.</span></span> <span data-ttu-id="8dd42-173">如果需要，可运行 `Install-WindowsFeature Web-Server` 和 `Install-WindowsFeature web-mgmt-tools`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-173">Run `Install-WindowsFeature Web-Server` and `Install-WindowsFeature web-mgmt-tools` if required.</span></span>

### <a name="provide-credentials-in-a-variable"></a><span data-ttu-id="8dd42-174">以变量形式提供凭据</span><span class="sxs-lookup"><span data-stu-id="8dd42-174">Provide credentials in a variable</span></span>

<span data-ttu-id="8dd42-175">也可以预先填充凭据变量，并将其传递给 `Set-RemoteRegistryValue` 函数的凭据参数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-175">You can also populate a credential variable ahead of time and pass it to the **Credential** parameter of `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="8dd42-176">可将此方法与持续集成/持续部署 (CI/CD) 工具（例如 Jenkins、TeamCity 和 Octopus Deploy）一起使用。</span><span class="sxs-lookup"><span data-stu-id="8dd42-176">Use this method with Continuous Integration / Continuous Deployment (CI/CD) tools such as Jenkins, TeamCity, and Octopus Deploy.</span></span> <span data-ttu-id="8dd42-177">可参阅 Hodge 的博客文章[使用 Windows 上的 Jenkins 和 PowerShell 实现自动化 - 第 2 部分][]来查看使用 Jenkins 的示例。</span><span class="sxs-lookup"><span data-stu-id="8dd42-177">For an example using Jenkins, check out Hodge's blog post [Automating with Jenkins and PowerShell on Windows - Part 2][].</span></span>

<span data-ttu-id="8dd42-178">此示例使用 .NET 方法创建凭据对象和安全字符串来传入密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-178">This example uses the .NET method to create the credential object and a secure string to pass in the password.</span></span>

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

<span data-ttu-id="8dd42-179">在此示例中，安全字符串由明文密码创建而成。</span><span class="sxs-lookup"><span data-stu-id="8dd42-179">For this example, the secure string is created using a clear text password.</span></span> <span data-ttu-id="8dd42-180">前面提到的所有 CI/CD 都可在运行时通过安全的方式提供该密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-180">All of the previously mentioned CI/CD have a secure method of providing that password at run time.</span></span> <span data-ttu-id="8dd42-181">使用这些工具时，请将纯文本密码替换为使用的 CI/CD 工具中定义的变量。</span><span class="sxs-lookup"><span data-stu-id="8dd42-181">When using those tools, replace the plain text password with the variable defined within the CI/CD tool you use.</span></span>

### <a name="run-without-credentials"></a><span data-ttu-id="8dd42-182">在不提供凭据的情况下运行</span><span class="sxs-lookup"><span data-stu-id="8dd42-182">Run without credentials</span></span>

<span data-ttu-id="8dd42-183">由于 `$Credential` 的默认值为空凭据对象，因此可以在不提供凭据的情况下运行此命令，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8dd42-183">Since `$Credential` defaults to an empty credential object, you can run the command without credentials, as shown in this example:</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a><span data-ttu-id="8dd42-184">使用旧版 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8dd42-184">Dealing with legacy cmdlets</span></span>

<span data-ttu-id="8dd42-185">并非所有 cmdlet 都支持凭据对象或都允许空凭据。</span><span class="sxs-lookup"><span data-stu-id="8dd42-185">Not all cmdlets support credential objects or allow empty credentials.</span></span> <span data-ttu-id="8dd42-186">cmdlet 可能希望用户名和密码参数是字符串形式。</span><span class="sxs-lookup"><span data-stu-id="8dd42-186">Instead, the cmdlet wants username and password parameters as strings.</span></span> <span data-ttu-id="8dd42-187">可通过以下几种方法解决这种局限性。</span><span class="sxs-lookup"><span data-stu-id="8dd42-187">There are a few ways to work around this limitation.</span></span>

### <a name="using-if-else-to-handle-empty-credentials"></a><span data-ttu-id="8dd42-188">使用 if-else 处理空凭据</span><span class="sxs-lookup"><span data-stu-id="8dd42-188">Using if-else to handle empty credentials</span></span>

<span data-ttu-id="8dd42-189">在这种情况下，你想要运行的 cmdlet 不接受空凭据对象。</span><span class="sxs-lookup"><span data-stu-id="8dd42-189">In this scenario, the cmdlet you want to run doesn't accept an empty credential object.</span></span> <span data-ttu-id="8dd42-190">此示例仅在凭据参数不为空时将其添加到 `Invoke-Command`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-190">This example adds the **Credential** parameter to `Invoke-Command` only if it's not empty.</span></span> <span data-ttu-id="8dd42-191">否则，它将运行不含凭据参数的 `Invoke-Command`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-191">Otherwise, it runs the `Invoke-Command` without the **Credential** parameter.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a><span data-ttu-id="8dd42-192">使用展开技术处理空凭据</span><span class="sxs-lookup"><span data-stu-id="8dd42-192">Using splatting to handle empty credentials</span></span>

<span data-ttu-id="8dd42-193">此示例使用参数展开技术调用旧版 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-193">This example uses parameter splatting to call the legacy cmdlet.</span></span> <span data-ttu-id="8dd42-194">`$Credential` 对象会根据条件添加到哈希表进行展开，因此无需再重复执行 `Invoke-Command` 脚本块。</span><span class="sxs-lookup"><span data-stu-id="8dd42-194">The `$Credential` object is conditionally added to the hash table for splatting and avoids the need to repeat the `Invoke-Command` script block.</span></span> <span data-ttu-id="8dd42-195">若要详细了解函数内的展开技术，请参阅博客文章[展开高级函数内的参数][]。</span><span class="sxs-lookup"><span data-stu-id="8dd42-195">To learn more about splatting inside functions, see the [Splatting Parameters Inside Advanced Functions][] blog post.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a><span data-ttu-id="8dd42-196">使用字符串密码</span><span class="sxs-lookup"><span data-stu-id="8dd42-196">Working with string passwords</span></span>

<span data-ttu-id="8dd42-197">`Invoke-Sqlcmd` cmdlet 是一种接受字符串密码的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8dd42-197">The `Invoke-Sqlcmd` cmdlet is an example of a cmdlet that accepts a string as a password.</span></span>
<span data-ttu-id="8dd42-198">`Invoke-Sqlcmd` 可允许你运行简单的 SQL 插入、更新和删除语句。</span><span class="sxs-lookup"><span data-stu-id="8dd42-198">`Invoke-Sqlcmd` allows you to run simple SQL insert, update, and delete statements.</span></span> <span data-ttu-id="8dd42-199">`Invoke-Sqlcmd` 需要使用明文用户名和密码，而不使用更加安全的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="8dd42-199">`Invoke-Sqlcmd` requires a clear-text username and password rather than a more secure credential object.</span></span> <span data-ttu-id="8dd42-200">此示例演示如何从凭据对象中提取用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8dd42-200">This example shows how to extract the username and password from a credential object.</span></span>

<span data-ttu-id="8dd42-201">本示例中的 `Get-AllSQLDatabases` 函数将调用 `Invoke-Sqlcmd` cmdlet 来查询 SQL Server 中的所有数据库。</span><span class="sxs-lookup"><span data-stu-id="8dd42-201">The `Get-AllSQLDatabases` function in this example calls the `Invoke-Sqlcmd` cmdlet to query a SQL server for all its databases.</span></span> <span data-ttu-id="8dd42-202">此函数使用前面示例中使用的相同属性定义凭据参数。</span><span class="sxs-lookup"><span data-stu-id="8dd42-202">The function defines a **Credential** parameter with the same attribute used in the previous examples.</span></span> <span data-ttu-id="8dd42-203">由于 `$Credential` 变量中存在用户名和密码，因此可以提取这些值以用于 `Invoke-Sqlcmd`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-203">Since the username and password exist within the `$Credential` variable, you can extract those values for use with `Invoke-Sqlcmd`.</span></span>

<span data-ttu-id="8dd42-204">用户名可从 `$Credential` 变量的“用户名”属性中获取。</span><span class="sxs-lookup"><span data-stu-id="8dd42-204">The user name is available from the **UserName** property of the `$Credential` variable.</span></span> <span data-ttu-id="8dd42-205">若要获取密码，必须使用 `$Credential` 对象的 `GetNetworkCredential()` 方法。</span><span class="sxs-lookup"><span data-stu-id="8dd42-205">To obtain the password, you have to use the `GetNetworkCredential()` method of the `$Credential` object.</span></span> <span data-ttu-id="8dd42-206">这些值将被提取到变量中，这些变量将添加到哈希表中以用于将参数展开到 `Invoke-Sqlcmd`。</span><span class="sxs-lookup"><span data-stu-id="8dd42-206">The values are extracted into variables that are added to a hash table used for splatting parameters to `Invoke-Sqlcmd`.</span></span>

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a><span data-ttu-id="8dd42-207">继续学习凭据管理</span><span class="sxs-lookup"><span data-stu-id="8dd42-207">Continued learning credential management</span></span>

<span data-ttu-id="8dd42-208">以安全的方式创建和存储凭据对象，这个过程可能会非常困难。</span><span class="sxs-lookup"><span data-stu-id="8dd42-208">Creating and storing credential objects securely can be difficult.</span></span> <span data-ttu-id="8dd42-209">以下资源可帮助你维护 PowerShell 凭据。</span><span class="sxs-lookup"><span data-stu-id="8dd42-209">The following resources can help you maintain PowerShell credentials.</span></span>

- <span data-ttu-id="8dd42-210">[BetterCredentials][]</span><span class="sxs-lookup"><span data-stu-id="8dd42-210">[BetterCredentials][]</span></span>
- <span data-ttu-id="8dd42-211">[Azure Key Vault][]</span><span class="sxs-lookup"><span data-stu-id="8dd42-211">[Azure Key Vault][]</span></span>
- <span data-ttu-id="8dd42-212">[保管库项目][]</span><span class="sxs-lookup"><span data-stu-id="8dd42-212">[Vault Project][]</span></span>
- <span data-ttu-id="8dd42-213">[SecretManagement 模块][]</span><span class="sxs-lookup"><span data-stu-id="8dd42-213">[SecretManagement module][]</span></span>

<!-- link references -->
[原始版本]: https://duffney.io/addcredentialstopowershellfunctions/
[original version]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[保管库项目]: https://www.vaultproject.io/
[Vault Project]: https://www.vaultproject.io/
[展开高级函数内的参数]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Splatting Parameters Inside Advanced Functions]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[使用 Windows 上的 Jenkins 和 PowerShell 实现自动化 - 第 2 部分]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[Automating with Jenkins and PowerShell on Windows - Part 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[SecretManagement 模块]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
[SecretManagement module]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
