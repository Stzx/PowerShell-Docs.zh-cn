---
ms.date: 12/12/2018
keywords: dsc,powershell,配置,安装程序
title: DSC 配置
description: DSC 配置是定义某一特殊类型函数的 PowerShell 脚本。
ms.openlocfilehash: e59ad2791055ee3ff0150c342ec621d0228c4fc1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658555"
---
# <a name="dsc-configurations"></a><span data-ttu-id="70981-104">DSC 配置</span><span class="sxs-lookup"><span data-stu-id="70981-104">DSC Configurations</span></span>

> <span data-ttu-id="70981-105">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="70981-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="70981-106">DSC 配置是定义某一特殊类型函数的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="70981-106">DSC configurations are PowerShell scripts that define a special type of function.</span></span> <span data-ttu-id="70981-107">若要定义配置，你可使用 PowerShell 关键字 **Configuration** 。</span><span class="sxs-lookup"><span data-stu-id="70981-107">To define a configuration, you use the PowerShell keyword **Configuration** .</span></span>

```powershell
Configuration MyDscConfiguration {
    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = 'Present'
            Name = 'RSAT'
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}
MyDscConfiguration
```

<span data-ttu-id="70981-108">将脚本保存为 `.ps1` 文件。</span><span class="sxs-lookup"><span data-stu-id="70981-108">Save the script as a `.ps1` file.</span></span>

## <a name="configuration-syntax"></a><span data-ttu-id="70981-109">配置语法</span><span class="sxs-lookup"><span data-stu-id="70981-109">Configuration syntax</span></span>

<span data-ttu-id="70981-110">配置脚本由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="70981-110">A configuration script consists of the following parts:</span></span>

- <span data-ttu-id="70981-111">**配置** 块。</span><span class="sxs-lookup"><span data-stu-id="70981-111">The **Configuration** block.</span></span> <span data-ttu-id="70981-112">这是最外层的脚本块。</span><span class="sxs-lookup"><span data-stu-id="70981-112">This is the outermost script block.</span></span> <span data-ttu-id="70981-113">你可通过使用 **Configuration** 关键字并提供配置名进行定义。</span><span class="sxs-lookup"><span data-stu-id="70981-113">You define it by using the **Configuration** keyword and providing a name.</span></span> <span data-ttu-id="70981-114">在这种情况下，该配置名为“MyDscConfiguration”。</span><span class="sxs-lookup"><span data-stu-id="70981-114">In this case, the name of the configuration is "MyDscConfiguration".</span></span>
- <span data-ttu-id="70981-115">一个或多个 **节点** 块。</span><span class="sxs-lookup"><span data-stu-id="70981-115">One or more **Node** blocks.</span></span> <span data-ttu-id="70981-116">这些将定义正在配置的节点（计算机或 VM）。</span><span class="sxs-lookup"><span data-stu-id="70981-116">These define the nodes (computers or VMs) that you are configuring.</span></span>
  <span data-ttu-id="70981-117">在以上配置中，有一个以计算机为目标的名为“TEST-PC1”的 **节点** 块。</span><span class="sxs-lookup"><span data-stu-id="70981-117">In the above configuration, there is one **Node** block that targets a computer named "TEST-PC1".</span></span>
  <span data-ttu-id="70981-118">节点块可以接受多个计算机名称。</span><span class="sxs-lookup"><span data-stu-id="70981-118">The Node block can accept multiple computer names.</span></span>
- <span data-ttu-id="70981-119">一个或多个资源块。</span><span class="sxs-lookup"><span data-stu-id="70981-119">One or more resource blocks.</span></span> <span data-ttu-id="70981-120">这是此配置为其正在配置的资源设置属性的位置。</span><span class="sxs-lookup"><span data-stu-id="70981-120">This is where the configuration sets the properties for the resources that it is configuring.</span></span> <span data-ttu-id="70981-121">在这种情况下，有两个资源块，每个资源块都调用“WindowsFeature”资源。</span><span class="sxs-lookup"><span data-stu-id="70981-121">In this case, there are two resource blocks, each of which call the "WindowsFeature" resource.</span></span>

<span data-ttu-id="70981-122">在 **配置** 块中，可执行在 PowerShell 函数中通常可执行的任何操作。</span><span class="sxs-lookup"><span data-stu-id="70981-122">Within a **Configuration** block, you can do anything that you normally could in a PowerShell function.</span></span> <span data-ttu-id="70981-123">例如，在上一示例中，如果不想在配置中对目标计算机名进行硬编码，则可以为节点名添加参数：</span><span class="sxs-lookup"><span data-stu-id="70981-123">For example, in the previous example, if you didn't want to hard code the name of the target computer in the configuration, you could add a parameter for the node name:</span></span>

