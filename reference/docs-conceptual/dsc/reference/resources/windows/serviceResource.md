---
ms.date: 09/20/2019
keywords: dsc,powershell,配置,安装程序
title: DSC Service 资源
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463578"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="c0e0f-103">DSC Service 资源</span><span class="sxs-lookup"><span data-stu-id="c0e0f-103">DSC Service Resource</span></span>

> <span data-ttu-id="c0e0f-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="c0e0f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="c0e0f-105">Windows PowerShell Desired State Configuration (DSC) 中的 **Service** 资源提供了在目标节点上管理服务的机制。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0e0f-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0e0f-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a><span data-ttu-id="c0e0f-107">属性</span><span class="sxs-lookup"><span data-stu-id="c0e0f-107">Properties</span></span>

|<span data-ttu-id="c0e0f-108">properties</span><span class="sxs-lookup"><span data-stu-id="c0e0f-108">Property</span></span> |<span data-ttu-id="c0e0f-109">说明</span><span class="sxs-lookup"><span data-stu-id="c0e0f-109">Description</span></span> |
|---|---|
|<span data-ttu-id="c0e0f-110">名称</span><span class="sxs-lookup"><span data-stu-id="c0e0f-110">Name</span></span> |<span data-ttu-id="c0e0f-111">指示服务名称。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-111">Indicates the service name.</span></span> <span data-ttu-id="c0e0f-112">请注意，有时它与显示名称不同。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="c0e0f-113">可使用 `Get-Service` cmdlet 获取服务及其当前状态的列表。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="c0e0f-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="c0e0f-114">BuiltInAccount</span></span> |<span data-ttu-id="c0e0f-115">指示要用于服务的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="c0e0f-116">允许用于此属性的值有：LocalService  、LocalSystem  和 NetworkService  。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="c0e0f-117">凭据</span><span class="sxs-lookup"><span data-stu-id="c0e0f-117">Credential</span></span> |<span data-ttu-id="c0e0f-118">指示服务将在其下运行的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="c0e0f-119">此属性与 **BuiltinAccount** 属性不能一起使用。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="c0e0f-120">StartupTimeout</span><span class="sxs-lookup"><span data-stu-id="c0e0f-120">StartupTimeout</span></span> | <span data-ttu-id="c0e0f-121">等待服务运行的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-121">The time to wait for the service to be running in milliseconds.</span></span>|
|<span data-ttu-id="c0e0f-122">StartupType</span><span class="sxs-lookup"><span data-stu-id="c0e0f-122">StartupType</span></span> |<span data-ttu-id="c0e0f-123">设置服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-123">Indicates the startup type for the service.</span></span> <span data-ttu-id="c0e0f-124">允许用于此属性的值有：**Automatic**、**Disabled** 和 **Manual**。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-124">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="c0e0f-125">状态</span><span class="sxs-lookup"><span data-stu-id="c0e0f-125">State</span></span> |<span data-ttu-id="c0e0f-126">指示你想要确保服务所处的状态。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-126">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="c0e0f-127">有效值为：**Running** 或 **Stopped**。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-127">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="c0e0f-128">TerminateTimeout</span><span class="sxs-lookup"><span data-stu-id="c0e0f-128">TerminateTimeout</span></span> |<span data-ttu-id="c0e0f-129">等待服务停止的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-129">The time to wait for the service to be stopped in milliseconds.</span></span>|
|<span data-ttu-id="c0e0f-130">依赖项</span><span class="sxs-lookup"><span data-stu-id="c0e0f-130">Dependencies</span></span> | <span data-ttu-id="c0e0f-131">服务应具有的依赖项名称的数组。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-131">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="c0e0f-132">说明</span><span class="sxs-lookup"><span data-stu-id="c0e0f-132">Description</span></span> |<span data-ttu-id="c0e0f-133">指示目标服务的说明。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-133">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="c0e0f-134">DesktopInteract</span><span class="sxs-lookup"><span data-stu-id="c0e0f-134">DesktopInteract</span></span> | <span data-ttu-id="c0e0f-135">指示服务是否应该能够与桌面上的窗口进行通信。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-135">Indicates whether or not the service should be able to communicate with a window on the desktop.</span></span> <span data-ttu-id="c0e0f-136">对于未作为 LocalSystem 运行的服务，必须为 false。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-136">Must be false for services not running as LocalSystem.</span></span>|
|<span data-ttu-id="c0e0f-137">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c0e0f-137">DisplayName</span></span> |<span data-ttu-id="c0e0f-138">指示目标服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-138">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="c0e0f-139">路径</span><span class="sxs-lookup"><span data-stu-id="c0e0f-139">Path</span></span> |<span data-ttu-id="c0e0f-140">指示新服务的二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-140">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="c0e0f-141">公共属性</span><span class="sxs-lookup"><span data-stu-id="c0e0f-141">Common properties</span></span>

|<span data-ttu-id="c0e0f-142">properties</span><span class="sxs-lookup"><span data-stu-id="c0e0f-142">Property</span></span> |<span data-ttu-id="c0e0f-143">说明</span><span class="sxs-lookup"><span data-stu-id="c0e0f-143">Description</span></span> |
|---|---|
|<span data-ttu-id="c0e0f-144">DependsOn</span><span class="sxs-lookup"><span data-stu-id="c0e0f-144">DependsOn</span></span> |<span data-ttu-id="c0e0f-145">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-145">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="c0e0f-146">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-146">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="c0e0f-147">Ensure</span><span class="sxs-lookup"><span data-stu-id="c0e0f-147">Ensure</span></span> |<span data-ttu-id="c0e0f-148">指示目标服务是否在系统中存在。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-148">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="c0e0f-149">将此属性设置为 **Absent** 可确保目标服务不存在。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-149">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="c0e0f-150">将其设置为 **Present** 可确保目标服务存在。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-150">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="c0e0f-151">默认值为 **Present**。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-151">The default value is **Present**.</span></span> |
|<span data-ttu-id="c0e0f-152">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c0e0f-152">PsDscRunAsCredential</span></span> |<span data-ttu-id="c0e0f-153">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-153">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="c0e0f-154">在 WMF 5.0 中添加了 **PsDscRunAsCredential** 公共属性，用于允许在其他凭据上下文中运行任何 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-154">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="c0e0f-155">有关详细信息，请参阅[将凭据与 DSC 资源配合使用](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="c0e0f-155">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="c0e0f-156">示例</span><span class="sxs-lookup"><span data-stu-id="c0e0f-156">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
