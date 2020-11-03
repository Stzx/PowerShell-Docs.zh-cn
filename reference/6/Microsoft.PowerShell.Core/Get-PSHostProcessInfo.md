---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 24ebb507b2f9544115d6309b0a91d8b19b0745ec
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198458"
---
# <span data-ttu-id="32b41-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="32b41-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="32b41-104">摘要</span><span class="sxs-lookup"><span data-stu-id="32b41-104">SYNOPSIS</span></span>
<span data-ttu-id="32b41-105">获取有关 PowerShell 主机的进程信息。</span><span class="sxs-lookup"><span data-stu-id="32b41-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="32b41-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32b41-106">SYNTAX</span></span>

### <span data-ttu-id="32b41-107">ProcessNameParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="32b41-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="32b41-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="32b41-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="32b41-109">ProcessIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="32b41-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="32b41-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32b41-110">DESCRIPTION</span></span>

<span data-ttu-id="32b41-111">`Get-PSHostProcessInfo`Cmdlet 获取有关在本地计算机上运行的 PowerShell 主机进程的信息。</span><span class="sxs-lookup"><span data-stu-id="32b41-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="32b41-112">从 PowerShell 6.2 开始，非 Windows 平台上支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32b41-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="32b41-113">示例</span><span class="sxs-lookup"><span data-stu-id="32b41-113">EXAMPLES</span></span>

### <span data-ttu-id="32b41-114">1：获取在系统上运行的 PowerShell 主机的列表</span><span class="sxs-lookup"><span data-stu-id="32b41-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="32b41-115">2：获取特定进程名称的 PowerShell 主机信息</span><span class="sxs-lookup"><span data-stu-id="32b41-115">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="32b41-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32b41-116">PARAMETERS</span></span>

### <span data-ttu-id="32b41-117">-Id</span><span class="sxs-lookup"><span data-stu-id="32b41-117">-Id</span></span>

<span data-ttu-id="32b41-118">按进程 ID 指定进程。</span><span class="sxs-lookup"><span data-stu-id="32b41-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="32b41-119">若要获取进程 ID，请运行 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32b41-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32b41-120">-Name</span><span class="sxs-lookup"><span data-stu-id="32b41-120">-Name</span></span>

<span data-ttu-id="32b41-121">按进程名称指定进程。</span><span class="sxs-lookup"><span data-stu-id="32b41-121">Specifies a process by the process name.</span></span> <span data-ttu-id="32b41-122">若要获取进程名称，请运行 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32b41-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32b41-123">-Process</span><span class="sxs-lookup"><span data-stu-id="32b41-123">-Process</span></span>

<span data-ttu-id="32b41-124">按进程对象指定进程。</span><span class="sxs-lookup"><span data-stu-id="32b41-124">Specifies a process by the process object.</span></span> <span data-ttu-id="32b41-125">使用此参数的最简单方法是 `Get-Process` ：保存返回要在变量中输入的进程的命令的结果，然后将该变量指定为此参数的值。</span><span class="sxs-lookup"><span data-stu-id="32b41-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="32b41-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32b41-126">CommonParameters</span></span>

<span data-ttu-id="32b41-127">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="32b41-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32b41-128">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="32b41-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32b41-129">输入</span><span class="sxs-lookup"><span data-stu-id="32b41-129">INPUTS</span></span>

### <span data-ttu-id="32b41-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="32b41-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="32b41-131">可以通过管道将 **进程** 对象传递 `Get-Process` 给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32b41-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="32b41-132">输出</span><span class="sxs-lookup"><span data-stu-id="32b41-132">OUTPUTS</span></span>

### <span data-ttu-id="32b41-133">Get-pshostprocessinfo。</span><span class="sxs-lookup"><span data-stu-id="32b41-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="32b41-134">注释</span><span class="sxs-lookup"><span data-stu-id="32b41-134">NOTES</span></span>

## <span data-ttu-id="32b41-135">相关链接</span><span class="sxs-lookup"><span data-stu-id="32b41-135">RELATED LINKS</span></span>

[<span data-ttu-id="32b41-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="32b41-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)