<span data-ttu-id="70981-124">在此示例中，指定节点名称，具体方法为在编译配置时以 ComputerName  参数的形式传递节点名称。</span><span class="sxs-lookup"><span data-stu-id="70981-124">In this example, you specify the name of the node by passing it as the **ComputerName** parameter when you compile the configuration.</span></span> <span data-ttu-id="70981-125">该名称默认为“localhost”。</span><span class="sxs-lookup"><span data-stu-id="70981-125">The name defaults to "localhost".</span></span>

```powershell
Configuration MyDscConfiguration
{
    param
    (
        [string[]]$ComputerName='localhost'
    )

    Node $ComputerName
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

<span data-ttu-id="70981-126"> 节点块还可以接受多个计算机名称。</span><span class="sxs-lookup"><span data-stu-id="70981-126">The **Node** block can also accept multiple computer names.</span></span> <span data-ttu-id="70981-127">在上述示例中，可以使用 `-ComputerName` 参数，也可以将以逗号分隔的计算机列表直接传递到节点  块。</span><span class="sxs-lookup"><span data-stu-id="70981-127">In the above example, you can either use the `-ComputerName` parameter, or pass a comma-separated list of computers directly to the **Node** block.</span></span>

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

<span data-ttu-id="70981-128">将计算机列表从配置指定到节点  块时，需要使用数组表示法。</span><span class="sxs-lookup"><span data-stu-id="70981-128">When specifying a list of computers to the **Node** block, from within a Configuration, you need to use array-notation.</span></span>

```powershell
Configuration MyDscConfiguration
{
    Node @('localhost', 'Server01')
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

## <a name="compiling-the-configuration"></a><span data-ttu-id="70981-129">正在编译配置</span><span class="sxs-lookup"><span data-stu-id="70981-129">Compiling the configuration</span></span>

<span data-ttu-id="70981-130">必须将其编译为 MOF 文档才能执行配置。</span><span class="sxs-lookup"><span data-stu-id="70981-130">Before you can enact a configuration, you have to compile it into a MOF document.</span></span> <span data-ttu-id="70981-131">可通过调用配置（像调用 PowerShell 函数一样）来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="70981-131">You do this by calling the configuration like you would call a PowerShell function.</span></span> <span data-ttu-id="70981-132">此示例的最后一行仅包含配置名称，用于调用配置。</span><span class="sxs-lookup"><span data-stu-id="70981-132">The last line of the example containing only the name of the configuration, calls the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="70981-133">函数必须在全局范围内（与其他任何 PowerShell 函数一样），才能调用配置。</span><span class="sxs-lookup"><span data-stu-id="70981-133">To call a configuration, the function must be in global scope (as with any other PowerShell function).</span></span> <span data-ttu-id="70981-134">可通过以下方式来实现此操作：对脚本执行“dot-source”操作，或者使用 F5 或单击 ISE 中的“运行脚本”  按钮以运行配置脚本。</span><span class="sxs-lookup"><span data-stu-id="70981-134">You can make this happen either by "dot-sourcing" the script, or by running the configuration script by using F5 or clicking on the **Run Script** button in the ISE.</span></span> <span data-ttu-id="70981-135">若要对脚本执行“dot-source”操作，请运行命令 `. .\myConfig.ps1`，其中 `myConfig.ps1` 是包含配置的脚本文件的名称。</span><span class="sxs-lookup"><span data-stu-id="70981-135">To dot-source the script, run the command `. .\myConfig.ps1` where `myConfig.ps1` is the name of the script file that contains your configuration.</span></span>

<span data-ttu-id="70981-136">调用配置时，它会：</span><span class="sxs-lookup"><span data-stu-id="70981-136">When you call the configuration, it:</span></span>

- <span data-ttu-id="70981-137">解析所有变量</span><span class="sxs-lookup"><span data-stu-id="70981-137">Resolves all variables</span></span>
- <span data-ttu-id="70981-138">在当前目录中使用与配置相同的名称创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="70981-138">Creates a folder in the current directory with the same name as the configuration.</span></span>
- <span data-ttu-id="70981-139">在新目录中创建名为 _NodeName_ .mof 的文件，其中 _NodeName_ 为配置的目标节点名称。</span><span class="sxs-lookup"><span data-stu-id="70981-139">Creates a file named _NodeName_ .mof in the new directory, where _NodeName_ is the name of the target node of the configuration.</span></span> <span data-ttu-id="70981-140">如果有多个节点，则将为每个节点创建一个 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="70981-140">If there is more than one node, a MOF file will be created for each node.</span></span>

> [!NOTE]
> <span data-ttu-id="70981-141">MOF 文件包含目标节点的所有配置信息。</span><span class="sxs-lookup"><span data-stu-id="70981-141">The MOF file contains all of the configuration information for the target node.</span></span> <span data-ttu-id="70981-142">因此，确保其安全非常重要。</span><span class="sxs-lookup"><span data-stu-id="70981-142">Because of this, it's important to keep it secure.</span></span> <span data-ttu-id="70981-143">有关详细信息，请参阅[保护 MOF 文件](../pull-server/secureMOF.md)。</span><span class="sxs-lookup"><span data-stu-id="70981-143">For more information, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>

<span data-ttu-id="70981-144">编译上述第一个配置会形成以下文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="70981-144">Compiling the first configuration above results in the following folder structure:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 localhost.mof
```

<span data-ttu-id="70981-145">如果配置采用了参数（如示例 2 所述），则需在编译时提供该参数。</span><span class="sxs-lookup"><span data-stu-id="70981-145">If the configuration takes a parameter, as in the second example, that has to be provided at compile time.</span></span> <span data-ttu-id="70981-146">其形式如下：</span><span class="sxs-lookup"><span data-stu-id="70981-146">Here's how that would look:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration -ComputerName 'MyTestNode'
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 MyTestNode.mof
```

## <a name="using-new-resources-in-your-configuration"></a><span data-ttu-id="70981-147">在配置中使用新的资源</span><span class="sxs-lookup"><span data-stu-id="70981-147">Using new resources in Your configuration</span></span>

<span data-ttu-id="70981-148">如果运行了前面的示例，你可能注意到你已收到警告信息，提示你正在使用未显式导入的资源。</span><span class="sxs-lookup"><span data-stu-id="70981-148">If you ran the previous examples, you might have noticed that you were warned that you were using a resource without explicitly importing it.</span></span> <span data-ttu-id="70981-149">现在，DSC 附带 12 种资源作为 PSDesiredStateConfiguration 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="70981-149">Today, DSC ships with 12 resources as part of the PSDesiredStateConfiguration module.</span></span>

<span data-ttu-id="70981-150">cmdlet - [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)，可用来确定哪些资源已安装在系统上并且可供 LCM 使用。</span><span class="sxs-lookup"><span data-stu-id="70981-150">The cmdlet, [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), can be used to determine what resources are installed on the system and available for use by the LCM.</span></span>
<span data-ttu-id="70981-151">一旦这些模块已置于 `$env:PSModulePath` 中并由 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) 正确识别，你仍需在配置中加载它们。</span><span class="sxs-lookup"><span data-stu-id="70981-151">Once these modules have been placed in `$env:PSModulePath` and are properly recognized by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), they still need to be loaded within your configuration.</span></span>

