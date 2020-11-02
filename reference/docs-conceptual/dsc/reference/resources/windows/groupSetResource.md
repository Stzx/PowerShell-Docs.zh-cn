---
ms.date: 09/20/2019
ms.topic: reference
title: DSC GroupSet 资源
description: DSC GroupSet 资源
ms.openlocfilehash: a9d1803aca40ac3571d42a5fd762489c03ed274e
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142882"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="f1a99-103">DSC GroupSet 资源</span><span class="sxs-lookup"><span data-stu-id="f1a99-103">DSC GroupSet Resource</span></span>

> <span data-ttu-id="f1a99-104">适用于：Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="f1a99-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="f1a99-105">Windows PowerShell Desired State Configuration (DSC) 中的 **GroupSet** 资源提供了管理目标节点上的本地组的机制。</span><span class="sxs-lookup"><span data-stu-id="f1a99-105">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="f1a99-106">此资源是[复合资源](../../../resources/authoringResourceComposite.md)，它会针对 `GroupName` 参数中指定的每个组调用 [Group 资源](groupResource.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a99-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="f1a99-107">当你要对多个组添加和/或删除相同成员列表、删除多个组或添加具有相同成员列表的多个组时，请使用此资源。</span><span class="sxs-lookup"><span data-stu-id="f1a99-107">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="f1a99-108">语法</span><span class="sxs-lookup"><span data-stu-id="f1a99-108">Syntax</span></span>

```Syntax
GroupSet [string] #ResourceName
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

## <a name="properties"></a><span data-ttu-id="f1a99-109">属性</span><span class="sxs-lookup"><span data-stu-id="f1a99-109">Properties</span></span>

|<span data-ttu-id="f1a99-110">Property</span><span class="sxs-lookup"><span data-stu-id="f1a99-110">Property</span></span> |<span data-ttu-id="f1a99-111">说明</span><span class="sxs-lookup"><span data-stu-id="f1a99-111">Description</span></span> |
|---|---|
|<span data-ttu-id="f1a99-112">GroupName</span><span class="sxs-lookup"><span data-stu-id="f1a99-112">GroupName</span></span> |<span data-ttu-id="f1a99-113">要确保其处于特定状态的组的名称。</span><span class="sxs-lookup"><span data-stu-id="f1a99-113">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="f1a99-114">成员</span><span class="sxs-lookup"><span data-stu-id="f1a99-114">Members</span></span> |<span data-ttu-id="f1a99-115">使用此属性将当前的组成员身份替换为指定成员。</span><span class="sxs-lookup"><span data-stu-id="f1a99-115">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="f1a99-116">此属性的值是一组形式为 `Domain\UserName` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="f1a99-116">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="f1a99-117">如果你在配置中设置此属性，请勿使用 **MembersToExclude** 或 **MembersToInclude** 属性。</span><span class="sxs-lookup"><span data-stu-id="f1a99-117">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="f1a99-118">这样做会导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="f1a99-118">Doing so will generate an error.</span></span> |
|<span data-ttu-id="f1a99-119">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="f1a99-119">MembersToInclude</span></span> |<span data-ttu-id="f1a99-120">使用此属性将成员添加到组的现有成员资格中。</span><span class="sxs-lookup"><span data-stu-id="f1a99-120">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="f1a99-121">此属性的值是一组形式为 `Domain\UserName` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="f1a99-121">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="f1a99-122">如果你在配置中设置此属性，请勿使用 **Members** 属性。</span><span class="sxs-lookup"><span data-stu-id="f1a99-122">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="f1a99-123">这样做会导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="f1a99-123">Doing so will generate an error.</span></span> |
|<span data-ttu-id="f1a99-124">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="f1a99-124">MembersToExclude</span></span> |<span data-ttu-id="f1a99-125">使用此属性从现有的组成员身份中删除成员。</span><span class="sxs-lookup"><span data-stu-id="f1a99-125">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="f1a99-126">此属性的值是一组形式为 `Domain\UserName` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="f1a99-126">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="f1a99-127">如果你在配置中设置此属性，请勿使用 **Members** 属性。</span><span class="sxs-lookup"><span data-stu-id="f1a99-127">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="f1a99-128">这样做会导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="f1a99-128">Doing so will generate an error.</span></span> |
|<span data-ttu-id="f1a99-129">凭据</span><span class="sxs-lookup"><span data-stu-id="f1a99-129">Credential</span></span> |<span data-ttu-id="f1a99-130">访问远程资源所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="f1a99-130">The credentials required to access remote resources.</span></span> <span data-ttu-id="f1a99-131">此帐户必须具有相应的 Active Directory 权限才能将所有非将本地帐户添加到组中；否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="f1a99-131">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="f1a99-132">公共属性</span><span class="sxs-lookup"><span data-stu-id="f1a99-132">Common properties</span></span>

|<span data-ttu-id="f1a99-133">properties</span><span class="sxs-lookup"><span data-stu-id="f1a99-133">Property</span></span> |<span data-ttu-id="f1a99-134">说明</span><span class="sxs-lookup"><span data-stu-id="f1a99-134">Description</span></span> |
|---|---|
|<span data-ttu-id="f1a99-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="f1a99-135">DependsOn</span></span> |<span data-ttu-id="f1a99-136">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="f1a99-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="f1a99-137">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="f1a99-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="f1a99-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="f1a99-138">Ensure</span></span> |<span data-ttu-id="f1a99-139">指示组是否存在。</span><span class="sxs-lookup"><span data-stu-id="f1a99-139">Indicates whether the groups exist.</span></span> <span data-ttu-id="f1a99-140">将此属性设置为 **Absent** 可确保组不存在。</span><span class="sxs-lookup"><span data-stu-id="f1a99-140">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="f1a99-141">将其设置为 **Present** 可确保组存在。</span><span class="sxs-lookup"><span data-stu-id="f1a99-141">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="f1a99-142">默认值为 **Present** 。</span><span class="sxs-lookup"><span data-stu-id="f1a99-142">The default value is **Present** .</span></span> |
|<span data-ttu-id="f1a99-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="f1a99-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="f1a99-144">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="f1a99-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="f1a99-145">在 WMF 5.0 中添加了 **PsDscRunAsCredential** 公共属性，用于允许在其他凭据上下文中运行任何 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="f1a99-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="f1a99-146">有关详细信息，请参阅[将凭据与 DSC 资源配合使用](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a99-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="f1a99-147">示例 1：确保组存在</span><span class="sxs-lookup"><span data-stu-id="f1a99-147">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="f1a99-148">下面的示例演示如何确保名为“myGroup”和“myOtherGroup”的两个组存在。</span><span class="sxs-lookup"><span data-stu-id="f1a99-148">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

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
> <span data-ttu-id="f1a99-149">为简单起见，此示例使用纯文本凭据。</span><span class="sxs-lookup"><span data-stu-id="f1a99-149">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="f1a99-150">有关如何在配置 MOF 文件中加密凭据的信息，请参阅[保护 MOF 文件](../../../pull-server/secureMOF.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a99-150">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>
