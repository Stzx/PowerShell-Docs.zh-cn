---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198031"
---
# <span data-ttu-id="e5ffa-103">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="e5ffa-103">Show-ControlPanelItem</span></span>

## <span data-ttu-id="e5ffa-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e5ffa-104">SYNOPSIS</span></span>
<span data-ttu-id="e5ffa-105">打开控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-105">Opens control panel items.</span></span>

## <span data-ttu-id="e5ffa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5ffa-106">SYNTAX</span></span>

### <span data-ttu-id="e5ffa-107">RegularName（默认值）</span><span class="sxs-lookup"><span data-stu-id="e5ffa-107">RegularName (Default)</span></span>

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="e5ffa-108">CanonicalName</span><span class="sxs-lookup"><span data-stu-id="e5ffa-108">CanonicalName</span></span>

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="e5ffa-109">Get-controlpanelitem</span><span class="sxs-lookup"><span data-stu-id="e5ffa-109">ControlPanelItem</span></span>

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## <span data-ttu-id="e5ffa-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5ffa-110">DESCRIPTION</span></span>

<span data-ttu-id="e5ffa-111">`Show-ControlPanelItem`Cmdlet 将在本地计算机上打开 "控制面板" 项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-111">The `Show-ControlPanelItem` cmdlet opens control panel items on the local computer.</span></span> <span data-ttu-id="e5ffa-112">可以使用它按名称、类别或描述打开控制面板项，即使在没有用户界面的系统上也是如此。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-112">You can use it to open control panel items by name, category, or description, even on systems that do not have a user interface.</span></span> <span data-ttu-id="e5ffa-113">你可以通过管道将控制面板项从 `Get-ControlPanelItem` cmdlet 发送到 `Show-ControlPanelItem` 。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-113">You can pipe control panel items from the `Get-ControlPanelItem` cmdlet to `Show-ControlPanelItem`.</span></span>

<span data-ttu-id="e5ffa-114">`Show-ControlPanelItem` 仅搜索可在系统上打开的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-114">`Show-ControlPanelItem` searches only control panel items that can be opened on the system.</span></span> <span data-ttu-id="e5ffa-115">在没有 " **控制面板** " 或 " **文件资源管理器** " 的计算机上， `Show-ControlPanelItem` 只会搜索可在不使用这些组件的情况下打开的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-115">On computers that do not have **Control Panel** or **File Explorer** , `Show-ControlPanelItem` searches only control panel items that can open without these components.</span></span>

<span data-ttu-id="e5ffa-116">此 cmdlet 是在 Windows PowerShell 3.0 中引入的，适用于 Windows 8、Windows Server 2012 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-116">This cmdlet was introduced in Windows PowerShell 3.0 and works on Windows 8, Windows Server 2012, and higher versions.</span></span>

## <span data-ttu-id="e5ffa-117">示例</span><span class="sxs-lookup"><span data-stu-id="e5ffa-117">EXAMPLES</span></span>

### <span data-ttu-id="e5ffa-118">示例1：显示控制面板项</span><span class="sxs-lookup"><span data-stu-id="e5ffa-118">Example 1: Show a control panel item</span></span>

<span data-ttu-id="e5ffa-119">此示例启动 " **自动播放** " 控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-119">This example launches the **AutoPlay** control panel item.</span></span>

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### <span data-ttu-id="e5ffa-120">示例2：通过管道将控制面板项传递给此 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5ffa-120">Example 2: Pipe a control panel item to this cmdlet</span></span>

<span data-ttu-id="e5ffa-121">此示例在本地计算机上打开 **Windows Defender 防火墙** 控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-121">This example opens the **Windows Defender Firewall** control panel item on the local computer.</span></span>
<span data-ttu-id="e5ffa-122">Windows 防火墙控制面板项的名称在 Windows 版本中已更改。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-122">The name of the Windows Firewall control panel item has changed over the versions of Windows.</span></span> <span data-ttu-id="e5ffa-123">此示例使用通配符模式查找控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-123">This example uses a wildcard pattern to find the control panel item.</span></span>

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="e5ffa-124">`Get-ControlPanelItem` 获取控制面板项并将 `Show-ControlPanelItem` 其打开。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-124">`Get-ControlPanelItem` gets the control panel item and the `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="e5ffa-125">示例 3：使用文件名打开控制面板项</span><span class="sxs-lookup"><span data-stu-id="e5ffa-125">Example 3: Use a file name to open a control panel item</span></span>

