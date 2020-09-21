---
ms.date: 07/08/2020
keywords: dsc,powershell,配置,安装程序
title: Get-Test-Set
ms.openlocfilehash: f7b7e947a85832365a783e40c25a25bfaa9fff8d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771509"
---
# <a name="get-test-set"></a><span data-ttu-id="38355-103">Get-Test-Set</span><span class="sxs-lookup"><span data-stu-id="38355-103">Get-Test-Set</span></span>

><span data-ttu-id="38355-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="38355-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="38355-105">PowerShell Desired State Configuration 是围绕 Get\*\*\*\*、Test\*\*\*\* 和 Set\*\*\*\* 进程构建的。</span><span class="sxs-lookup"><span data-stu-id="38355-105">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="38355-106">每个 DSC [资源](resources.md) 都包含完成这些操作的方法。</span><span class="sxs-lookup"><span data-stu-id="38355-106">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span>
<span data-ttu-id="38355-107">在[配置](../configurations/configurations.md)中，定义资源块来填充成为资源的 Get\*\*\*\*、Test\*\*\*\* 和 Set\*\*\*\* 方法参数的键。</span><span class="sxs-lookup"><span data-stu-id="38355-107">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="38355-108">这是 Service\*\*\*\* 资源块的语法。</span><span class="sxs-lookup"><span data-stu-id="38355-108">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="38355-109">Service\*\*\*\* 资源配置 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="38355-109">The **Service** resource configures Windows services.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

<span data-ttu-id="38355-110">Service \*\*\*\* 资源的 Get\*\*\*\*、Test\*\*\*\* 和 Set\*\*\*\* 方法将具有接受这些值的参数块。</span><span class="sxs-lookup"><span data-stu-id="38355-110">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

```powershell
param
(
    [parameter(Mandatory = $true)]
    [ValidateNotNullOrEmpty()]
    [System.String]
    $Name,

    [System.String]
    [ValidateSet("Automatic", "Manual", "Disabled")]
    $StartupType,

    [System.String]
    [ValidateSet("LocalSystem", "LocalService", "NetworkService")]
    $BuiltInAccount,

    [System.Management.Automation.PSCredential]
    [ValidateNotNull()]
    $Credential,

    [System.String]
    [ValidateSet("Running", "Stopped")]
    $State="Running",

    [System.String]
    [ValidateNotNullOrEmpty()]
    $DisplayName,

    [System.String]
    [ValidateNotNullOrEmpty()]
    $Description,

    [System.String]
    [ValidateNotNullOrEmpty()]
    $Path,

    [System.String[]]
    [ValidateNotNullOrEmpty()]
    $Dependencies,

    [System.String]
    [ValidateSet("Present", "Absent")]
    $Ensure="Present"
)
```

> [!NOTE]
> <span data-ttu-id="38355-111">用于定义资源的语言和方法决定了如何定义 Get\*\*\*\*、Test\*\*\*\* 和 Set\*\*\*\* 方法。</span><span class="sxs-lookup"><span data-stu-id="38355-111">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="38355-112">由于 Service\*\*\*\* 资源只有一个必需的键 (`Name`)，因此 Service\*\*\*\* 块资源可以非常简单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38355-112">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

```powershell
Configuration TestConfig
{
    Import-DSCResource -Name Service
    Node localhost
    {
        Service "MyService"
        {
            Name = "Spooler"
        }
    }
}
```

<span data-ttu-id="38355-113">编译上述配置时，为键指定的值存储在生成的 `.mof` 文件中。</span><span class="sxs-lookup"><span data-stu-id="38355-113">When you compile the Configuration above, the values you specify for a key are stored in the `.mof` file that is generated.</span></span> <span data-ttu-id="38355-114">有关详细信息，请参阅 [MOF](/windows/desktop/wmisdk/managed-object-format--mof-)。</span><span class="sxs-lookup"><span data-stu-id="38355-114">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

```
instance of MSFT_ServiceResource as $MSFT_ServiceResource1ref
{
SourceInfo = "::5::1::Service";
 ModuleName = "PsDesiredStateConfiguration";
 ResourceID = "[Service]MyService";
 Name = "Spooler";

ModuleVersion = "1.0";

 ConfigurationName = "Test";

};
```

