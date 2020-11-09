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
# <a name="add-credential-support-to-powershell-functions"></a>向 PowerShell 函数添加凭据支持

> [!NOTE]
> 本文的[原始版本][]发布在 [@joshduffney][] 撰写的博客上。 此文已经过编辑，以便发布在本站点中。 PowerShell 团队感谢 Josh 与我们分享这篇文章。 若要访问他的博客，请访问 [duffney.io][]。

本文介绍了如何向 PowerShell 函数添加凭据以及这样做的理由。 凭据参数用于允许你以其他用户的身份运行函数或 cmdlet。 最常见的用途是以提升的用户帐户身份运行函数或 cmdlet。

例如，cmdlet `New-ADUser` 包含“凭据”参数，你可以在此参数中提供域管理员凭据，以便在域中创建帐户。 假设你用于运行 PowerShell 会话的常规帐户尚没有上述访问权限。

## <a name="creating-credential-object"></a>创建凭据对象

[PSCredential][] 对象表示一组安全凭据，例如用户名和密码。 此对象可以作为参数传递给函数，以便该函数以此凭据对象中的用户帐户身份运行。 可使用下面的几种方法创建凭据对象。 创建凭据对象的第一种方法是使用 PowerShell cmdlet `Get-Credential`。 在未使用参数的情况下运行它时，系统会提示你输入用户名和密码。 你也可以使用一些可选参数来调用此 cmdlet。

若要预先指定域名和用户名，可以使用“凭据”或“用户名”参数。 使用“用户名”参数时，你还需要提供“邮件”值。 以下代码演示了如何使用此 cmdlet。 也可以将凭据对象存储在变量中，以便可以多次使用该凭据。 下面的示例将凭据对象存储到了变量 `$Cred` 中。

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

有时，无法使用上面示例所示的交互式方法创建凭据对象。 大多数自动化工具都需要使用非交互式方法。 若要在无用户交互的情况下创建凭据，请创建一个包含密码的安全字符串。 然后，将安全字符串和用户名传递到 `System.Management.Automation.PSCredential()` 方法。

请使用下面的命令创建一个包含密码的安全字符串：

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

需要提供“AsPlainText”和“强制”参数。 如果没有提供这些参数，你将收到一条警告消息，其中会提示你不得将纯文本传递到安全字符串中。 由于纯文本密码会记录在各种日志中，因此 PowerShell 会返回此警告。 创建安全字符串后，需要将其传递到 `PSCredential()` 方法，以创建凭据对象。 在下面的示例中，变量 `$password` 包含安全字符串，`$Cred` 包含凭据对象。

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

现在你已了解如何创建凭据对象，接下来就可以向 PowerShell 函数添加凭据参数。

## <a name="adding-a-credential-parameter"></a>添加凭据参数

就像添加任何其他参数一样，首先要将其添加到函数的 `param` 块中。
建议将此参数命名为 `$Credential`，因为现有的 PowerShell cmdlet 都使用此名称。 此参数的类型应为 `[System.Management.Automation.PSCredential]`。

下面的示例显示了名为 `Get-Something` 的函数的参数块。 该参数块包含两个参数：`$Name` 和 `$Credential`。

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

此示例中的代码足以生成一个可用的凭据参数，不过你还可以添加一些内容来使其更加可靠。

- 添加 `[ValidateNotNull()]` 验证属性，用于检查要传递给凭据的值。 如果参数值为 null，此属性将阻止函数使用无效的凭据执行。

- 添加 `[System.Management.Automation.Credential()]`。 它将允许你以字符串形式传入用户名，并可提供交互式密码提示。

- 将 `$Credential` 参数的默认值设置为 `[System.Management.Automation.PSCredential]::Empty`。 你的函数可能会将此 `$Credential` 对象传递到现有的 PowerShell cmdlet。 向函数调用的 cmdlet 提供 null 值，这会引发错误。 提供空凭据对象可以避免此错误。

