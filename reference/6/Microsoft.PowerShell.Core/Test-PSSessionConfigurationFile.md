---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: a5017b7a46e36a8a2c67ad05d3b6606056ded0f1
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343963"
---
# <span data-ttu-id="21dc0-103">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="21dc0-103">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="21dc0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="21dc0-104">SYNOPSIS</span></span>
<span data-ttu-id="21dc0-105">验证会话配置文件中的键和值。</span><span class="sxs-lookup"><span data-stu-id="21dc0-105">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="21dc0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21dc0-106">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="21dc0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21dc0-107">DESCRIPTION</span></span>

<span data-ttu-id="21dc0-108">此 cmdlet 验证会话配置文件是否包含有效的密钥，以及这些值是否为正确的类型。</span><span class="sxs-lookup"><span data-stu-id="21dc0-108">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="21dc0-109">对于枚举值，该 cmdlet 将验证指定的值是否有效。</span><span class="sxs-lookup"><span data-stu-id="21dc0-109">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="21dc0-110">`$True`如果文件通过了所有测试，则该 cmdlet 将返回， `$False` 否则返回。</span><span class="sxs-lookup"><span data-stu-id="21dc0-110">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="21dc0-111">若要查找任何错误，请使用 **Verbose** 参数。</span><span class="sxs-lookup"><span data-stu-id="21dc0-111">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="21dc0-112">`Test-PSSessionConfigurationFile` 验证会话配置文件，如由 cmdlet 创建的文件 `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="21dc0-112">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="21dc0-113">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="21dc0-113">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="21dc0-114">有关会话配置文件的信息，请参阅 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)。</span><span class="sxs-lookup"><span data-stu-id="21dc0-114">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="21dc0-115">此 cmdlet 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="21dc0-115">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="21dc0-116">示例</span><span class="sxs-lookup"><span data-stu-id="21dc0-116">EXAMPLES</span></span>

### <span data-ttu-id="21dc0-117">示例1：测试会话配置文件</span><span class="sxs-lookup"><span data-stu-id="21dc0-117">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="21dc0-118">示例2：测试会话配置的会话配置文件</span><span class="sxs-lookup"><span data-stu-id="21dc0-118">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="21dc0-119">在此示例中，我们将测试 **受限** 会话配置中使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="21dc0-119">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="21dc0-120">**Path** 参数的值是 `Get-PSSessionConfiguration` 用于获取 **受限** 会话配置的命令的结果。</span><span class="sxs-lookup"><span data-stu-id="21dc0-120">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="21dc0-121">会话配置文件的路径存储在会话配置的 **ConfigFilePath** 属性的值中。</span><span class="sxs-lookup"><span data-stu-id="21dc0-121">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="21dc0-122">示例3：测试所有会话配置文件</span><span class="sxs-lookup"><span data-stu-id="21dc0-122">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="21dc0-123">此示例中的函数测试本地计算机上的所有会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="21dc0-123">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="21dc0-124">函数使用 `Get-PSSessionConfiguration` cmdlet 获取所有会话配置。</span><span class="sxs-lookup"><span data-stu-id="21dc0-124">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="21dc0-125">循环内的代码 `ForEach-Object` 显示文件路径并测试每个会话配置。</span><span class="sxs-lookup"><span data-stu-id="21dc0-125">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

<span data-ttu-id="21dc0-126">会话配置的 **ConfigFilePath** 属性包含在会话配置中使用的会话配置文件的路径（如果有）。</span><span class="sxs-lookup"><span data-stu-id="21dc0-126">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="21dc0-127">如果填充了 **ConfigFilePath** 属性的值（该值为 true），则该命令将获取（打印） **ConfigFilePath** 属性值。</span><span class="sxs-lookup"><span data-stu-id="21dc0-127">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="21dc0-128">然后，它使用 `Test-PSSessionConfigurationFile` cmdlet 来测试 **ConfigFilePath** 值中的文件。</span><span class="sxs-lookup"><span data-stu-id="21dc0-128">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="21dc0-129">当文件无法通过测试时， **Verbose** 参数将返回文件错误。</span><span class="sxs-lookup"><span data-stu-id="21dc0-129">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="21dc0-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21dc0-130">PARAMETERS</span></span>

### <span data-ttu-id="21dc0-131">-Path</span><span class="sxs-lookup"><span data-stu-id="21dc0-131">-Path</span></span>

<span data-ttu-id="21dc0-132">指定会话配置文件的路径和文件名 ( .pssc) 。</span><span class="sxs-lookup"><span data-stu-id="21dc0-132">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="21dc0-133">如果省略该路径，则默认为当前文件夹。</span><span class="sxs-lookup"><span data-stu-id="21dc0-133">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="21dc0-134">支持通配符，但它们必须解析为单个文件。</span><span class="sxs-lookup"><span data-stu-id="21dc0-134">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="21dc0-135">还可以通过管道将会话配置文件路径传递给 `Test-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="21dc0-135">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="21dc0-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="21dc0-136">CommonParameters</span></span>

<span data-ttu-id="21dc0-137">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="21dc0-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21dc0-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="21dc0-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21dc0-139">输入</span><span class="sxs-lookup"><span data-stu-id="21dc0-139">INPUTS</span></span>

### <span data-ttu-id="21dc0-140">System.String</span><span class="sxs-lookup"><span data-stu-id="21dc0-140">System.String</span></span>

<span data-ttu-id="21dc0-141">你可以通过管道将会话配置文件路径传递给 `Test-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="21dc0-141">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="21dc0-142">输出</span><span class="sxs-lookup"><span data-stu-id="21dc0-142">OUTPUTS</span></span>

### <span data-ttu-id="21dc0-143">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="21dc0-143">System.Boolean</span></span>

## <span data-ttu-id="21dc0-144">注释</span><span class="sxs-lookup"><span data-stu-id="21dc0-144">NOTES</span></span>

<span data-ttu-id="21dc0-145">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="21dc0-145">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="21dc0-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="21dc0-146">RELATED LINKS</span></span>

[<span data-ttu-id="21dc0-147">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21dc0-147">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="21dc0-148">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21dc0-148">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="21dc0-149">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21dc0-149">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="21dc0-150">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="21dc0-150">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="21dc0-151">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="21dc0-151">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="21dc0-152">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21dc0-152">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="21dc0-153">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21dc0-153">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="21dc0-154">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="21dc0-154">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="21dc0-155">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="21dc0-155">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="21dc0-156">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="21dc0-156">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="21dc0-157">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="21dc0-157">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="21dc0-158">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="21dc0-158">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
