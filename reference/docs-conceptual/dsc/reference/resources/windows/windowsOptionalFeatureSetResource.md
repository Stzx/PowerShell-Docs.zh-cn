---
ms.date: 07/16/2020
keywords: dsc,powershell,配置,安装程序
title: DSC WindowsOptionalFeatureSet 资源
ms.openlocfilehash: e4f88f1cae6d7ddb3596ab4f27eb3766259f1a31
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464156"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="f64bb-103">DSC WindowsOptionalFeatureSet 资源</span><span class="sxs-lookup"><span data-stu-id="f64bb-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="f64bb-104">适用于：Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="f64bb-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="f64bb-105">Windows PowerShell Desired State Configuration (DSC) 中的 **WindowsOptionalFeatureSet** 资源提供了确保在目标节点上启用可选功能的机制。</span><span class="sxs-lookup"><span data-stu-id="f64bb-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="f64bb-106">此资源是[复合资源](../../../resources/authoringResourceComposite.md)，它会针对 **Name** 属性中指定的每个功能调用 [WindowsOptionalFeature 资源](windowsOptionalFeatureResource.md)。</span><span class="sxs-lookup"><span data-stu-id="f64bb-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="f64bb-107">要将一些 Windows 可选功能配置为相同状态时，请使用此资源。</span><span class="sxs-lookup"><span data-stu-id="f64bb-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="f64bb-108">语法</span><span class="sxs-lookup"><span data-stu-id="f64bb-108">Syntax</span></span>

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="f64bb-109">属性</span><span class="sxs-lookup"><span data-stu-id="f64bb-109">Properties</span></span>

|<span data-ttu-id="f64bb-110">properties</span><span class="sxs-lookup"><span data-stu-id="f64bb-110">Property</span></span> |<span data-ttu-id="f64bb-111">说明</span><span class="sxs-lookup"><span data-stu-id="f64bb-111">Description</span></span> |
|---|---|
|<span data-ttu-id="f64bb-112">名称</span><span class="sxs-lookup"><span data-stu-id="f64bb-112">Name</span></span> |<span data-ttu-id="f64bb-113">指示要确保启用或禁用的功能的名称。</span><span class="sxs-lookup"><span data-stu-id="f64bb-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span> |
|<span data-ttu-id="f64bb-114">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="f64bb-114">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="f64bb-115">指定 DISM 在搜索源文件以启用功能时是否联系 Windows 更新 (WU)。</span><span class="sxs-lookup"><span data-stu-id="f64bb-115">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="f64bb-116">如果为 `$true`，则 DISM 不联系 WU。</span><span class="sxs-lookup"><span data-stu-id="f64bb-116">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="f64bb-117">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="f64bb-117">RemoveFilesOnDisable</span></span> |<span data-ttu-id="f64bb-118">当 **Ensure** 设置为 **Absent** 时，设置为 `$true` 以删除与功能关联的所有文件。</span><span class="sxs-lookup"><span data-stu-id="f64bb-118">Set to `$true` to remove all files associated with the features when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="f64bb-119">LogLevel</span><span class="sxs-lookup"><span data-stu-id="f64bb-119">LogLevel</span></span> |<span data-ttu-id="f64bb-120">日志中显示的最大输出级别。</span><span class="sxs-lookup"><span data-stu-id="f64bb-120">The maximum output level shown in the logs.</span></span> <span data-ttu-id="f64bb-121">接受的值包括：**ErrorsOnly**、**ErrorsAndWarning** 和 **ErrorsAndWarningAndInformation**。</span><span class="sxs-lookup"><span data-stu-id="f64bb-121">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="f64bb-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="f64bb-122">LogPath</span></span> |<span data-ttu-id="f64bb-123">希望资源提供程序在其中记录操作的日志文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f64bb-123">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="f64bb-124">公共属性</span><span class="sxs-lookup"><span data-stu-id="f64bb-124">Common properties</span></span>

|<span data-ttu-id="f64bb-125">properties</span><span class="sxs-lookup"><span data-stu-id="f64bb-125">Property</span></span> |<span data-ttu-id="f64bb-126">说明</span><span class="sxs-lookup"><span data-stu-id="f64bb-126">Description</span></span> |
|---|---|
|<span data-ttu-id="f64bb-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="f64bb-127">DependsOn</span></span> |<span data-ttu-id="f64bb-128">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="f64bb-128">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="f64bb-129">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="f64bb-129">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="f64bb-130">Ensure</span><span class="sxs-lookup"><span data-stu-id="f64bb-130">Ensure</span></span> |<span data-ttu-id="f64bb-131">指定是否启用功能。</span><span class="sxs-lookup"><span data-stu-id="f64bb-131">Specifies whether the features are enabled.</span></span> <span data-ttu-id="f64bb-132">若要确保启用功能，请将此属性设置为 **Enable**。</span><span class="sxs-lookup"><span data-stu-id="f64bb-132">To ensure that the features are enabled, set this property to **Enable**.</span></span> <span data-ttu-id="f64bb-133">若要确保禁用功能，请将此属性设置为 **Disable**。</span><span class="sxs-lookup"><span data-stu-id="f64bb-133">To ensure that the features are disabled, set the property to **Disable**.</span></span> <span data-ttu-id="f64bb-134">默认值为 **Enable**。</span><span class="sxs-lookup"><span data-stu-id="f64bb-134">The default value is **Enable**.</span></span> |
|<span data-ttu-id="f64bb-135">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="f64bb-135">PsDscRunAsCredential</span></span> |<span data-ttu-id="f64bb-136">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="f64bb-136">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="f64bb-137">在 WMF 5.0 中添加了 **PsDscRunAsCredential** 公共属性，用于允许在其他凭据上下文中运行任何 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="f64bb-137">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="f64bb-138">有关详细信息，请参阅[将凭据与 DSC 资源配合使用](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="f64bb-138">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
