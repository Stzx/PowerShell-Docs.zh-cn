---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: 使用打印机
description: 本文介绍如何使用 WMI 对象和 COM 接口在 Windows 中管理打印机。
ms.openlocfilehash: 2606753783043eeae8e9d461e56f0901149cb8e3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501076"
---
# <a name="working-with-printers-in-windows"></a><span data-ttu-id="5ab7c-104">在 Windows 中使用打印机</span><span class="sxs-lookup"><span data-stu-id="5ab7c-104">Working with Printers in Windows</span></span>

<span data-ttu-id="5ab7c-105">你可以通过 PowerShell 使用 WMI 和 WSH 中的 WScript.Network  COM 对象来管理打印机。</span><span class="sxs-lookup"><span data-stu-id="5ab7c-105">You can use PowerShell to manage printers by using WMI and the **WScript.Network** COM object from WSH.</span></span> <span data-ttu-id="5ab7c-106">我们将结合这两种工具来演示特定任务。</span><span class="sxs-lookup"><span data-stu-id="5ab7c-106">We will use a mix of both tools to demonstrate specific tasks.</span></span>

## <a name="listing-printer-connections"></a><span data-ttu-id="5ab7c-107">列出打印机连接</span><span class="sxs-lookup"><span data-stu-id="5ab7c-107">Listing Printer Connections</span></span>

<span data-ttu-id="5ab7c-108">列出计算机上安装的打印机的最简单方法是使用 WMI **Win32_Printer** 类：</span><span class="sxs-lookup"><span data-stu-id="5ab7c-108">The simplest way to list the printers installed on a computer is to use the WMI **Win32_Printer** class:</span></span>

```powershell
Get-CimInstance -Class Win32_Printer
```

<span data-ttu-id="5ab7c-109">此外还可以通过使用通常在 WSH 脚本中使用的 **WScript.Network** COM 对象列出打印机：</span><span class="sxs-lookup"><span data-stu-id="5ab7c-109">You can also list the printers by using the **WScript.Network** COM object that is typically used in WSH scripts:</span></span>

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

<span data-ttu-id="5ab7c-110">由于此命令返回的端口名和打印机设备名的简单字符串集合没有任何可以区分的标签，因此并不容易解释。</span><span class="sxs-lookup"><span data-stu-id="5ab7c-110">Because this command returns a simple string collection of port names and printer device names without any distinguishing labels, it is not easy to interpret.</span></span>

## <a name="adding-a-network-printer"></a><span data-ttu-id="5ab7c-111">添加网络打印机</span><span class="sxs-lookup"><span data-stu-id="5ab7c-111">Adding a Network Printer</span></span>

<span data-ttu-id="5ab7c-112">若要添加新的网络打印机，请使用 **WScript.Network** ：</span><span class="sxs-lookup"><span data-stu-id="5ab7c-112">To add a new network printer, use **WScript.Network** :</span></span>

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a><span data-ttu-id="5ab7c-113">设置默认打印机</span><span class="sxs-lookup"><span data-stu-id="5ab7c-113">Setting a Default Printer</span></span>

<span data-ttu-id="5ab7c-114">若要使用 WMI 设置默认打印机，请在 **Win32_Printer** 集合中查找打印机，然后调用 **SetDefaultPrinter** 方法：</span><span class="sxs-lookup"><span data-stu-id="5ab7c-114">To use WMI to set the default printer, find the printer in the **Win32_Printer** collection and then invoke the **SetDefaultPrinter** method:</span></span>

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

<span data-ttu-id="5ab7c-115">**WScript.Network** 使用起来要简单一些，因为它具有 **SetDefaultPrinter** 方法，该方法仅将打印机名称作为参数：</span><span class="sxs-lookup"><span data-stu-id="5ab7c-115">**WScript.Network** is a little simpler to use, because it has a **SetDefaultPrinter** method that takes only the printer name as an argument:</span></span>

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a><span data-ttu-id="5ab7c-116">删除打印机连接</span><span class="sxs-lookup"><span data-stu-id="5ab7c-116">Removing a Printer Connection</span></span>

<span data-ttu-id="5ab7c-117">若要删除打印机连接，请使用 **WScript.Network RemovePrinterConnection** 方法：</span><span class="sxs-lookup"><span data-stu-id="5ab7c-117">To remove a printer connection, use the **WScript.Network RemovePrinterConnection** method:</span></span>

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
