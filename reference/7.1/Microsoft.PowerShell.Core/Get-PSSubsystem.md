---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: ''
schema: 2.0.0
ms.openlocfilehash: 34998e7c4a6876821df949019970dc1d87297397
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200562"
---
# <span data-ttu-id="b3c44-101">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="b3c44-101">Get-PSSubsystem</span></span>

## <span data-ttu-id="b3c44-102">摘要</span><span class="sxs-lookup"><span data-stu-id="b3c44-102">SYNOPSIS</span></span>
<span data-ttu-id="b3c44-103">检索有关在 PowerShell 中注册的子系统的信息。</span><span class="sxs-lookup"><span data-stu-id="b3c44-103">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="b3c44-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3c44-104">SYNTAX</span></span>

### <span data-ttu-id="b3c44-105">GetAllSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="b3c44-105">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="b3c44-106">GetByKindSet</span><span class="sxs-lookup"><span data-stu-id="b3c44-106">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="b3c44-107">GetByTypeSet</span><span class="sxs-lookup"><span data-stu-id="b3c44-107">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="b3c44-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b3c44-108">DESCRIPTION</span></span>

<span data-ttu-id="b3c44-109">检索有关在 PowerShell 中注册的子系统的信息。</span><span class="sxs-lookup"><span data-stu-id="b3c44-109">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c44-110">这是一项实验性功能。</span><span class="sxs-lookup"><span data-stu-id="b3c44-110">This is an experimental feature.</span></span> <span data-ttu-id="b3c44-111">只有启用此功能时，此 cmdlet 才可用 `PSSubsystemPluginModel` 。</span><span class="sxs-lookup"><span data-stu-id="b3c44-111">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="b3c44-112">有关详细信息，请参阅 [使用实验性功能](/powershell/scripting/learn/experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="b3c44-112">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="b3c44-113">利用此功能，可以将 `System.Management.Automation.dll` 的组件分隔到驻留在自己的程序集中的各个子系统。</span><span class="sxs-lookup"><span data-stu-id="b3c44-113">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="b3c44-114">这种隔离可减少核心 PowerShell 引擎的磁盘占用，并支持这些组件成为最小 PowerShell 安装的可选功能。</span><span class="sxs-lookup"><span data-stu-id="b3c44-114">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="b3c44-115">目前仅支持 CommandPredictor 子系统。</span><span class="sxs-lookup"><span data-stu-id="b3c44-115">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="b3c44-116">该子系统与 PSReadLine 模块一起使用，以提供自定义预测插件。</span><span class="sxs-lookup"><span data-stu-id="b3c44-116">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="b3c44-117">将来  ，Job、CommandCompleter、Remoting 和其他组件可以分隔到 `System.Management.Automation.dll` 外的子系统程序集。</span><span class="sxs-lookup"><span data-stu-id="b3c44-117">In future, **Job** , **CommandCompleter** , **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="b3c44-118">示例</span><span class="sxs-lookup"><span data-stu-id="b3c44-118">EXAMPLES</span></span>

### <span data-ttu-id="b3c44-119">示例 1-显示所有可用子系统</span><span class="sxs-lookup"><span data-stu-id="b3c44-119">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="b3c44-120">示例 2-显示特定类型的所有可用子系统</span><span class="sxs-lookup"><span data-stu-id="b3c44-120">Example 2 - Display all available subsystems of a specific kind</span></span>

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## <span data-ttu-id="b3c44-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3c44-121">PARAMETERS</span></span>

### <span data-ttu-id="b3c44-122">-Kind</span><span class="sxs-lookup"><span data-stu-id="b3c44-122">-Kind</span></span>


<span data-ttu-id="b3c44-123">指定要返回的子系统的种类。</span><span class="sxs-lookup"><span data-stu-id="b3c44-123">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="b3c44-124">有效值为： `CommandPredictor` 。</span><span class="sxs-lookup"><span data-stu-id="b3c44-124">Valid values are: `CommandPredictor`.</span></span>

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c44-125">-SubsystemType</span><span class="sxs-lookup"><span data-stu-id="b3c44-125">-SubsystemType</span></span>

<span data-ttu-id="b3c44-126">指定要返回的子系统类型。</span><span class="sxs-lookup"><span data-stu-id="b3c44-126">Specifies the type of subsystem to be returned.</span></span>

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b3c44-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b3c44-127">CommonParameters</span></span>

<span data-ttu-id="b3c44-128">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b3c44-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3c44-129">有关详细信息，请参阅 [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b3c44-129">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3c44-130">输入</span><span class="sxs-lookup"><span data-stu-id="b3c44-130">INPUTS</span></span>

### <span data-ttu-id="b3c44-131">"SubsystemKind"。</span><span class="sxs-lookup"><span data-stu-id="b3c44-131">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="b3c44-132">System.Type</span><span class="sxs-lookup"><span data-stu-id="b3c44-132">System.Type</span></span>

## <span data-ttu-id="b3c44-133">输出</span><span class="sxs-lookup"><span data-stu-id="b3c44-133">OUTPUTS</span></span>

### <span data-ttu-id="b3c44-134">"SubsystemInfo"。</span><span class="sxs-lookup"><span data-stu-id="b3c44-134">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="b3c44-135">注释</span><span class="sxs-lookup"><span data-stu-id="b3c44-135">NOTES</span></span>

## <span data-ttu-id="b3c44-136">相关链接</span><span class="sxs-lookup"><span data-stu-id="b3c44-136">RELATED LINKS</span></span>

[<span data-ttu-id="b3c44-137">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="b3c44-137">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="b3c44-138">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b3c44-138">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="b3c44-139">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b3c44-139">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="b3c44-140">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="b3c44-140">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="b3c44-141">使用实验性功能</span><span class="sxs-lookup"><span data-stu-id="b3c44-141">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