<span data-ttu-id="70981-152"> Import-DscResource 是仅可在配置  块中识别的动态关键字，它不是 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="70981-152">**Import-DscResource** is a dynamic keyword that can only be recognized within a **Configuration** block, it is not a cmdlet.</span></span> <span data-ttu-id="70981-153">**Import-DscResource** 支持两种参数：</span><span class="sxs-lookup"><span data-stu-id="70981-153">**Import-DscResource** supports two parameters:</span></span>

- <span data-ttu-id="70981-154">**ModuleName** 是使用 **Import-DscResource** 的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="70981-154">**ModuleName** is the recommended way of using **Import-DscResource** .</span></span> <span data-ttu-id="70981-155">它接受包含要导入资源的模块名称以及模块名称的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="70981-155">It accepts the name of the module that contains the resources to be imported (as well as a string array of module names).</span></span>
- <span data-ttu-id="70981-156">**Name** 是要导入资源的名称。</span><span class="sxs-lookup"><span data-stu-id="70981-156">**Name** is the name of the resource to import.</span></span> <span data-ttu-id="70981-157">这不是由 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) 返回为“Name”的友好名称，而是定义资源架构时使用的类名（由 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) 返回为 **ResourceType** ）。</span><span class="sxs-lookup"><span data-stu-id="70981-157">This is not the friendly name returned as "Name" by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), but the class name used when defining the resource schema (returned as **ResourceType** by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span></span>

<span data-ttu-id="70981-158">有关使用 `Import-DSCResource` 的详细信息，请参阅[使用 Import-DSCResource](import-dscresource.md)</span><span class="sxs-lookup"><span data-stu-id="70981-158">For more information on using `Import-DSCResource`, see [Using Import-DSCResource](import-dscresource.md)</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="70981-159">PowerShell v4 和 v5 差异</span><span class="sxs-lookup"><span data-stu-id="70981-159">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="70981-160">DSC 资源需要在 PowerShell 4.0 中存储的位置存在差异。</span><span class="sxs-lookup"><span data-stu-id="70981-160">There are differences in where DSC resources need to be stored in PowerShell 4.0.</span></span> <span data-ttu-id="70981-161">有关详细信息，请参阅[资源位置](import-dscresource.md#resource-location)。</span><span class="sxs-lookup"><span data-stu-id="70981-161">For more information, see [Resource location](import-dscresource.md#resource-location).</span></span>

## <a name="see-also"></a><span data-ttu-id="70981-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70981-162">See Also</span></span>

- [<span data-ttu-id="70981-163">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="70981-163">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="70981-164">DSC 资源</span><span class="sxs-lookup"><span data-stu-id="70981-164">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="70981-165">配置本地配置管理器</span><span class="sxs-lookup"><span data-stu-id="70981-165">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
