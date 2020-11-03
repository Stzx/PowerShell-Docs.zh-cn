---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=855965
Help Version: 6.2.5.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: c61d6278-02a3-4618-ae37-a524d40a7f44
Module Name: PSDiagnostics
ms.date: 11/27/2018
schema: 2.0.0
title: PSDiagnostics 模块
ms.openlocfilehash: 10bd2d740ce4b21b7e0867c870a55a01a94ee499
ms.sourcegitcommit: 3571b9e87e8881adbf7984cda46a63891039a987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2020
ms.locfileid: "93196801"
---
# <span data-ttu-id="d7cdf-103">PSDiagnostics 模块</span><span class="sxs-lookup"><span data-stu-id="d7cdf-103">PSDiagnostics Module</span></span>

## <span data-ttu-id="d7cdf-104">说明</span><span class="sxs-lookup"><span data-stu-id="d7cdf-104">Description</span></span>

<span data-ttu-id="d7cdf-105">PowerShell 诊断模块包含一组 cmdlet，可用于在 Windows 上的 PowerShell 中使用 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-105">The PowerShell Diagnostics Module contains a set of cmdlets that enables the use of ETW tracing in PowerShell on Windows.</span></span>

## <span data-ttu-id="d7cdf-106">PSDiagnostics Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7cdf-106">PSDiagnostics Cmdlets</span></span>

### [<span data-ttu-id="d7cdf-107">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-107">Disable-PSTrace</span></span>](Disable-PSTrace.md)
<span data-ttu-id="d7cdf-108">禁用 Microsoft Windows PowerShell 事件提供程序日志。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-108">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="d7cdf-109">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-109">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
<span data-ttu-id="d7cdf-110">停止通过 Enable-PSWSManCombinedTrace 启动的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-110">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

### [<span data-ttu-id="d7cdf-111">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-111">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
<span data-ttu-id="d7cdf-112">停止通过 Enable-WSManTrace 启动的 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-112">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

### [<span data-ttu-id="d7cdf-113">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-113">Enable-PSTrace</span></span>](Enable-PSTrace.md)
<span data-ttu-id="d7cdf-114">启用 Microsoft Windows PowerShell 事件提供程序日志。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-114">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="d7cdf-115">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-115">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
<span data-ttu-id="d7cdf-116">启用启用了 WSMan 和 PowerShell 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-116">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

### [<span data-ttu-id="d7cdf-117">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-117">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
<span data-ttu-id="d7cdf-118">启动启用了 WSMan 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-118">Start a logging session with the WSMan providers enabled.</span></span>

### [<span data-ttu-id="d7cdf-119">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d7cdf-119">Get-LogProperties</span></span>](Get-LogProperties.md)
<span data-ttu-id="d7cdf-120">检索 Windows 事件日志的属性。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-120">Retrieves the properties of a Windows event log.</span></span>

### [<span data-ttu-id="d7cdf-121">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d7cdf-121">Set-LogProperties</span></span>](Set-LogProperties.md)
<span data-ttu-id="d7cdf-122">更改 Windows 事件日志的属性。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-122">Changes the properties of a Windows event log.</span></span>

### [<span data-ttu-id="d7cdf-123">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-123">Start-Trace</span></span>](Start-Trace.md)
<span data-ttu-id="d7cdf-124">启动事件跟踪日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-124">Start an Event Trace logging session.</span></span>

### [<span data-ttu-id="d7cdf-125">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="d7cdf-125">Stop-Trace</span></span>](Stop-Trace.md)
<span data-ttu-id="d7cdf-126">停止事件跟踪日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-126">Stop an Event Trace logging session.</span></span>