<span data-ttu-id="e5ffa-126">此示例通过使用 " **程序和功能** " 控制面板项的应用程序名称打开该面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-126">This example opens the **Programs and Features** control panel item by using its application name.</span></span>

```powershell
appwiz.cpl
```

<span data-ttu-id="e5ffa-127">此方法是使用命令的替代方法 `Show-ControlPanelItem` 。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-127">This method is an alternative to using a `Show-ControlPanelItem` command.</span></span>

> [!NOTE]
> <span data-ttu-id="e5ffa-128">在 PowerShell 中，可以省略控制面板文件的 cpl 文件扩展名，因为它包含在环境变量的值中。 `$env:PathExt`</span><span class="sxs-lookup"><span data-stu-id="e5ffa-128">In PowerShell, you can omit the .cpl file extension for control panel files because it's included in the value of the `$env:PathExt` environment variable.</span></span>

## <span data-ttu-id="e5ffa-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5ffa-129">PARAMETERS</span></span>

### <span data-ttu-id="e5ffa-130">-CanonicalName</span><span class="sxs-lookup"><span data-stu-id="e5ffa-130">-CanonicalName</span></span>

<span data-ttu-id="e5ffa-131">指定使用指定规范名称或名称模式的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-131">Specifies control panel items by using the specified canonical names or name patterns.</span></span> <span data-ttu-id="e5ffa-132">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-132">Wildcard characters are permitted.</span></span> <span data-ttu-id="e5ffa-133">如果输入多个名称，则此 cmdlet 将打开与任何名称匹配的控制面板项，就好像名称列表中的项由 **OR** 运算符分隔时。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-133">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

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

### <span data-ttu-id="e5ffa-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e5ffa-134">-InputObject</span></span>

<span data-ttu-id="e5ffa-135">通过提交控制面板项对象指定要打开的控制面板项。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-135">Specifies control panel items to open by submitting control panel item objects.</span></span> <span data-ttu-id="e5ffa-136">输入包含控制面板项对象的变量，或键入获取控制面板项对象的命令或表达式，例如 `Get-ControlPanelItem` 。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-136">Enter a variable that contains control panel item objects, or type a command or expression that gets control panel item objects, such as `Get-ControlPanelItem`.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e5ffa-137">-Name</span><span class="sxs-lookup"><span data-stu-id="e5ffa-137">-Name</span></span>

<span data-ttu-id="e5ffa-138">指定控制面板项的名称。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-138">Specifies names of control panel items.</span></span> <span data-ttu-id="e5ffa-139">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="e5ffa-140">如果输入多个名称，则此 cmdlet 将打开与任何名称匹配的控制面板项，就好像名称列表中的项由 **OR** 运算符分隔时。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-140">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="e5ffa-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e5ffa-141">CommonParameters</span></span>

<span data-ttu-id="e5ffa-142">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5ffa-143">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5ffa-144">输入</span><span class="sxs-lookup"><span data-stu-id="e5ffa-144">INPUTS</span></span>

### <span data-ttu-id="e5ffa-145">System.string、Get-controlpanelitem 的。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-145">System.String, Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="e5ffa-146">可以通过管道将名称或控制面板项对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-146">You can pipe a name or control panel item object to this cmdlet.</span></span>

## <span data-ttu-id="e5ffa-147">输出</span><span class="sxs-lookup"><span data-stu-id="e5ffa-147">OUTPUTS</span></span>

### <span data-ttu-id="e5ffa-148">无</span><span class="sxs-lookup"><span data-stu-id="e5ffa-148">None</span></span>

<span data-ttu-id="e5ffa-149">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="e5ffa-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="e5ffa-150">注释</span><span class="sxs-lookup"><span data-stu-id="e5ffa-150">NOTES</span></span>

## <span data-ttu-id="e5ffa-151">相关链接</span><span class="sxs-lookup"><span data-stu-id="e5ffa-151">RELATED LINKS</span></span>

[<span data-ttu-id="e5ffa-152">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="e5ffa-152">Get-ControlPanelItem</span></span>](Get-ControlPanelItem.md)
