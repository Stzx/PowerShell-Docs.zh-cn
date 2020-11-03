---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198032"
---
# <span data-ttu-id="502d2-103">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-103">Show-EventLog</span></span>

## <span data-ttu-id="502d2-104">摘要</span><span class="sxs-lookup"><span data-stu-id="502d2-104">SYNOPSIS</span></span>
<span data-ttu-id="502d2-105">在事件查看器中显示本地或远程计算机的事件日志。</span><span class="sxs-lookup"><span data-stu-id="502d2-105">Displays the event logs of the local or a remote computer in Event Viewer.</span></span>

## <span data-ttu-id="502d2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="502d2-106">SYNTAX</span></span>

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="502d2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="502d2-107">DESCRIPTION</span></span>
<span data-ttu-id="502d2-108">**Show-EventLog** cmdlet 在本地计算机上打开事件查看器，并在其中显示本地计算机或远程计算机上的所有经典事件日志。</span><span class="sxs-lookup"><span data-stu-id="502d2-108">The **Show-EventLog** cmdlet opens Event Viewer on the local computer and displays in it all of the classic event logs on the local computer or a remote computer.</span></span>

<span data-ttu-id="502d2-109">若要在 Windows Vista 和更高版本的 Windows 操作系统上打开事件查看器，当前用户必须是本地计算机上 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="502d2-109">To open Event Viewer on Windows Vista and later versions of the Windows operating system, the current user must be a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="502d2-110"> ( **eventlog** Cmdlet 包含 **eventlog** 名词的 cmdlet) 仅适用于经典事件日志。</span><span class="sxs-lookup"><span data-stu-id="502d2-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="502d2-111">若要从使用 windows Vista 和更高版本的 windows 操作系统中的 Windows 事件日志技术的日志中获取事件，请使用 Get-WinEvent cmdlet。</span><span class="sxs-lookup"><span data-stu-id="502d2-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="502d2-112">示例</span><span class="sxs-lookup"><span data-stu-id="502d2-112">EXAMPLES</span></span>

### <span data-ttu-id="502d2-113">示例1：显示本地计算机的事件日志</span><span class="sxs-lookup"><span data-stu-id="502d2-113">Example 1: Display event logs for the local computer</span></span>

```
PS C:\> Show-EventLog
```

<span data-ttu-id="502d2-114">此命令打开事件查看器并在其中显示本地计算机上的传统事件日志。</span><span class="sxs-lookup"><span data-stu-id="502d2-114">This command opens Event Viewer and displays in it the classic event logs on the local computer.</span></span>

### <span data-ttu-id="502d2-115">示例2：显示远程计算机的事件日志</span><span class="sxs-lookup"><span data-stu-id="502d2-115">Example 2: Display event logs for a remote computer</span></span>

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

<span data-ttu-id="502d2-116">此命令打开事件查看器并在其中显示计算机 Server01 上的传统事件日志。</span><span class="sxs-lookup"><span data-stu-id="502d2-116">This command opens Event Viewer and displays in it the classic event logs on the Server01 computer.</span></span>

## <span data-ttu-id="502d2-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="502d2-117">PARAMETERS</span></span>

### <span data-ttu-id="502d2-118">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="502d2-118">-ComputerName</span></span>
<span data-ttu-id="502d2-119">指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="502d2-119">Specifies a remote computer.</span></span>
<span data-ttu-id="502d2-120">**Show-EventLog** 显示来自本地计算机上事件查看器中指定计算机的事件日志。</span><span class="sxs-lookup"><span data-stu-id="502d2-120">**Show-EventLog** displays the event logs from the specified computer in Event Viewer on the local computer.</span></span>
<span data-ttu-id="502d2-121">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="502d2-121">The default is the local computer.</span></span>

<span data-ttu-id="502d2-122">键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="502d2-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="502d2-123">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="502d2-123">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="502d2-124">即使你的计算机未配置为运行远程命令，你也可以使用 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="502d2-124">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="502d2-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="502d2-125">CommonParameters</span></span>
<span data-ttu-id="502d2-126">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="502d2-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="502d2-127">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="502d2-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="502d2-128">输入</span><span class="sxs-lookup"><span data-stu-id="502d2-128">INPUTS</span></span>

### <span data-ttu-id="502d2-129">无</span><span class="sxs-lookup"><span data-stu-id="502d2-129">None</span></span>
<span data-ttu-id="502d2-130">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="502d2-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="502d2-131">输出</span><span class="sxs-lookup"><span data-stu-id="502d2-131">OUTPUTS</span></span>

### <span data-ttu-id="502d2-132">无</span><span class="sxs-lookup"><span data-stu-id="502d2-132">None</span></span>
<span data-ttu-id="502d2-133">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="502d2-133">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="502d2-134">注释</span><span class="sxs-lookup"><span data-stu-id="502d2-134">NOTES</span></span>

* <span data-ttu-id="502d2-135">Windows PowerShell 命令提示符在事件查看器打开后立即返回。</span><span class="sxs-lookup"><span data-stu-id="502d2-135">The Windows PowerShell command prompt returns as soon as Event Viewer opens.</span></span> <span data-ttu-id="502d2-136">当事件查看器处于打开状态时，你可以在当前会话中工作。</span><span class="sxs-lookup"><span data-stu-id="502d2-136">You can work in the current session while Event Viewer is open.</span></span>

  <span data-ttu-id="502d2-137">因为此 cmdlet 需要用户界面，所以它无法在 Windows Server 的 Server Core 安装上运行。</span><span class="sxs-lookup"><span data-stu-id="502d2-137">Because this cmdlet requires a user interface, it does not work on Server Core installations of Windows Server.</span></span>

*

## <span data-ttu-id="502d2-138">相关链接</span><span class="sxs-lookup"><span data-stu-id="502d2-138">RELATED LINKS</span></span>

[<span data-ttu-id="502d2-139">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-139">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="502d2-140">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-140">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="502d2-141">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-141">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="502d2-142">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-142">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="502d2-143">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-143">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="502d2-144">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="502d2-144">Write-EventLog</span></span>](Write-EventLog.md)