> [!TIP]
> 某些接受凭据参数的 cmdlet 不能按照预期方式支持 `[System.Management.Automation.PSCredential]::Empty`。 有关解决方法的信息，请参阅[处理旧版 Cmdlet](#dealing-with-legacy-cmdlets) 部分。

## <a name="using-credential-parameters"></a>使用凭据参数

下面的示例演示了凭据参数的用法。 此示例显示了一个名为 `Set-RemoteRegistryValue` 的函数，该函数出自 [The Pester Book][]。 此函数使用前面部分所述的技巧定义了凭据参数。 此函数使用其创建的 `$Credential` 变量调用 `Invoke-Command`。 这样即可以更改运行 `Invoke-Command` 的用户。 由于 `$Credential` 的默认值为空凭据，因此可以在不提供凭据的情况下运行该函数。

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

以下各个部分介绍了向 `Set-RemoteRegistryValue` 提供凭据的不同方法。

### <a name="prompting-for-credentials"></a>提示输入凭据

运行时在括号 `()` 中使用 `Get-Credential`，这样将优先运行 `Get-credential`。 系统提示输入用户名和密码。 可以使用 `Get-credential` 的“凭据”或“用户名”参数来预填充用户名和域。 下面的示例使用展开技术将参数传递给 `Set-RemoteRegistryValue` 函数。 有关展开技术的详细信息，请参阅 [about_Splatting][] 一文。

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

使用 `(Get-Credential)` 似乎很繁琐。 通常，如果仅将凭据参数与一个用户名一起使用时，该 cmdlet 会自动提示输入密码。 `[System.Management.Automation.Credential()]` 属性将实现此行为。

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
> 这些示例假定你已安装 Windows 的 Web 服务器功能，以便可以设置所显示的注册表值。 如果需要，可运行 `Install-WindowsFeature Web-Server` 和 `Install-WindowsFeature web-mgmt-tools`。

### <a name="provide-credentials-in-a-variable"></a>以变量形式提供凭据

也可以预先填充凭据变量，并将其传递给 `Set-RemoteRegistryValue` 函数的凭据参数。 可将此方法与持续集成/持续部署 (CI/CD) 工具（例如 Jenkins、TeamCity 和 Octopus Deploy）一起使用。 可参阅 Hodge 的博客文章[使用 Windows 上的 Jenkins 和 PowerShell 实现自动化 - 第 2 部分][]来查看使用 Jenkins 的示例。

此示例使用 .NET 方法创建凭据对象和安全字符串来传入密码。

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

在此示例中，安全字符串由明文密码创建而成。 前面提到的所有 CI/CD 都可在运行时通过安全的方式提供该密码。 使用这些工具时，请将纯文本密码替换为使用的 CI/CD 工具中定义的变量。

### <a name="run-without-credentials"></a>在不提供凭据的情况下运行

由于 `$Credential` 的默认值为空凭据对象，因此可以在不提供凭据的情况下运行此命令，如以下示例中所示：

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a>使用旧版 cmdlet

并非所有 cmdlet 都支持凭据对象或都允许空凭据。 cmdlet 可能希望用户名和密码参数是字符串形式。 可通过以下几种方法解决这种局限性。

### <a name="using-if-else-to-handle-empty-credentials"></a>使用 if-else 处理空凭据

在这种情况下，你想要运行的 cmdlet 不接受空凭据对象。 此示例仅在凭据参数不为空时将其添加到 `Invoke-Command`。 否则，它将运行不含凭据参数的 `Invoke-Command`。

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

### <a name="using-splatting-to-handle-empty-credentials"></a>使用展开技术处理空凭据

此示例使用参数展开技术调用旧版 cmdlet。 `$Credential` 对象会根据条件添加到哈希表进行展开，因此无需再重复执行 `Invoke-Command` 脚本块。 若要详细了解函数内的展开技术，请参阅博客文章[展开高级函数内的参数][]。

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

### <a name="working-with-string-passwords"></a>使用字符串密码

`Invoke-Sqlcmd` cmdlet 是一种接受字符串密码的 cmdlet。
`Invoke-Sqlcmd` 可允许你运行简单的 SQL 插入、更新和删除语句。 `Invoke-Sqlcmd` 需要使用明文用户名和密码，而不使用更加安全的凭据对象。 此示例演示如何从凭据对象中提取用户名和密码。

本示例中的 `Get-AllSQLDatabases` 函数将调用 `Invoke-Sqlcmd` cmdlet 来查询 SQL Server 中的所有数据库。 此函数使用前面示例中使用的相同属性定义凭据参数。 由于 `$Credential` 变量中存在用户名和密码，因此可以提取这些值以用于 `Invoke-Sqlcmd`。

用户名可从 `$Credential` 变量的“用户名”属性中获取。 若要获取密码，必须使用 `$Credential` 对象的 `GetNetworkCredential()` 方法。 这些值将被提取到变量中，这些变量将添加到哈希表中以用于将参数展开到 `Invoke-Sqlcmd`。

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

## <a name="continued-learning-credential-management"></a>继续学习凭据管理

以安全的方式创建和存储凭据对象，这个过程可能会非常困难。 以下资源可帮助你维护 PowerShell 凭据。

- [BetterCredentials][]
- [Azure Key Vault][]
- [保管库项目][]
- [SecretManagement 模块][]

<!-- link references -->
[原始版本]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[保管库项目]: https://www.vaultproject.io/
[展开高级函数内的参数]: https://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[使用 Windows 上的 Jenkins 和 PowerShell 实现自动化 - 第 2 部分]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[SecretManagement 模块]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
