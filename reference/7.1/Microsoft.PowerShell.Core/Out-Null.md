---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: ff70c7dd5314fd1f123299e8f4ed14c70c7d7c9a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198785"
---
# <span data-ttu-id="0e2ff-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="0e2ff-103">Out-Null</span></span>

## <span data-ttu-id="0e2ff-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0e2ff-104">SYNOPSIS</span></span>
<span data-ttu-id="0e2ff-105">隐藏输出，而不是将其向下发送或显示。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="0e2ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e2ff-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="0e2ff-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e2ff-107">DESCRIPTION</span></span>

<span data-ttu-id="0e2ff-108">**Out** cmdlet 会将其输出发送到 null，实际上，将其从管道中删除并防止输出显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="0e2ff-109">示例</span><span class="sxs-lookup"><span data-stu-id="0e2ff-109">EXAMPLES</span></span>

### <span data-ttu-id="0e2ff-110">示例1：删除输出</span><span class="sxs-lookup"><span data-stu-id="0e2ff-110">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="0e2ff-111">此命令获取当前位置/目录中的项，但不会通过管道传递或在命令行中显示其输出。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-111">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="0e2ff-112">这对于隐藏不需要的输出很有用。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-112">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="0e2ff-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e2ff-113">PARAMETERS</span></span>

### <span data-ttu-id="0e2ff-114">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0e2ff-114">-InputObject</span></span>

<span data-ttu-id="0e2ff-115">指定从管道) 中删除 (要发送到 NULL 的对象。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-115">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="0e2ff-116">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-116">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0e2ff-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e2ff-117">CommonParameters</span></span>

<span data-ttu-id="0e2ff-118">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e2ff-119">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e2ff-120">输入</span><span class="sxs-lookup"><span data-stu-id="0e2ff-120">INPUTS</span></span>

### <span data-ttu-id="0e2ff-121">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0e2ff-121">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0e2ff-122">你可以通过管道将任何对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-122">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="0e2ff-123">输出</span><span class="sxs-lookup"><span data-stu-id="0e2ff-123">OUTPUTS</span></span>

### <span data-ttu-id="0e2ff-124">无</span><span class="sxs-lookup"><span data-stu-id="0e2ff-124">None</span></span>

<span data-ttu-id="0e2ff-125">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-125">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0e2ff-126">注释</span><span class="sxs-lookup"><span data-stu-id="0e2ff-126">NOTES</span></span>

* <span data-ttu-id="0e2ff-127"> ( **out** cmdlet) 包含 **out** 谓词的 cmdlet 没有用于名称或文件路径的参数。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-127">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="0e2ff-128">若要将数据发送到 **Out** cmdlet，请使用管道运算符 (|) 将 PowerShell 命令的输出发送到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-128">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="0e2ff-129">还可以将数据存储在变量中，并使用 *InputObject* 参数将数据传递给 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-129">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="0e2ff-130">有关详细信息，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-130">For more information, see the examples.</span></span>
* <span data-ttu-id="0e2ff-131">**Out-Null** 不返回任何输出对象。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-131">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="0e2ff-132">如果通过管道将 **Out-Null** 的输出传递给 Get-Member cmdlet，则 **Get-Member** 将报告未指定任何对象。</span><span class="sxs-lookup"><span data-stu-id="0e2ff-132">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="0e2ff-133">相关链接</span><span class="sxs-lookup"><span data-stu-id="0e2ff-133">RELATED LINKS</span></span>

[<span data-ttu-id="0e2ff-134">Out-Default</span><span class="sxs-lookup"><span data-stu-id="0e2ff-134">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="0e2ff-135">Out-Host</span><span class="sxs-lookup"><span data-stu-id="0e2ff-135">Out-Host</span></span>](Out-Host.md)

