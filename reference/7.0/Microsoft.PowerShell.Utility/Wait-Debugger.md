---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: f1488f65cf5ce48efe9d6459952653ff6570aa25
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196784"
---
# <span data-ttu-id="e8f8b-103">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="e8f8b-103">Wait-Debugger</span></span>

## <span data-ttu-id="e8f8b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e8f8b-104">SYNOPSIS</span></span>
<span data-ttu-id="e8f8b-105">在脚本中运行下一个语句之前，停止调试器中的脚本。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-105">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="e8f8b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8f8b-106">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="e8f8b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e8f8b-107">DESCRIPTION</span></span>

<span data-ttu-id="e8f8b-108">在 cmdlet 后的点处停止 PowerShell 脚本执行引擎 `Wait-Debugger` ，并等待附加调试器。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-108">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="e8f8b-109">这类似于 `Enable-RunspaceDebug -BreakAll` 在 DSC 资源中使用，但会在脚本中的特定点处中断。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-109">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="e8f8b-110">完成后，请确保删除 `Wait-Debugger` 行。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-110">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="e8f8b-111">当正在运行的脚本在处停止时，该脚本将会挂起 `Wait-Debugger` 。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-111">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="e8f8b-112">示例</span><span class="sxs-lookup"><span data-stu-id="e8f8b-112">EXAMPLES</span></span>

### <span data-ttu-id="e8f8b-113">示例1：插入断点以进行调试</span><span class="sxs-lookup"><span data-stu-id="e8f8b-113">Example 1: Insert breakpoint for debugging</span></span>

```
[DscResource()]
class FileResource
{
    [DscProperty(Key)]
    [string] $Path

    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    [DscProperty(Mandatory)]
    [string] $SourcePath

    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime


    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (! $fileExists)
            {
               $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    [bool] Test()
    {
        $present = Test-Path -LiteralPath $this.Path

        if ($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
        {
            return (! $present)
        }
    }

    [FileResource] Get()
    {
        $present = Test-Path -Path $this.Path

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }

        return $this
    }

    [void] CopyFile()
    {
        # Testing only - Remove before deployment!
        Wait-Debugger

        if (! (Test-Path -LiteralPath $this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose "Copying $($this.SourcePath) to $($this.Path)"

        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <span data-ttu-id="e8f8b-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8f8b-114">PARAMETERS</span></span>

### <span data-ttu-id="e8f8b-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e8f8b-115">CommonParameters</span></span>

<span data-ttu-id="e8f8b-116">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e8f8b-117">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f8b-117">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e8f8b-118">输入</span><span class="sxs-lookup"><span data-stu-id="e8f8b-118">INPUTS</span></span>

### <span data-ttu-id="e8f8b-119">无</span><span class="sxs-lookup"><span data-stu-id="e8f8b-119">None</span></span>

## <span data-ttu-id="e8f8b-120">输出</span><span class="sxs-lookup"><span data-stu-id="e8f8b-120">OUTPUTS</span></span>

### <span data-ttu-id="e8f8b-121">无</span><span class="sxs-lookup"><span data-stu-id="e8f8b-121">None</span></span>

## <span data-ttu-id="e8f8b-122">注释</span><span class="sxs-lookup"><span data-stu-id="e8f8b-122">NOTES</span></span>

## <span data-ttu-id="e8f8b-123">相关链接</span><span class="sxs-lookup"><span data-stu-id="e8f8b-123">RELATED LINKS</span></span>

[<span data-ttu-id="e8f8b-124">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="e8f8b-124">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
