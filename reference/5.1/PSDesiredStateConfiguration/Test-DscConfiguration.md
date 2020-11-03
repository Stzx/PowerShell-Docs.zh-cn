---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197824"
---
# <span data-ttu-id="66074-103">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="66074-103">Test-DscConfiguration</span></span>

## <span data-ttu-id="66074-104">摘要</span><span class="sxs-lookup"><span data-stu-id="66074-104">SYNOPSIS</span></span>
<span data-ttu-id="66074-105">测试节点上的实际配置是否与所需配置相匹配。</span><span class="sxs-lookup"><span data-stu-id="66074-105">Tests whether the actual configuration on the nodes matches the desired configuration.</span></span>

## <span data-ttu-id="66074-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66074-106">SYNTAX</span></span>

### <span data-ttu-id="66074-107">ComputerNameSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="66074-107">ComputerNameSet (Default)</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### <span data-ttu-id="66074-108">ComputerNameAndPathSet</span><span class="sxs-lookup"><span data-stu-id="66074-108">ComputerNameAndPathSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="66074-109">ComputerNameAndReferenceConfigurationSet</span><span class="sxs-lookup"><span data-stu-id="66074-109">ComputerNameAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="66074-110">CimSessionAndPathSet</span><span class="sxs-lookup"><span data-stu-id="66074-110">CimSessionAndPathSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="66074-111">CimSessionAndReferenceConfigurationSet</span><span class="sxs-lookup"><span data-stu-id="66074-111">CimSessionAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="66074-112">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="66074-112">CimSessionSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## <span data-ttu-id="66074-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66074-113">DESCRIPTION</span></span>
<span data-ttu-id="66074-114">**Test-DscConfiguration** cmdlet 测试节点上的实际配置是否与所需配置相匹配。</span><span class="sxs-lookup"><span data-stu-id="66074-114">The **Test-DscConfiguration** cmdlet tests whether the actual configuration on the nodes matches the desired configuration.</span></span>
<span data-ttu-id="66074-115">通过使用计算机名称或通用信息模型 (CIM) 会话，指定想要测试配置的计算机。</span><span class="sxs-lookup"><span data-stu-id="66074-115">Specify which computers for which you want to test configurations by using computer names or Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="66074-116">如果不指定目标计算机，则该 cmdlet 将测试本地计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="66074-116">If you do not specify a target computer, the cmdlet tests configuration of the local computer.</span></span>

<span data-ttu-id="66074-117">如果所需配置和实际配置匹配，则该 cmdlet 将返回字符串值 "True"。</span><span class="sxs-lookup"><span data-stu-id="66074-117">If the desired and actual configurations match, the cmdlet returns a string value of 'True'.</span></span>
<span data-ttu-id="66074-118">否则，它将返回字符串值 "False"。</span><span class="sxs-lookup"><span data-stu-id="66074-118">Otherwise, it returns a string value of 'False'.</span></span>

## <span data-ttu-id="66074-119">示例</span><span class="sxs-lookup"><span data-stu-id="66074-119">EXAMPLES</span></span>

### <span data-ttu-id="66074-120">示例 1：测试本地计算机的配置</span><span class="sxs-lookup"><span data-stu-id="66074-120">Example 1: Test configuration for the local computer</span></span>

```
PS C:\> Test-DscConfiguration
```

<span data-ttu-id="66074-121">此命令将测试本地计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="66074-121">This command tests configuration for the local computer.</span></span>

### <span data-ttu-id="66074-122">示例 2：测试指定计算机的配置</span><span class="sxs-lookup"><span data-stu-id="66074-122">Example 2: Test configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

<span data-ttu-id="66074-123">此示例将测试由 CIM 会话指定的计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="66074-123">This example test configuration from a computer specified by a CIM session.</span></span>
<span data-ttu-id="66074-124">该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="66074-124">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="66074-125">或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="66074-125">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="66074-126">第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。</span><span class="sxs-lookup"><span data-stu-id="66074-126">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="66074-127">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="66074-127">The command prompts you for a password.</span></span>
<span data-ttu-id="66074-128">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="66074-128">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="66074-129">第二个命令测试由存储在 $Session 变量中的 **CimSession** 对象标识的计算机（在此示例中，是名为 Server01 的计算机）的配置。</span><span class="sxs-lookup"><span data-stu-id="66074-129">The second command tests configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

### <span data-ttu-id="66074-130">示例 3：带有详细结果的配置测试</span><span class="sxs-lookup"><span data-stu-id="66074-130">Example 3: Test configurations with detailed results</span></span>

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

<span data-ttu-id="66074-131">此命令测试由 ComputerName  参数指定的一组计算机的配置，并返回详细信息（包括总体状态、处于所需状态的资源、未处于所需状态的资源以及计算机名称）。</span><span class="sxs-lookup"><span data-stu-id="66074-131">This command tests configurations for a set of computers specified by the *ComputerName* parameter and returns detailed information that includes the overall state, resources that are in the desired state, resources that are not in the desired state and computer name.</span></span>

### <span data-ttu-id="66074-132">示例 4：测试文件夹中指定的配置</span><span class="sxs-lookup"><span data-stu-id="66074-132">Example 4: Test configurations specified in a folder</span></span>

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

<span data-ttu-id="66074-133">此命令测试在 Path  参数指定的文件夹中定义的配置。</span><span class="sxs-lookup"><span data-stu-id="66074-133">This command tests configurations that are defined in a folder specified by the *Path* parameter.</span></span>
<span data-ttu-id="66074-134">针对一组计算机测试配置，每台计算机以配置文件的文件名标识。</span><span class="sxs-lookup"><span data-stu-id="66074-134">The configurations are tested against a set of computers, each identified by the file name of the configuration file.</span></span>

