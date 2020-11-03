---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198299"
---
# <span data-ttu-id="fbae4-103">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="fbae4-103">Get-ControlPanelItem</span></span>

## <span data-ttu-id="fbae4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fbae4-104">SYNOPSIS</span></span>
<span data-ttu-id="fbae4-105">获取控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-105">Gets control panel items.</span></span>

## <span data-ttu-id="fbae4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbae4-106">SYNTAX</span></span>

### <span data-ttu-id="fbae4-107">RegularName（默认值）</span><span class="sxs-lookup"><span data-stu-id="fbae4-107">RegularName (Default)</span></span>

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="fbae4-108">CanonicalName</span><span class="sxs-lookup"><span data-stu-id="fbae4-108">CanonicalName</span></span>

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="fbae4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbae4-109">DESCRIPTION</span></span>

<span data-ttu-id="fbae4-110">`Get-ControlPanelItem`Cmdlet 将获取本地计算机上的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-110">The `Get-ControlPanelItem` cmdlet gets control panel items on the local computer.</span></span> <span data-ttu-id="fbae4-111">你可以将其用于按名称、类别或描述查找控制面板项，即使在没有用户界面的系统上也可以如此。</span><span class="sxs-lookup"><span data-stu-id="fbae4-111">You can use it to find control panel items by name, category, or description, even on systems that do not have a user interface.</span></span>

<span data-ttu-id="fbae4-112">此 cmdlet 仅获取可在系统上打开的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-112">This cmdlet gets only the control panel items that can be opened on the system.</span></span> <span data-ttu-id="fbae4-113">在没有 "控制面板" 或 "文件资源管理器" 的计算机上，此 cmdlet 仅获取可以在不使用这些组件的情况下打开的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-113">On computers that do not have Control Panel or File Explorer, this cmdlet gets only control panel items that can open without these components.</span></span>

<span data-ttu-id="fbae4-114">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fbae4-114">This cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="fbae4-115">它仅适用于 Windows 8 和 Windows Server 2012 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="fbae4-115">It works only on Windows 8 and Windows Server 2012 and newer.</span></span>

## <span data-ttu-id="fbae4-116">示例</span><span class="sxs-lookup"><span data-stu-id="fbae4-116">EXAMPLES</span></span>

### <span data-ttu-id="fbae4-117">示例 1：获取所有控制面板项</span><span class="sxs-lookup"><span data-stu-id="fbae4-117">Example 1: Get all control panel items</span></span>

<span data-ttu-id="fbae4-118">此命令获取本地计算机上的所有控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-118">This command gets all control panel items on the local computer.</span></span>

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### <span data-ttu-id="fbae4-119">示例 2：按名称获取控制面板项</span><span class="sxs-lookup"><span data-stu-id="fbae4-119">Example 2: Get control panel items by name</span></span>

<span data-ttu-id="fbae4-120">此示例获取名称中包含程序或应用程序的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-120">This example gets control panel items that have Program or App in their names.</span></span>

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### <span data-ttu-id="fbae4-121">示例 3：按类别获取控制面板项</span><span class="sxs-lookup"><span data-stu-id="fbae4-121">Example 3: Get control panel items by category</span></span>

<span data-ttu-id="fbae4-122">此命令获取其名称中具有安全性的类别中的所有控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-122">This command gets all control panel items in categories that have Security in their names.</span></span>

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### <span data-ttu-id="fbae4-123">示例 4：打开控制面板项</span><span class="sxs-lookup"><span data-stu-id="fbae4-123">Example 4: Open a control panel item</span></span>

<span data-ttu-id="fbae4-124">此示例在本地计算机上打开 "Windows 防火墙" 控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-124">This example opens the Windows Firewall control panel item on the local computer.</span></span>

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="fbae4-125">`Get-ControlPanelItem`Cmdlet 将获取控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-125">The `Get-ControlPanelItem` cmdlet gets the control panel item.</span></span> <span data-ttu-id="fbae4-126">`Show-ControlPanelItem`Cmdlet 将打开它。</span><span class="sxs-lookup"><span data-stu-id="fbae4-126">The `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="fbae4-127">示例 5：获取远程计算机上的控制面板项</span><span class="sxs-lookup"><span data-stu-id="fbae4-127">Example 5: Get control panel items on a remote computer</span></span>

<span data-ttu-id="fbae4-128">此示例将获取 Server01 远程计算机上的 BitLocker 驱动器加密控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-128">This example gets the BitLocker Drive Encryption control panel item on the Server01 remote computer.</span></span>
<span data-ttu-id="fbae4-129">`Invoke-Command`Cmdlet 以 `Get-ControlPanelItem` 远程方式运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fbae4-129">The `Invoke-Command` cmdlet runs the `Get-ControlPanelItem` cmdlet remotely.</span></span>

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### <span data-ttu-id="fbae4-130">示例 6：搜索控制面板项的描述</span><span class="sxs-lookup"><span data-stu-id="fbae4-130">Example 6: Search the descriptions of control panel items</span></span>

