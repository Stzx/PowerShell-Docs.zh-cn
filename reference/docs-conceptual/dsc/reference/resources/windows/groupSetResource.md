---
ms.date: 09/20/2019
keywords: dsc,powershell,配置,安装程序
description: 提供了管理目标节点上的本地组的机制。
title: DSC GroupSet 资源
ms.openlocfilehash: 90e0c3f0e09c6a300988869265dfdb432ed5d217
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464189"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="daa72-104">DSC GroupSet 资源</span><span class="sxs-lookup"><span data-stu-id="daa72-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="daa72-105">适用于：Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="daa72-105">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="daa72-106">Windows PowerShell Desired State Configuration (DSC) 中的 **GroupSet** 资源提供了管理目标节点上的本地组的机制。</span><span class="sxs-lookup"><span data-stu-id="daa72-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="daa72-107">此资源是[复合资源](../../../resources/authoringResourceComposite.md)，它会针对 `GroupName` 参数中指定的每个组调用 [Group 资源](groupResource.md)。</span><span class="sxs-lookup"><span data-stu-id="daa72-107">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="daa72-108">当你要对多个组添加和/或删除相同成员列表、删除多个组或添加具有相同成员列表的多个组时，请使用此资源。</span><span class="sxs-lookup"><span data-stu-id="daa72-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="daa72-109">语法</span><span class="sxs-lookup"><span data-stu-id="daa72-109">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="daa72-110">属性</span><span class="sxs-lookup"><span data-stu-id="daa72-110">Properties</span></span>

|<span data-ttu-id="daa72-111">properties</span><span class="sxs-lookup"><span data-stu-id="daa72-111">Property</span></span> |<span data-ttu-id="daa72-112">说明</span><span class="sxs-lookup"><span data-stu-id="daa72-112">Description</span></span> |
|---|---|
|<span data-ttu-id="daa72-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="daa72-113">GroupName</span></span> |<span data-ttu-id="daa72-114">要确保其处于特定状态的组的名称。</span><span class="sxs-lookup"><span data-stu-id="daa72-114">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="daa72-115">成员</span><span class="sxs-lookup"><span data-stu-id="daa72-115">Members</span></span> |<span data-ttu-id="daa72-116">使用此属性将当前的组成员身份替换为指定成员。</span><span class="sxs-lookup"><span data-stu-id="daa72-116">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="daa72-117">此属性的值是一组形式为 `Domain\UserName` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="daa72-117">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="daa72-118">如果你在配置中设置此属性，请勿使用 **MembersToExclude** 或 **MembersToInclude** 属性。</span><span class="sxs-lookup"><span data-stu-id="daa72-118">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="daa72-119">这样做会导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="daa72-119">Doing so will generate an error.</span></span> |
|<span data-ttu-id="daa72-120">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="daa72-120">MembersToInclude</span></span> |<span data-ttu-id="daa72-121">使用此属性将成员添加到组的现有成员资格中。</span><span class="sxs-lookup"><span data-stu-id="daa72-121">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="daa72-122">此属性的值是一组形式为 `Domain\UserName` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="daa72-122">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="daa72-123">如果你在配置中设置此属性，请勿使用 **Members** 属性。</span><span class="sxs-lookup"><span data-stu-id="daa72-123">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="daa72-124">这样做会导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="daa72-124">Doing so will generate an error.</span></span> |
|<span data-ttu-id="daa72-125">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="daa72-125">MembersToExclude</span></span> |<span data-ttu-id="daa72-126">使用此属性从现有的组成员身份中删除成员。</span><span class="sxs-lookup"><span data-stu-id="daa72-126">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="daa72-127">此属性的值是一组形式为 `Domain\UserName` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="daa72-127">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="daa72-128">如果你在配置中设置此属性，请勿使用 **Members** 属性。</span><span class="sxs-lookup"><span data-stu-id="daa72-128">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="daa72-129">这样做会导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="daa72-129">Doing so will generate an error.</span></span> |
|<span data-ttu-id="daa72-130">凭据</span><span class="sxs-lookup"><span data-stu-id="daa72-130">Credential</span></span> |<span data-ttu-id="daa72-131">访问远程资源所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="daa72-131">The credentials required to access remote resources.</span></span> <span data-ttu-id="daa72-132">此帐户必须具有相应的 Active Directory 权限才能将所有非将本地帐户添加到组中；否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="daa72-132">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="daa72-133">公共属性</span><span class="sxs-lookup"><span data-stu-id="daa72-133">Common properties</span></span>

|<span data-ttu-id="daa72-134">properties</span><span class="sxs-lookup"><span data-stu-id="daa72-134">Property</span></span> |<span data-ttu-id="daa72-135">说明</span><span class="sxs-lookup"><span data-stu-id="daa72-135">Description</span></span> |
|---|---|
|<span data-ttu-id="daa72-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="daa72-136">DependsOn</span></span> |<span data-ttu-id="daa72-137">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="daa72-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="daa72-138">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="daa72-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="daa72-139">Ensure</span><span class="sxs-lookup"><span data-stu-id="daa72-139">Ensure</span></span> |<span data-ttu-id="daa72-140">指示组是否存在。</span><span class="sxs-lookup"><span data-stu-id="daa72-140">Indicates whether the groups exist.</span></span> <span data-ttu-id="daa72-141">将此属性设置为 **Absent** 可确保组不存在。</span><span class="sxs-lookup"><span data-stu-id="daa72-141">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="daa72-142">将其设置为 **Present** 可确保组存在。</span><span class="sxs-lookup"><span data-stu-id="daa72-142">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="daa72-143">默认值为 **Present**。</span><span class="sxs-lookup"><span data-stu-id="daa72-143">The default value is **Present**.</span></span> |
|<span data-ttu-id="daa72-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="daa72-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="daa72-145">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="daa72-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="daa72-146">在 WMF 5.0 中添加了 **PsDscRunAsCredential** 公共属性，用于允许在其他凭据上下文中运行任何 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="daa72-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="daa72-147">有关详细信息，请参阅[将凭据与 DSC 资源配合使用](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="daa72-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="daa72-148">示例 1：确保组存在</span><span class="sxs-lookup"><span data-stu-id="daa72-148">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="daa72-149">下面的示例演示如何确保名为“myGroup”和“myOtherGroup”的两个组存在。</span><span class="sxs-lookup"><span data-stu-id="daa72-149">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="daa72-150">为简单起见，此示例使用纯文本凭据。</span><span class="sxs-lookup"><span data-stu-id="daa72-150">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="daa72-151">有关如何在配置 MOF 文件中加密凭据的信息，请参阅[保护 MOF 文件](../../../pull-server/secureMOF.md)。</span><span class="sxs-lookup"><span data-stu-id="daa72-151">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>