### <span data-ttu-id="66074-135">示例 5：测试文件中指定的配置</span><span class="sxs-lookup"><span data-stu-id="66074-135">Example 5: Test configurations specified in a file</span></span>

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

<span data-ttu-id="66074-136">针对 ComputerName  参数指定的一组计算机，此命令测试文件中定义的配置。</span><span class="sxs-lookup"><span data-stu-id="66074-136">This command tests a configuration defined in a file against a set of computers specified by the *ComputerName* parameter.</span></span>

## <span data-ttu-id="66074-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66074-137">PARAMETERS</span></span>

### <span data-ttu-id="66074-138">-AsJob</span><span class="sxs-lookup"><span data-stu-id="66074-138">-AsJob</span></span>
<span data-ttu-id="66074-139">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="66074-139">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="66074-140">如果指定 AsJob  参数，该命令将返回表示作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="66074-140">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="66074-141">作业完成前，可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="66074-141">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="66074-142">作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。</span><span class="sxs-lookup"><span data-stu-id="66074-142">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="66074-143">若要管理作业，请使用 Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66074-143">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="66074-144">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66074-144">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="66074-145">若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 以及更高版本的 Windows 操作系统上，还必须使用“以管理员身份运行”选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="66074-145">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="66074-146">有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66074-146">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="66074-147">有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="66074-147">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="66074-148">-CimSession</span><span class="sxs-lookup"><span data-stu-id="66074-148">-CimSession</span></span>
<span data-ttu-id="66074-149">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66074-149">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="66074-150">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="66074-150">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="66074-151">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="66074-151">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66074-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="66074-152">-ComputerName</span></span>
<span data-ttu-id="66074-153">指定此 cmdlet 要测试配置的一批计算机名称。</span><span class="sxs-lookup"><span data-stu-id="66074-153">Specifies an array of computer names on which this cmdlet tests the configuration.</span></span>
<span data-ttu-id="66074-154">该 cmdlet 测试由这些计算机的 Path  参数指定的位置中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="66074-154">The cmdlet tests the configuration document in the location specified by the *Path* parameter to these computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66074-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="66074-155">-Credential</span></span>
<span data-ttu-id="66074-156">针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="66074-156">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="66074-157">若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66074-157">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="66074-158">要了解详情，请键入 `Get-Help Get-Credential`。</span><span class="sxs-lookup"><span data-stu-id="66074-158">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66074-159">-Detailed</span><span class="sxs-lookup"><span data-stu-id="66074-159">-Detailed</span></span>
<span data-ttu-id="66074-160">指示此 cmdlet 返回与节点所需状态进行比较的配置文档的详细结果。</span><span class="sxs-lookup"><span data-stu-id="66074-160">Indicates that this cmdlet returns a detailed result of comparing the configuration document with the desired state of the nodes.</span></span>
<span data-ttu-id="66074-161">结果中包括总体状态、处于所需状态的资源、未处于所需状态的资源以及计算机名称等信息。</span><span class="sxs-lookup"><span data-stu-id="66074-161">The result includes information such as overall state, resources that are in the desired state, resources that are not in desired state, and computer name.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66074-162">-Path</span><span class="sxs-lookup"><span data-stu-id="66074-162">-Path</span></span>
<span data-ttu-id="66074-163">指定包含配置文档文件的文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="66074-163">Specifies the path of a folder that contains configuration document files.</span></span>
<span data-ttu-id="66074-164">针对由 ComputerName  或 CimSession  参数指定的计算机所需状态，该 cmdlet 测试配置。</span><span class="sxs-lookup"><span data-stu-id="66074-164">The cmdlet tests the configuration against the desired state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66074-165">-ReferenceConfiguration</span><span class="sxs-lookup"><span data-stu-id="66074-165">-ReferenceConfiguration</span></span>
<span data-ttu-id="66074-166">指定配置文档文件的路径。</span><span class="sxs-lookup"><span data-stu-id="66074-166">Specifies the path of the configuration document file.</span></span>
<span data-ttu-id="66074-167">针对由 ComputerName  或 CimSession  参数指定的计算机实际状态，该 cmdlet 测试配置。</span><span class="sxs-lookup"><span data-stu-id="66074-167">This cmdlet tests the configuration against the actual state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66074-168">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="66074-168">-ThrottleLimit</span></span>
<span data-ttu-id="66074-169">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="66074-169">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="66074-170">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="66074-170">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="66074-171">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="66074-171">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66074-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66074-172">CommonParameters</span></span>
<span data-ttu-id="66074-173">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="66074-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66074-174">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="66074-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66074-175">输入</span><span class="sxs-lookup"><span data-stu-id="66074-175">INPUTS</span></span>

## <span data-ttu-id="66074-176">输出</span><span class="sxs-lookup"><span data-stu-id="66074-176">OUTPUTS</span></span>

## <span data-ttu-id="66074-177">注释</span><span class="sxs-lookup"><span data-stu-id="66074-177">NOTES</span></span>

## <span data-ttu-id="66074-178">相关链接</span><span class="sxs-lookup"><span data-stu-id="66074-178">RELATED LINKS</span></span>

[<span data-ttu-id="66074-179">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="66074-179">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="66074-180">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="66074-180">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="66074-181">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="66074-181">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="66074-182">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="66074-182">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="66074-183">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="66074-183">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)
