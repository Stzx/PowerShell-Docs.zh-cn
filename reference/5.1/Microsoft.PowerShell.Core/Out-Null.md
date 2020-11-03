---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: 5a949629cdf0f0822866863822e82e70fc38d8c2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197641"
---
# <span data-ttu-id="7dcf1-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="7dcf1-103">Out-Null</span></span>

## <span data-ttu-id="7dcf1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7dcf1-104">SYNOPSIS</span></span>
<span data-ttu-id="7dcf1-105">隐藏输出，而不是将其向下发送或显示。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="7dcf1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7dcf1-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="7dcf1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7dcf1-107">DESCRIPTION</span></span>
<span data-ttu-id="7dcf1-108">**Out** cmdlet 会将其输出发送到 null，实际上，将其从管道中删除并防止输出显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span> <span data-ttu-id="7dcf1-109">这只会影响标准输出流。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-109">This only affects the standard output stream.</span></span>
<span data-ttu-id="7dcf1-110">其他输出流（如错误流）不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-110">Other output streams, like the Error stream are not affected.</span></span> <span data-ttu-id="7dcf1-111">将显示异常。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-111">Exceptions will be displayed.</span></span> <span data-ttu-id="7dcf1-112">这样，就可以更轻松地测试命令中的任何错误。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-112">This makes it easier to test your command for any errors.</span></span>

## <span data-ttu-id="7dcf1-113">示例</span><span class="sxs-lookup"><span data-stu-id="7dcf1-113">EXAMPLES</span></span>

### <span data-ttu-id="7dcf1-114">示例1：删除输出</span><span class="sxs-lookup"><span data-stu-id="7dcf1-114">Example 1: Delete output</span></span>

```
PS C:\> Get-ChildItem | Out-Null
```

<span data-ttu-id="7dcf1-115">此命令获取当前位置/目录中的项，但不会通过管道传递或在命令行中显示其输出。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-115">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="7dcf1-116">这对于隐藏不需要的输出很有用。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-116">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="7dcf1-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7dcf1-117">PARAMETERS</span></span>

### <span data-ttu-id="7dcf1-118">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7dcf1-118">-InputObject</span></span>
<span data-ttu-id="7dcf1-119">指定从管道) 中删除 (要发送到 NULL 的对象。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-119">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="7dcf1-120">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-120">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7dcf1-121">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7dcf1-121">CommonParameters</span></span>
<span data-ttu-id="7dcf1-122">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7dcf1-123">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7dcf1-124">输入</span><span class="sxs-lookup"><span data-stu-id="7dcf1-124">INPUTS</span></span>

### <span data-ttu-id="7dcf1-125">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="7dcf1-125">System.Management.Automation.PSObject</span></span>
<span data-ttu-id="7dcf1-126">你可以通过管道将任何对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-126">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="7dcf1-127">输出</span><span class="sxs-lookup"><span data-stu-id="7dcf1-127">OUTPUTS</span></span>

### <span data-ttu-id="7dcf1-128">无</span><span class="sxs-lookup"><span data-stu-id="7dcf1-128">None</span></span>
<span data-ttu-id="7dcf1-129">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-129">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7dcf1-130">注释</span><span class="sxs-lookup"><span data-stu-id="7dcf1-130">NOTES</span></span>

* <span data-ttu-id="7dcf1-131"> ( **out** cmdlet) 包含 **out** 谓词的 cmdlet 没有用于名称或文件路径的参数。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-131">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="7dcf1-132">若要将数据发送到 **Out** cmdlet，请使用管道运算符 (|) 将 Windows PowerShell 命令的输出发送到该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-132">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a Windows PowerShell command to the cmdlet.</span></span> <span data-ttu-id="7dcf1-133">还可以将数据存储在变量中，并使用 *InputObject* 参数将数据传递给 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-133">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="7dcf1-134">有关详细信息，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-134">For more information, see the examples.</span></span>
* <span data-ttu-id="7dcf1-135">**Out-Null** 不返回任何输出对象。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-135">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="7dcf1-136">如果通过管道将 **Out-Null** 的输出传递给 Get-Member cmdlet，则 **Get-Member** 将报告未指定任何对象。</span><span class="sxs-lookup"><span data-stu-id="7dcf1-136">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="7dcf1-137">相关链接</span><span class="sxs-lookup"><span data-stu-id="7dcf1-137">RELATED LINKS</span></span>

[<span data-ttu-id="7dcf1-138">Out-Default</span><span class="sxs-lookup"><span data-stu-id="7dcf1-138">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="7dcf1-139">Out-Host</span><span class="sxs-lookup"><span data-stu-id="7dcf1-139">Out-Host</span></span>](Out-Host.md)
