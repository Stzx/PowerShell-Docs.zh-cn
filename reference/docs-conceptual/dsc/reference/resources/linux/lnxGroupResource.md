---
ms.date: 07/17/2020
ms.topic: reference
title: 适用于 Linux 的 DSC nxGroup 资源
description: 适用于 Linux 的 DSC nxGroup 资源
ms.openlocfilehash: 3544bee763c0a4456002f9a02fde38de5d4fb65c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664257"
---
# <a name="dsc-for-linux-nxgroup-resource"></a><span data-ttu-id="02615-103">适用于 Linux 的 DSC nxGroup 资源</span><span class="sxs-lookup"><span data-stu-id="02615-103">DSC for Linux nxGroup Resource</span></span>

<span data-ttu-id="02615-104">PowerShell Desired State Configuration (DSC) 中的 **nxGroup** 资源提供了在 Linux 节点上管理本地组的机制。</span><span class="sxs-lookup"><span data-stu-id="02615-104">The **nxGroup** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="02615-105">语法</span><span class="sxs-lookup"><span data-stu-id="02615-105">Syntax</span></span>

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a><span data-ttu-id="02615-106">属性</span><span class="sxs-lookup"><span data-stu-id="02615-106">Properties</span></span>

|<span data-ttu-id="02615-107">properties</span><span class="sxs-lookup"><span data-stu-id="02615-107">Property</span></span> |<span data-ttu-id="02615-108">说明</span><span class="sxs-lookup"><span data-stu-id="02615-108">Description</span></span> |
|---|---|
|<span data-ttu-id="02615-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="02615-109">GroupName</span></span> |<span data-ttu-id="02615-110">指定要确保其特定状态的组的名称。</span><span class="sxs-lookup"><span data-stu-id="02615-110">Specifies the name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="02615-111">成员</span><span class="sxs-lookup"><span data-stu-id="02615-111">Members</span></span> |<span data-ttu-id="02615-112">指定构成该组的成员。</span><span class="sxs-lookup"><span data-stu-id="02615-112">Specifies the members that form the group.</span></span> |
|<span data-ttu-id="02615-113">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="02615-113">MembersToInclude</span></span> |<span data-ttu-id="02615-114">指定要确保是该组成员的用户。</span><span class="sxs-lookup"><span data-stu-id="02615-114">Specifies the users who you want to ensure are members of the group.</span></span> |
|<span data-ttu-id="02615-115">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="02615-115">MembersToExclude</span></span> |<span data-ttu-id="02615-116">指定要确保不是该组成员的用户。</span><span class="sxs-lookup"><span data-stu-id="02615-116">Specifies the users who you want to ensure are not members of the group.</span></span> |
|<span data-ttu-id="02615-117">PreferredGroupID</span><span class="sxs-lookup"><span data-stu-id="02615-117">PreferredGroupID</span></span> |<span data-ttu-id="02615-118">尽量将组 ID 设置为提供的值。</span><span class="sxs-lookup"><span data-stu-id="02615-118">Sets the group id to the provided value if possible.</span></span> <span data-ttu-id="02615-119">如果组 ID 正在使用中，则使用下一个可用的组 ID。</span><span class="sxs-lookup"><span data-stu-id="02615-119">If the group id is currently in use, the next available group id is used.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="02615-120">公共属性</span><span class="sxs-lookup"><span data-stu-id="02615-120">Common properties</span></span>

|<span data-ttu-id="02615-121">properties</span><span class="sxs-lookup"><span data-stu-id="02615-121">Property</span></span> |<span data-ttu-id="02615-122">说明</span><span class="sxs-lookup"><span data-stu-id="02615-122">Description</span></span> |
|---|---|
|<span data-ttu-id="02615-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="02615-123">DependsOn</span></span> |<span data-ttu-id="02615-124">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="02615-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="02615-125">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="02615-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="02615-126">Ensure</span><span class="sxs-lookup"><span data-stu-id="02615-126">Ensure</span></span> |<span data-ttu-id="02615-127">确定是否检查组是否存在。</span><span class="sxs-lookup"><span data-stu-id="02615-127">Determines whether to check if the group exists.</span></span> <span data-ttu-id="02615-128">将此属性设置为 **Present** 可确保组存在。</span><span class="sxs-lookup"><span data-stu-id="02615-128">Set this property to **Present** to ensure the group exists.</span></span> <span data-ttu-id="02615-129">将其设置为 **Absent** 可确保组不存在。</span><span class="sxs-lookup"><span data-stu-id="02615-129">Set it to **Absent** to ensure the group does not exist.</span></span> <span data-ttu-id="02615-130">默认值为 **Present** 。</span><span class="sxs-lookup"><span data-stu-id="02615-130">The default value is **Present** .</span></span> |

## <a name="example"></a><span data-ttu-id="02615-131">示例</span><span class="sxs-lookup"><span data-stu-id="02615-131">Example</span></span>

<span data-ttu-id="02615-132">下面的示例确保用户“monuser”存在，且为组“DBusers”的成员。</span><span class="sxs-lookup"><span data-stu-id="02615-132">The following example ensures that the user 'monuser' exists and is a member of the group 'DBusers'.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```
