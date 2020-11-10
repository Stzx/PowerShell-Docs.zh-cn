---
description: 简要介绍了 PowerShell 所需状态配置 (DSC) 功能。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 5d088934ffc953ad19be401bce72f6287f0fde07
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387016"
---
# <a name="about_desiredstateconfiguration"></a><span data-ttu-id="d5656-104">about_DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5656-104">about_DesiredStateConfiguration</span></span>

## <a name="short-description"></a><span data-ttu-id="d5656-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="d5656-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="d5656-106">简要介绍了 PowerShell 所需状态配置 (DSC) 功能。</span><span class="sxs-lookup"><span data-stu-id="d5656-106">Provides a brief introduction to the PowerShell Desired State Configuration (DSC) feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="d5656-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="d5656-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d5656-108">DSC 是 PowerShell 中的一个管理平台，可用于部署和管理软件服务的配置数据，并管理这些服务的运行环境。</span><span class="sxs-lookup"><span data-stu-id="d5656-108">DSC is a management platform in PowerShell that enables deploying and managing configuration data for software services, and managing the environment in which these services run.</span></span>

<span data-ttu-id="d5656-109">DSC 提供了一组 PowerShell 语言扩展、新的 cmdlet 和资源，你可以使用它以声明方式指定你希望配置软件环境状态的方式。</span><span class="sxs-lookup"><span data-stu-id="d5656-109">DSC provides a set of PowerShell language extensions, new cmdlets, and resources that you can use to declaratively specify how you want the state of your software environment to be configured.</span></span> <span data-ttu-id="d5656-110">它还提供了维护和管理现有配置的方法。</span><span class="sxs-lookup"><span data-stu-id="d5656-110">It also provides a means to maintain and manage existing configurations.</span></span>

<span data-ttu-id="d5656-111">PowerShell 4.0 中引入了 DSC。</span><span class="sxs-lookup"><span data-stu-id="d5656-111">DSC is introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="d5656-112">有关 DSC 的详细信息，请参阅 [PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/overview)。</span><span class="sxs-lookup"><span data-stu-id="d5656-112">For detailed information about DSC, see [PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview).</span></span>

## <a name="developing-dsc-resources-with-classes"></a><span data-ttu-id="d5656-113">用类开发 DSC 资源</span><span class="sxs-lookup"><span data-stu-id="d5656-113">DEVELOPING DSC RESOURCES WITH CLASSES</span></span>

<span data-ttu-id="d5656-114">从 PowerShell 5.0 开始，可以使用类开发 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="d5656-114">Starting in PowerShell 5.0, you can develop DSC resources by using classes.</span></span>
<span data-ttu-id="d5656-115">有关详细信息，请参阅 [about_Classes](about_Classes.md)和 [使用 PowerShell 类编写自定义 DSC 资源](/powershell/scripting/dsc/resources/authoringresourceclass)。</span><span class="sxs-lookup"><span data-stu-id="d5656-115">For more information, see [about_Classes](about_Classes.md), and [Writing a custom DSC resource with PowerShell classes](/powershell/scripting/dsc/resources/authoringresourceclass).</span></span>

## <a name="using-dsc"></a><span data-ttu-id="d5656-116">使用 DSC</span><span class="sxs-lookup"><span data-stu-id="d5656-116">USING DSC</span></span>

