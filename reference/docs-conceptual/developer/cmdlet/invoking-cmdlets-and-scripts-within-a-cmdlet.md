---
ms.date: 09/13/2016
ms.topic: reference
title: 调用 Cmdlet 中的 Cmdlet 和脚本
description: 调用 Cmdlet 中的 Cmdlet 和脚本
ms.openlocfilehash: 246c61661f2d290e7e7ac62a8ad303b05bdc7582
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652650"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="ec471-103">调用 Cmdlet 中的 Cmdlet 和脚本</span><span class="sxs-lookup"><span data-stu-id="ec471-103">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="ec471-104">Cmdlet 可以从 cmdlet 的输入处理方法中调用其他 cmdlet 和脚本。</span><span class="sxs-lookup"><span data-stu-id="ec471-104">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="ec471-105">这样，便可以将现有 cmdlet 和脚本的功能添加到 cmdlet，而无需重写代码。</span><span class="sxs-lookup"><span data-stu-id="ec471-105">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="ec471-106">Invoke 方法</span><span class="sxs-lookup"><span data-stu-id="ec471-106">The Invoke Method</span></span>

<span data-ttu-id="ec471-107">所有 cmdlet 都可以通过从 cmdlet 重写的输入处理方法中调用[BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)方法来调用现有的 cmdlet，例如，该 cmdlet 会重写[此方法。](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)</span><span class="sxs-lookup"><span data-stu-id="ec471-107">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="ec471-108">但是，你只能调用直接从 [system.web](/dotnet/api/System.Management.Automation.Cmdlet) 类派生的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec471-108">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="ec471-109">不能调用派生自 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 类的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec471-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="ec471-110">" [System.object](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) " 方法具有以下变体。</span><span class="sxs-lookup"><span data-stu-id="ec471-110">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="ec471-111">。[调用](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)此变体将调用 Cmdlet 对象，并返回 "T" 类型对象的集合。</span><span class="sxs-lookup"><span data-stu-id="ec471-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="ec471-112">。[调用](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)此变体将调用 Cmdlet 对象并返回强类型化的 emumerator。</span><span class="sxs-lookup"><span data-stu-id="ec471-112">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="ec471-113">此变体允许用户使用集合中的对象执行自定义操作。</span><span class="sxs-lookup"><span data-stu-id="ec471-113">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="ec471-114">示例</span><span class="sxs-lookup"><span data-stu-id="ec471-114">Examples</span></span>

|<span data-ttu-id="ec471-115">示例</span><span class="sxs-lookup"><span data-stu-id="ec471-115">Example</span></span>|<span data-ttu-id="ec471-116">描述</span><span class="sxs-lookup"><span data-stu-id="ec471-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec471-117">在 Cmdlet 中调用 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ec471-117">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="ec471-118">此示例演示如何从另一个 cmdlet 中调用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec471-118">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="ec471-119">在 Cmdlet 中调用脚本</span><span class="sxs-lookup"><span data-stu-id="ec471-119">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="ec471-120">此示例演示如何从另一个 cmdlet 中调用提供给 cmdlet 的脚本。</span><span class="sxs-lookup"><span data-stu-id="ec471-120">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ec471-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec471-121">See Also</span></span>

[<span data-ttu-id="ec471-122">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ec471-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
