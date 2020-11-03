---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197846"
---
# <span data-ttu-id="0c003-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="0c003-103">Start-Sleep</span></span>

## <span data-ttu-id="0c003-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0c003-104">SYNOPSIS</span></span>
<span data-ttu-id="0c003-105">在指定的时间段内将脚本或会话中的活动挂起。</span><span class="sxs-lookup"><span data-stu-id="0c003-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="0c003-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0c003-106">SYNTAX</span></span>

### <span data-ttu-id="0c003-107">Seconds（默认值）</span><span class="sxs-lookup"><span data-stu-id="0c003-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="0c003-108">毫秒</span><span class="sxs-lookup"><span data-stu-id="0c003-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="0c003-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c003-109">DESCRIPTION</span></span>

<span data-ttu-id="0c003-110">`Start-Sleep`Cmdlet 将在指定的时间段内将脚本或会话中的活动挂起。</span><span class="sxs-lookup"><span data-stu-id="0c003-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span>
<span data-ttu-id="0c003-111">你可以使用它完成许多任务，例如等待操作完成或在重复操作之前暂停。</span><span class="sxs-lookup"><span data-stu-id="0c003-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="0c003-112">示例</span><span class="sxs-lookup"><span data-stu-id="0c003-112">EXAMPLES</span></span>

### <span data-ttu-id="0c003-113">示例1：为所有命令休眠15秒</span><span class="sxs-lookup"><span data-stu-id="0c003-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

<span data-ttu-id="0c003-114">此命令让会话中的所有命令休眠 15 秒。</span><span class="sxs-lookup"><span data-stu-id="0c003-114">This command makes all commands in the session sleep for 15 seconds.</span></span>

### <span data-ttu-id="0c003-115">示例2：睡眠所有命令</span><span class="sxs-lookup"><span data-stu-id="0c003-115">Example 2: Sleep all commands</span></span>

```powershell
Start-Sleep -m 500
```

<span data-ttu-id="0c003-116">此命令让会话中的所有命令休眠 1/2 秒（500 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="0c003-116">This command makes all the commands in the session sleep for one-half of a second (500 milliseconds).</span></span>

## <span data-ttu-id="0c003-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0c003-117">PARAMETERS</span></span>

### <span data-ttu-id="0c003-118">-Milliseconds</span><span class="sxs-lookup"><span data-stu-id="0c003-118">-Milliseconds</span></span>

<span data-ttu-id="0c003-119">指定资源休眠的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="0c003-119">Specifies how long the resource sleeps in milliseconds.</span></span>
<span data-ttu-id="0c003-120">该参数可以缩写为 **m** 。</span><span class="sxs-lookup"><span data-stu-id="0c003-120">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0c003-121">-Seconds</span><span class="sxs-lookup"><span data-stu-id="0c003-121">-Seconds</span></span>

<span data-ttu-id="0c003-122">指定资源休眠的时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="0c003-122">Specifies how long the resource sleeps in seconds.</span></span>
<span data-ttu-id="0c003-123">)  ( **秒** ，可以省略参数名称，也可以将其 **缩写为。**</span><span class="sxs-lookup"><span data-stu-id="0c003-123">You can omit the parameter name ( **Seconds** ), or you can abbreviate it as **s** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0c003-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0c003-124">CommonParameters</span></span>

<span data-ttu-id="0c003-125">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0c003-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0c003-126">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0c003-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0c003-127">输入</span><span class="sxs-lookup"><span data-stu-id="0c003-127">INPUTS</span></span>

### <span data-ttu-id="0c003-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="0c003-128">System.Int32</span></span>

<span data-ttu-id="0c003-129">可以通过管道将秒数传递给 `Start-Sleep` 。</span><span class="sxs-lookup"><span data-stu-id="0c003-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="0c003-130">输出</span><span class="sxs-lookup"><span data-stu-id="0c003-130">OUTPUTS</span></span>

### <span data-ttu-id="0c003-131">无</span><span class="sxs-lookup"><span data-stu-id="0c003-131">None</span></span>

<span data-ttu-id="0c003-132">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="0c003-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="0c003-133">注释</span><span class="sxs-lookup"><span data-stu-id="0c003-133">NOTES</span></span>

- <span data-ttu-id="0c003-134">还可以 `Start-Sleep` 通过其内置别名来引用 `sleep` 。</span><span class="sxs-lookup"><span data-stu-id="0c003-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="0c003-135">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="0c003-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="0c003-136">`Ctrl+C` 中断 `Start-Sleep` 。</span><span class="sxs-lookup"><span data-stu-id="0c003-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="0c003-137">`Ctrl+C` 不会中断 `[Threading.Thread]::Sleep` 。</span><span class="sxs-lookup"><span data-stu-id="0c003-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="0c003-138">有关详细信息，请参阅 [Thread 方法](/dotnet/api/system.threading.thread.sleep)。</span><span class="sxs-lookup"><span data-stu-id="0c003-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="0c003-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="0c003-139">RELATED LINKS</span></span>
