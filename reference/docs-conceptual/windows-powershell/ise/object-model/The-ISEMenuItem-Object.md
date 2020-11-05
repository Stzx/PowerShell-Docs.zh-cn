---
ms.date: 12/31/2019
title: ISEMenuItem 对象
description: ISEMenuItem 对象是 Microsoft.PowerShell.Host.ISE.ISEMenuItem 类的实例。 “加载项”菜单上的所有菜单对象都是 ISEMenuItem 类的实例。
ms.openlocfilehash: 15036e3551687a21dfbe50834a89247c80949656
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663443"
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="0b2ce-104">ISEMenuItem 对象</span><span class="sxs-lookup"><span data-stu-id="0b2ce-104">The ISEMenuItem Object</span></span>

<span data-ttu-id="0b2ce-105">ISEMenuItem 对象是 Microsoft.PowerShell.Host.ISE.ISEMenuItem 类的实例。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-105">An **ISEMenuItem** object is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>
<span data-ttu-id="0b2ce-106">“ **加载项** ”菜单上的所有对象都是 **Microsoft.PowerShell.Host.ISE.ISEMenuItem** 类的实例。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-106">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="0b2ce-107">属性</span><span class="sxs-lookup"><span data-stu-id="0b2ce-107">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="0b2ce-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0b2ce-108">DisplayName</span></span>

<span data-ttu-id="0b2ce-109">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0b2ce-110">只读属性，可获取菜单项的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-110">The read-only property that gets the display name of the menu item.</span></span>

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a><span data-ttu-id="0b2ce-111">操作</span><span class="sxs-lookup"><span data-stu-id="0b2ce-111">Action</span></span>

<span data-ttu-id="0b2ce-112">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0b2ce-113">只读属性，可获取脚本块。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-113">The read-only property that gets the block of script.</span></span> <span data-ttu-id="0b2ce-114">单击菜单项时，它将调用该操作。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-114">It invokes the action when you click the menu item.</span></span>

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a><span data-ttu-id="0b2ce-115">快捷方式</span><span class="sxs-lookup"><span data-stu-id="0b2ce-115">Shortcut</span></span>

<span data-ttu-id="0b2ce-116">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0b2ce-117">只读属性，可获取菜单项的 Windows 输入键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-117">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a><span data-ttu-id="0b2ce-118">子菜单</span><span class="sxs-lookup"><span data-stu-id="0b2ce-118">Submenus</span></span>

<span data-ttu-id="0b2ce-119">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0b2ce-120">只读属性，可获取菜单项的[子菜单列表](The-ISEMenuItemCollection-Object.md)。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-120">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="0b2ce-121">脚本示例</span><span class="sxs-lookup"><span data-stu-id="0b2ce-121">Scripting example</span></span>

<span data-ttu-id="0b2ce-122">若要更好地了解加载项菜单及其可编写脚本属性的使用，请通读下面的脚本示例。</span><span class="sxs-lookup"><span data-stu-id="0b2ce-122">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

```powershell
# This is a scripting example that shows the use of the Add-ons menu.
# Clear the Add-ons menu if any entries currently exist
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()

# Add an Add-ons menu item with an shortcut and fast access key.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add('_Process', {Get-Process}, 'Alt+P')
# Add a nested menu - a parent and a child submenu item.
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('Parent', $null, $null)
$parentAdded.SubMenus.Add('_Dir', {dir}, 'Alt+D')
```

## <a name="see-also"></a><span data-ttu-id="0b2ce-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b2ce-123">See Also</span></span>

- [<span data-ttu-id="0b2ce-124">ISEMenuItemCollection 对象</span><span class="sxs-lookup"><span data-stu-id="0b2ce-124">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md)
- [<span data-ttu-id="0b2ce-125">Windows PowerShell ISE 脚本对象模型的用途</span><span class="sxs-lookup"><span data-stu-id="0b2ce-125">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="0b2ce-126">ISE 对象模型层次结构</span><span class="sxs-lookup"><span data-stu-id="0b2ce-126">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