<span data-ttu-id="38355-115">应用时，[本地 Configuration Manager](../managing-nodes/metaConfig.md) (LCM) 将从 `.mof` 文件读取值“Spooler”，并将其传递给 Service 资源中“MyService”实例的 Get、Test 和 Set 方法的 Name 参数    。</span><span class="sxs-lookup"><span data-stu-id="38355-115">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the `.mof` file, and pass it to the **Name** parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="38355-116">获取</span><span class="sxs-lookup"><span data-stu-id="38355-116">Get</span></span>

<span data-ttu-id="38355-117">资源的 Get\*\*\*\* 方法，检索在目标节点上配置的资源的状态。</span><span class="sxs-lookup"><span data-stu-id="38355-117">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="38355-118">此状态作为[哈希表](/powershell/module/microsoft.powershell.core/about/about_hash_tables)返回。</span><span class="sxs-lookup"><span data-stu-id="38355-118">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>
<span data-ttu-id="38355-119">哈希表\*\*\*\* 的键是资源接受的可配置值或参数。</span><span class="sxs-lookup"><span data-stu-id="38355-119">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="38355-120">Get\*\*\*\* 方法直接映射到 [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="38355-120">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="38355-121">调用 `Get-DSCConfiguration` 时，LCM 运行当前应用配置中每个资源的 Get\*\*\*\* 方法。</span><span class="sxs-lookup"><span data-stu-id="38355-121">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="38355-122">LCM 使用存储在 `.mof` 中的键值作为每个相应资源实例的参数。</span><span class="sxs-lookup"><span data-stu-id="38355-122">The LCM uses the key values stored in the `.mof` file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="38355-123">这是配置“Spooler”服务的 Service\*\*\*\* 资源的示例输出。</span><span class="sxs-lookup"><span data-stu-id="38355-123">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

```output
ConfigurationName    : Test
DependsOn            :
ModuleName           : PsDesiredStateConfiguration
ModuleVersion        : 1.1
PsDscRunAsCredential :
ResourceId           : [Service]Spooler
SourceInfo           :
BuiltInAccount       : LocalSystem
Credential           :
Dependencies         : {RPCSS, http}
Description          : This service spools print jobs and handles interaction with the printer.  If you turn off
                       this service, you won't be able to print or see your printers.
DisplayName          : Print Spooler
Ensure               :
Name                 : Spooler
Path                 : C:\WINDOWS\System32\spoolsv.exe
StartupType          : Automatic
State                : Running
Status               :
PSComputerName       :
CimClassName         : MSFT_ServiceResource
```

<span data-ttu-id="38355-124">输出显示了 Service\*\*\*\* 资源可配置的当前值属性。</span><span class="sxs-lookup"><span data-stu-id="38355-124">The output shows the current value properties configurable by the **Service** resource.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

## <a name="test"></a><span data-ttu-id="38355-125">测试</span><span class="sxs-lookup"><span data-stu-id="38355-125">Test</span></span>

<span data-ttu-id="38355-126">资源的 Test\*\*\*\* 方法确定目标节点当前是否符合资源的所需状态__。</span><span class="sxs-lookup"><span data-stu-id="38355-126">The **Test** method of a resource determines if the target node is currently compliant with the resource's _desired state_.</span></span> <span data-ttu-id="38355-127">Test\*\*\*\* 方法返回 `$true` 或 `$false` 以仅指示节点是否符合。</span><span class="sxs-lookup"><span data-stu-id="38355-127">The **Test** method returns `$true` or `$false` only to indicate whether the Node is compliant.</span></span> <span data-ttu-id="38355-128">调用 [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) 时，LCM 调用当前应用配置中每个资源的 Test\*\*\*\* 方法。</span><span class="sxs-lookup"><span data-stu-id="38355-128">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="38355-129">LCM 使用存储在“.mof”中的键值作为每个相应资源实例的参数。</span><span class="sxs-lookup"><span data-stu-id="38355-129">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="38355-130">如果任何单个资源的 Test 结果是 `$false`，则 `Test-DSCConfiguration` 返回 `$false`，表示该节点不符合。</span><span class="sxs-lookup"><span data-stu-id="38355-130">If the result of any individual resource's **Test** is `$false`, `Test-DSCConfiguration` returns `$false` indicating that the Node is not compliant.</span></span> <span data-ttu-id="38355-131">如果所有资源的 Test 方法都返回 `$true`，则 `Test-DSCConfiguration` 返回 `$true`，表示该节点符合。</span><span class="sxs-lookup"><span data-stu-id="38355-131">If all resource's **Test** methods return `$true`, `Test-DSCConfiguration` returns `$true` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="38355-132">从 PowerShell 5.0 开始，已添加 Detailed 参数。</span><span class="sxs-lookup"><span data-stu-id="38355-132">Beginning in PowerShell 5.0, the **Detailed** parameter was added.</span></span> <span data-ttu-id="38355-133">指定 Detailed 将导致 `Test-DSCConfiguration` 返回一个对象，该对象包含符合和不符合资源的结果集合。</span><span class="sxs-lookup"><span data-stu-id="38355-133">Specifying **Detailed** causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="38355-134">有关详细信息，请参阅 [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span><span class="sxs-lookup"><span data-stu-id="38355-134">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="38355-135">设置</span><span class="sxs-lookup"><span data-stu-id="38355-135">Set</span></span>

<span data-ttu-id="38355-136">资源的 Set\*\*\*\* 方法尝试强制节点符合资源的所需状态\*\*。</span><span class="sxs-lookup"><span data-stu-id="38355-136">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="38355-137">Set\*\*\*\* 方法旨在幂等\*\*\*\*，这意味着 Set\*\*\*\* 可以多次运行，并始终得到相同的结果而没有错误。</span><span class="sxs-lookup"><span data-stu-id="38355-137">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span> <span data-ttu-id="38355-138">当运行 [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration) 时，LCM 在当前应用的配置中循环切换每个资源。</span><span class="sxs-lookup"><span data-stu-id="38355-138">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="38355-139">LCM 从“.mof”文件检索当前资源实例的键值，并使用它们作为 Test\*\*\*\* 方法的参数。</span><span class="sxs-lookup"><span data-stu-id="38355-139">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="38355-140">如果 Test\*\*\*\* 方法返回 `$true`，则节点符合当前资源，并跳过 Set\*\*\*\* 方法。</span><span class="sxs-lookup"><span data-stu-id="38355-140">If the **Test** method returns `$true`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="38355-141">如果 Test\*\*\*\* 返回 `$false`，则节点不符合。</span><span class="sxs-lookup"><span data-stu-id="38355-141">If the **Test** returns `$false`, the Node is non-compliant.</span></span> <span data-ttu-id="38355-142">LCM 将资源实例的键值作为参数传递给资源的 Set\*\*\*\* 方法，使节点恢复符合性。</span><span class="sxs-lookup"><span data-stu-id="38355-142">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="38355-143">通过指定 Verbose 和 Wait 参数，可以查看 `Start-DSCConfiguration` cmdlet 的进度 。</span><span class="sxs-lookup"><span data-stu-id="38355-143">By specifying the **Verbose** and **Wait** parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="38355-144">在此示例中，节点已具有符合性。</span><span class="sxs-lookup"><span data-stu-id="38355-144">In this example, the Node is already compliant.</span></span> <span data-ttu-id="38355-145">`Verbose` 输出表明跳过了 Set\*\*\*\* 方法。</span><span class="sxs-lookup"><span data-stu-id="38355-145">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -UseExisting

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
ApplyConfiguration,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid
S-1-5-21-124525095-708259637-1543119021-1282804.
VERBOSE: [SERVER01]:                            [] Starting consistency engine.
VERBOSE: [SERVER01]:                            [] Checking consistency for current configuration.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\DscResources\MSFT_ServiceResource\MSFT
_ServiceResource.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [[Service]Spooler] Importing the module MSFT_ServiceResource in
force mode.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Service]Spooler]  in 0.2540 seconds.
VERBOSE: [SERVER01]: LCM:  [ Skip   Set      ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [] Consistency check completed.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 1.379 seconds
```

## <a name="see-also"></a><span data-ttu-id="38355-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38355-146">See also</span></span>

- [<span data-ttu-id="38355-147">Azure Automation DSC 概述</span><span class="sxs-lookup"><span data-stu-id="38355-147">Azure Automation DSC Overview</span></span>](/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="38355-148">设置 SMB 请求服务器</span><span class="sxs-lookup"><span data-stu-id="38355-148">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="38355-149">配置请求客户端</span><span class="sxs-lookup"><span data-stu-id="38355-149">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)
