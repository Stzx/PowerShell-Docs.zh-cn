---
ms.date: 09/20/2019
keywords: dsc,powershell,配置,安装程序
title: DSC WindowsProcess 资源
ms.openlocfilehash: 5c30af98bf7b99551396082630605c566a866697
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560485"
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="35f90-103">DSC WindowsProcess 资源</span><span class="sxs-lookup"><span data-stu-id="35f90-103">DSC WindowsProcess Resource</span></span>

> <span data-ttu-id="35f90-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="35f90-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="35f90-105">Windows PowerShell Desired State Configuration (DSC) 中的 **WindowsProcess** 资源提供了用于在目标节点上配置进程的机制。</span><span class="sxs-lookup"><span data-stu-id="35f90-105">The **WindowsProcess** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="35f90-106">语法</span><span class="sxs-lookup"><span data-stu-id="35f90-106">Syntax</span></span>

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="35f90-107">属性</span><span class="sxs-lookup"><span data-stu-id="35f90-107">Properties</span></span>

|<span data-ttu-id="35f90-108">properties</span><span class="sxs-lookup"><span data-stu-id="35f90-108">Property</span></span> |<span data-ttu-id="35f90-109">说明</span><span class="sxs-lookup"><span data-stu-id="35f90-109">Description</span></span> |
|---|---|
|<span data-ttu-id="35f90-110">参数</span><span class="sxs-lookup"><span data-stu-id="35f90-110">Arguments</span></span> |<span data-ttu-id="35f90-111">指示要原样传递到进程的参数字符串</span><span class="sxs-lookup"><span data-stu-id="35f90-111">Indicates a string of arguments to pass to the process as-is.</span></span> <span data-ttu-id="35f90-112">如果需要传递多个参数，请将它们全部放在此字符串中。</span><span class="sxs-lookup"><span data-stu-id="35f90-112">If you need to pass several arguments, put them all in this string.</span></span> |
|<span data-ttu-id="35f90-113">路径</span><span class="sxs-lookup"><span data-stu-id="35f90-113">Path</span></span> |<span data-ttu-id="35f90-114">进程可执行文件的路径。</span><span class="sxs-lookup"><span data-stu-id="35f90-114">The path to the process executable.</span></span> <span data-ttu-id="35f90-115">如果这是可执行文件的文件名（不是完全限定的路径），则 DSC 资源会搜索环境 `$env:Path` 变量以查找可执行文件。</span><span class="sxs-lookup"><span data-stu-id="35f90-115">If this the file name of the executable (not the fully qualified path), the DSC resource will search the environment `$env:Path` variable to find the executable file.</span></span> <span data-ttu-id="35f90-116">如果此属性的值是完全限定的路径，则 DSC 不使用 `$env:Path` 变量查找文件，并且会在不存在路径时引发错误。</span><span class="sxs-lookup"><span data-stu-id="35f90-116">If the value of this property is a fully qualified path, DSC will not use the `$env:Path` variable to find the file, and will throw an error if the path does not exist.</span></span> <span data-ttu-id="35f90-117">不允许使用相对路径。</span><span class="sxs-lookup"><span data-stu-id="35f90-117">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="35f90-118">凭据</span><span class="sxs-lookup"><span data-stu-id="35f90-118">Credential</span></span> |<span data-ttu-id="35f90-119">指示启动进程的凭据。</span><span class="sxs-lookup"><span data-stu-id="35f90-119">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="35f90-120">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="35f90-120">StandardErrorPath</span></span> |<span data-ttu-id="35f90-121">指示写入标准错误的目录路径。</span><span class="sxs-lookup"><span data-stu-id="35f90-121">Indicates the directory path to write the standard error.</span></span> <span data-ttu-id="35f90-122">将覆盖任何现有文件。</span><span class="sxs-lookup"><span data-stu-id="35f90-122">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="35f90-123">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="35f90-123">StandardInputPath</span></span> |<span data-ttu-id="35f90-124">指示标准输入位置。</span><span class="sxs-lookup"><span data-stu-id="35f90-124">Indicates the standard input location.</span></span> |
|<span data-ttu-id="35f90-125">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="35f90-125">StandardOutputPath</span></span> |<span data-ttu-id="35f90-126">指示写入标准输出的位置。</span><span class="sxs-lookup"><span data-stu-id="35f90-126">Indicates the location to write the standard output.</span></span> <span data-ttu-id="35f90-127">将覆盖任何现有文件。</span><span class="sxs-lookup"><span data-stu-id="35f90-127">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="35f90-128">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="35f90-128">WorkingDirectory</span></span> |<span data-ttu-id="35f90-129">指示将用作进程当前工作目录的位置。</span><span class="sxs-lookup"><span data-stu-id="35f90-129">Indicates the location that will be used as the current working directory for the process.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="35f90-130">公共属性</span><span class="sxs-lookup"><span data-stu-id="35f90-130">Common properties</span></span>

|<span data-ttu-id="35f90-131">properties</span><span class="sxs-lookup"><span data-stu-id="35f90-131">Property</span></span> |<span data-ttu-id="35f90-132">说明</span><span class="sxs-lookup"><span data-stu-id="35f90-132">Description</span></span> |
|---|---|
|<span data-ttu-id="35f90-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="35f90-133">DependsOn</span></span> |<span data-ttu-id="35f90-134">指示必须先运行其他资源的配置，再配置此资源。</span><span class="sxs-lookup"><span data-stu-id="35f90-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="35f90-135">例如，如果想要首先运行 ID 为 ResourceName、类型为 ResourceType 的资源配置脚本块，则使用此属性的语法为 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="35f90-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="35f90-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="35f90-136">Ensure</span></span> |<span data-ttu-id="35f90-137">指示进程是否存在。</span><span class="sxs-lookup"><span data-stu-id="35f90-137">Indicates if the process exists.</span></span> <span data-ttu-id="35f90-138">将此属性设置为 **Present** 可确保进程存在。</span><span class="sxs-lookup"><span data-stu-id="35f90-138">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="35f90-139">否则，将其设置为 **Absent**。</span><span class="sxs-lookup"><span data-stu-id="35f90-139">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="35f90-140">默认值为 **Present**。</span><span class="sxs-lookup"><span data-stu-id="35f90-140">The default value is **Present**.</span></span> |
|<span data-ttu-id="35f90-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="35f90-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="35f90-142">设置用于运行整个资源的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="35f90-142">Sets the credential for running the entire resource as.</span></span> |