<span data-ttu-id="d5656-117">要使用 DSC 配置你的环境，请先使用配置关键字来定义一个 PowerShell 脚本块，后跟一个标识符，该标识符后面跟着分隔块的大括号对。</span><span class="sxs-lookup"><span data-stu-id="d5656-117">To use DSC to configure your environment, first define a PowerShell script block using the Configuration keyword, followed by an identifier, which is in turn followed by the pair of curly braces delimiting the block.</span></span> <span data-ttu-id="d5656-118">在配置块中，你可以定义节点块，以便为环境中 (计算机) 的每个节点指定所需的配置状态。</span><span class="sxs-lookup"><span data-stu-id="d5656-118">Inside the configuration block you can define node blocks that specify the desired configuration state for each node (computer) in the environment.</span></span> <span data-ttu-id="d5656-119">节点块以 Node 关键字开头，后跟目标计算机的名称，可以是变量。</span><span class="sxs-lookup"><span data-stu-id="d5656-119">A node block starts with the Node keyword, followed by the name of the target computer, which can be a variable.</span></span> <span data-ttu-id="d5656-120">在计算机名称后，出现用于分隔节点块的大括号。</span><span class="sxs-lookup"><span data-stu-id="d5656-120">After the computer name, come the curly braces that delimit the node block.</span></span> <span data-ttu-id="d5656-121">在节点块内，可以定义用于配置特定资源的资源块。</span><span class="sxs-lookup"><span data-stu-id="d5656-121">Inside the node block, you can define resource blocks to configure specific resources.</span></span> <span data-ttu-id="d5656-122">资源块以资源的类型名称开头，后跟要为该块指定的标识符，后跟分隔块的大括号，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="d5656-122">A resource block starts with the type name of the resource, followed by the identifier you want to specify for that block, followed by the curly braces that delimit the block, as shown in the following example.</span></span>

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

<span data-ttu-id="d5656-123">若要创建配置，请使用与调用 PowerShell 函数相同的方式来调用配置块，并传入您在上面的示例中定义的任何所需参数 (两个) 。</span><span class="sxs-lookup"><span data-stu-id="d5656-123">To create a configuration, invoke the Configuration block the same way you would invoke a PowerShell function, passing in any expected parameters you may have defined (two in the example above).</span></span> <span data-ttu-id="d5656-124">例如，在这种情况下：</span><span class="sxs-lookup"><span data-stu-id="d5656-124">For example, in this case:</span></span>

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

<span data-ttu-id="d5656-125">这会在你指定的路径下为每个节点生成一个 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="d5656-125">This generates a MOF file per node at the path you specify.</span></span> <span data-ttu-id="d5656-126">这些 MOF 文件指定每个节点所需的配置。</span><span class="sxs-lookup"><span data-stu-id="d5656-126">These MOF files specify the desired configuration for each node.</span></span> <span data-ttu-id="d5656-127">接下来，使用以下 cmdlet 分析配置 MOF 文件，发送每个节点的相应配置，并制定这些配置。</span><span class="sxs-lookup"><span data-stu-id="d5656-127">Next, use the following cmdlet to parse the configuration MOF files, send each node its corresponding configuration, and enact those configurations.</span></span> <span data-ttu-id="d5656-128">请注意，不需要为基于类的 DSC 资源创建单独的 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="d5656-128">Note that you do not need to create a separate MOF file for class-based DSC resources.</span></span>

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a><span data-ttu-id="d5656-129">使用 DSC 维护配置状态</span><span class="sxs-lookup"><span data-stu-id="d5656-129">USING DSC TO MAINTAIN CONFIGURATION STATE</span></span>

<span data-ttu-id="d5656-130">对于 DSC，配置是幂等的。</span><span class="sxs-lookup"><span data-stu-id="d5656-130">With DSC, configuration is idempotent.</span></span> <span data-ttu-id="d5656-131">这意味着，如果你使用 DSC 来多次执行相同的配置，则生成的配置状态将始终相同。</span><span class="sxs-lookup"><span data-stu-id="d5656-131">This means that if you use DSC to enact the same configuration more than once, the resulting configuration state will always be the same.</span></span> <span data-ttu-id="d5656-132">因此，如果您怀疑您的环境中的任何节点可能会从所需的配置状态偏移，则可以再次执行相同的 DSC 配置，使其返回到所需状态。</span><span class="sxs-lookup"><span data-stu-id="d5656-132">Because of this, if you suspect that any nodes in your environment may have drifted from the desired state of configuration, you can enact the same DSC configuration again to bring them back to the desired state.</span></span> <span data-ttu-id="d5656-133">不需要修改配置脚本来仅对状态与所需状态为 "偏移" 的资源进行寻址。</span><span class="sxs-lookup"><span data-stu-id="d5656-133">You do not need to modify the configuration script to address only those resources whose state has drifted from the desired state.</span></span>