<span data-ttu-id="fbae4-131">此示例将搜索 "控制面板" 项的 " **说明** " 属性，以仅获取包含名称 **设备** 的那些项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-131">This example searches the **Description** property of the control panel items to get only those that contain the name **Device** .</span></span>

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

<span data-ttu-id="fbae4-132">`Get-ControlPanelItem`Cmdlet 将获取所有控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-132">The `Get-ControlPanelItem` cmdlet gets all control panel items.</span></span> <span data-ttu-id="fbae4-133">`Where-Object`Cmdlet 按 **Description** 属性的值筛选这些项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-133">The `Where-Object` cmdlet filters the items by the value of the **Description** property.</span></span>

## <span data-ttu-id="fbae4-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbae4-134">PARAMETERS</span></span>

### <span data-ttu-id="fbae4-135">-CanonicalName</span><span class="sxs-lookup"><span data-stu-id="fbae4-135">-CanonicalName</span></span>

<span data-ttu-id="fbae4-136">按照此 cmdlet 获取的规范名称或名称模式，将控制面板项指定为字符串数组。</span><span class="sxs-lookup"><span data-stu-id="fbae4-136">Specifies, as a string array, the control panel items by their canonical names or name patterns that this cmdlet gets.</span></span> <span data-ttu-id="fbae4-137">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="fbae4-137">Wildcards are permitted.</span></span> <span data-ttu-id="fbae4-138">如果输入多个名称，则此 cmdlet 将获取与任何名称匹配的控制面板项，如同名称列表中的项由 "or" 运算符分隔时。</span><span class="sxs-lookup"><span data-stu-id="fbae4-138">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span>

<span data-ttu-id="fbae4-139">默认情况下，此 cmdlet 将获取系统中的所有控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-139">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="fbae4-140">-Category</span><span class="sxs-lookup"><span data-stu-id="fbae4-140">-Category</span></span>

<span data-ttu-id="fbae4-141">指定为字符串数组，此 cmdlet 获取的指定类别中的控制面板项的类别。</span><span class="sxs-lookup"><span data-stu-id="fbae4-141">Specifies, as a string array, the categories of the control panel items in the specified categories that this cmdlet gets.</span></span> <span data-ttu-id="fbae4-142">输入一个类别名称或名称模式。</span><span class="sxs-lookup"><span data-stu-id="fbae4-142">Enter a category name or name pattern.</span></span> <span data-ttu-id="fbae4-143">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="fbae4-143">Wildcards are permitted.</span></span> <span data-ttu-id="fbae4-144">如果输入多个名称，则此 cmdlet 将获取与任何名称匹配的控制面板项，如同名称列表中的项由 "or" 运算符分隔时。</span><span class="sxs-lookup"><span data-stu-id="fbae4-144">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span> <span data-ttu-id="fbae4-145">默认情况下，此 cmdlet 将获取系统中的所有控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-145">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="fbae4-146">-Name</span><span class="sxs-lookup"><span data-stu-id="fbae4-146">-Name</span></span>

<span data-ttu-id="fbae4-147">以字符串数组的形式指定此 cmdlet 获取的控制面板的名称或名称模式。</span><span class="sxs-lookup"><span data-stu-id="fbae4-147">Specifies, as a string array, the names or name patterns of the control panel that this cmdlet gets.</span></span>
<span data-ttu-id="fbae4-148">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="fbae4-148">Wildcards are permitted.</span></span> <span data-ttu-id="fbae4-149">还可以通过管道将名称或名称模式传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fbae4-149">You can also pipe a name or name pattern to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="fbae4-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fbae4-150">CommonParameters</span></span>

<span data-ttu-id="fbae4-151">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fbae4-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbae4-152">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fbae4-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbae4-153">输入</span><span class="sxs-lookup"><span data-stu-id="fbae4-153">INPUTS</span></span>

### <span data-ttu-id="fbae4-154">System.String</span><span class="sxs-lookup"><span data-stu-id="fbae4-154">System.String</span></span>

<span data-ttu-id="fbae4-155">可以通过管道将名称或名称模式传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fbae4-155">You can pipe a name or name pattern to this cmdlet.</span></span>

## <span data-ttu-id="fbae4-156">输出</span><span class="sxs-lookup"><span data-stu-id="fbae4-156">OUTPUTS</span></span>

### <span data-ttu-id="fbae4-157">Microsoft.PowerShell.Commands.ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="fbae4-157">Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="fbae4-158">此 cmdlet 将获取本地计算机上的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="fbae4-158">This cmdlet gets control panel items on the local computer.</span></span>

## <span data-ttu-id="fbae4-159">注释</span><span class="sxs-lookup"><span data-stu-id="fbae4-159">NOTES</span></span>

## <span data-ttu-id="fbae4-160">相关链接</span><span class="sxs-lookup"><span data-stu-id="fbae4-160">RELATED LINKS</span></span>

[<span data-ttu-id="fbae4-161">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="fbae4-161">Show-ControlPanelItem</span></span>](Show-ControlPanelItem.md)