<span data-ttu-id="d5656-134">下面的示例演示了如何验证给定节点上的实际配置状态是否与该节点上代理的上一个 DSC 配置偏移。</span><span class="sxs-lookup"><span data-stu-id="d5656-134">The following example shows how you can verify whether the actual state of configuration on a given node has drifted from the last DSC configuration enacted on the node.</span></span> <span data-ttu-id="d5656-135">在此示例中，我们将检查本地计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="d5656-135">In this example we are checking the configuration of the local computer.</span></span>

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a><span data-ttu-id="d5656-136">内置 DSC 资源</span><span class="sxs-lookup"><span data-stu-id="d5656-136">BUILT-IN DSC RESOURCES</span></span>

<span data-ttu-id="d5656-137">你可以在配置脚本中使用下列内置资源：</span><span class="sxs-lookup"><span data-stu-id="d5656-137">You can use the following built-in resources in your configuration scripts:</span></span>

|<span data-ttu-id="d5656-138">名称</span><span class="sxs-lookup"><span data-stu-id="d5656-138">Name</span></span>                  |<span data-ttu-id="d5656-139">属性</span><span class="sxs-lookup"><span data-stu-id="d5656-139">Properties</span></span>                                         |
|----------------------|---------------------------------------------------|
|<span data-ttu-id="d5656-140">文件</span><span class="sxs-lookup"><span data-stu-id="d5656-140">File</span></span>                  |<span data-ttu-id="d5656-141">{DestinationPath，属性，Checksum，Content ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-141">{DestinationPath, Attributes, Checksum, Content...}</span></span>|
|<span data-ttu-id="d5656-142">存档</span><span class="sxs-lookup"><span data-stu-id="d5656-142">Archive</span></span>               |<span data-ttu-id="d5656-143">{Destination，路径，校验和，Credential ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-143">{Destination, Path, Checksum, Credential...}</span></span>       |
|<span data-ttu-id="d5656-144">环境</span><span class="sxs-lookup"><span data-stu-id="d5656-144">Environment</span></span>           |<span data-ttu-id="d5656-145">{Name，DependsOn，请确保，Path ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-145">{Name, DependsOn, Ensure, Path...}</span></span>                 |
|<span data-ttu-id="d5656-146">组</span><span class="sxs-lookup"><span data-stu-id="d5656-146">Group</span></span>                 |<span data-ttu-id="d5656-147">{DependsOn，Credential，，"Description ...}"</span><span class="sxs-lookup"><span data-stu-id="d5656-147">{GroupName, Credential, DependsOn, Description...}</span></span> |
|<span data-ttu-id="d5656-148">日志</span><span class="sxs-lookup"><span data-stu-id="d5656-148">Log</span></span>                   |<span data-ttu-id="d5656-149">{Message，DependsOn，PsDscRunAsCredential}</span><span class="sxs-lookup"><span data-stu-id="d5656-149">{Message, DependsOn, PsDscRunAsCredential}</span></span>         |
|<span data-ttu-id="d5656-150">程序包</span><span class="sxs-lookup"><span data-stu-id="d5656-150">Package</span></span>               |<span data-ttu-id="d5656-151">{Name、Path、ProductId、Arguments ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-151">{Name, Path, ProductId, Arguments...}</span></span>              |
|<span data-ttu-id="d5656-152">注册表</span><span class="sxs-lookup"><span data-stu-id="d5656-152">Registry</span></span>              |<span data-ttu-id="d5656-153">{Key，ValueName，DependsOn，请确保 ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-153">{Key, ValueName, DependsOn, Ensure...}</span></span>             |
|<span data-ttu-id="d5656-154">Script</span><span class="sxs-lookup"><span data-stu-id="d5656-154">Script</span></span>                |<span data-ttu-id="d5656-155">{GetScript，SetScript，TestScript，Credential ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-155">{GetScript, SetScript, TestScript, Credential...}</span></span>  |
|<span data-ttu-id="d5656-156">服务</span><span class="sxs-lookup"><span data-stu-id="d5656-156">Service</span></span>               |<span data-ttu-id="d5656-157">{Name，与 builtinaccount，Credential，依存关系 ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-157">{Name, BuiltInAccount, Credential, Dependencies...}</span></span>|
|<span data-ttu-id="d5656-158">用户</span><span class="sxs-lookup"><span data-stu-id="d5656-158">User</span></span>                  |<span data-ttu-id="d5656-159">{UserName、DependsOn、Description、Disabled ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-159">{UserName, DependsOn, Description, Disabled...}</span></span>    |
|<span data-ttu-id="d5656-160">WaitForAll</span><span class="sxs-lookup"><span data-stu-id="d5656-160">WaitForAll</span></span>            |<span data-ttu-id="d5656-161">{NodeName，Context.resourcename，DependsOn，PsDscRunAsC ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-161">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="d5656-162">WaitForAny</span><span class="sxs-lookup"><span data-stu-id="d5656-162">WaitForAny</span></span>            |<span data-ttu-id="d5656-163">{NodeName，Context.resourcename，DependsOn，PsDscRunAsC ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-163">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="d5656-164">WaitForSome</span><span class="sxs-lookup"><span data-stu-id="d5656-164">WaitForSome</span></span>           |<span data-ttu-id="d5656-165">{NodeCount，NodeName，Context.resourcename，DependsOn ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-165">{NodeCount, NodeName, ResourceName, DependsOn...}</span></span>  |
|<span data-ttu-id="d5656-166">WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="d5656-166">WindowsFeature</span></span>        |<span data-ttu-id="d5656-167">{Name，Credential，DependsOn，请确保 ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-167">{Name, Credential, DependsOn, Ensure...}</span></span>           |
|<span data-ttu-id="d5656-168">WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="d5656-168">WindowsOptionalFeature</span></span>|<span data-ttu-id="d5656-169">{Name，DependsOn，请确保，LogLevel ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-169">{Name, DependsOn, Ensure, LogLevel...}</span></span>             |
|<span data-ttu-id="d5656-170">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="d5656-170">WindowsProcess</span></span>        |<span data-ttu-id="d5656-171">{Arguments，Path，Credential，DependsOn ...}</span><span class="sxs-lookup"><span data-stu-id="d5656-171">{Arguments, Path, Credential, DependsOn...}</span></span>        |

<span data-ttu-id="d5656-172">若要获取系统上可用 DSC 资源的列表，请运行 `Get-DscResource` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d5656-172">To get a list of available DSC resources on your system, run the `Get-DscResource` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d5656-173">在低于 7.0 的 PowerShell 版本中，`Get-DscResource` 找不到基于类的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="d5656-173">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="d5656-174">本主题中的示例演示如何使用 File 和 node.js 资源。</span><span class="sxs-lookup"><span data-stu-id="d5656-174">The example in this topic demonstrates how to use the File and WindowsFeature resources.</span></span> <span data-ttu-id="d5656-175">若要查看可用于资源的所有属性，请在资源关键字中插入光标 (例如，在 PowerShell ISE 中的配置脚本内) 文件，然后按住<kbd>CTRL</kbd> + <kbd>空格键</kbd></span><span class="sxs-lookup"><span data-stu-id="d5656-175">To see all properties that you can use with a resource, insert the cursor in the resource keyword (for example, File) within your configuration script in PowerShell ISE, hold down <kbd>CTRL</kbd>+<kbd>SPACEBAR</kbd></span></span>

## <a name="find-more-resources"></a><span data-ttu-id="d5656-176">查找更多资源</span><span class="sxs-lookup"><span data-stu-id="d5656-176">FIND MORE RESOURCES</span></span>

<span data-ttu-id="d5656-177">您可以下载、安装并了解由 PowerShell 和 DSC 用户社区和 Microsoft 创建的许多其他可用 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="d5656-177">You can download, install, and learn about many other available DSC resources that have been created by the PowerShell and DSC user community, and by Microsoft.</span></span> <span data-ttu-id="d5656-178">请访问 [PowerShell 库](https://www.powershellgallery.com/) ，浏览并了解可用的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="d5656-178">Visit the [PowerShell Gallery](https://www.powershellgallery.com/) to browse and learn about available DSC resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5656-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5656-179">SEE ALSO</span></span>

[<span data-ttu-id="d5656-180">PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="d5656-180">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="d5656-181">内置 PowerShell 所需状态配置资源</span><span class="sxs-lookup"><span data-stu-id="d5656-181">Built-In PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/resources)

[<span data-ttu-id="d5656-182">构建自定义 PowerShell 所需状态配置资源</span><span class="sxs-lookup"><span data-stu-id="d5656-182">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
