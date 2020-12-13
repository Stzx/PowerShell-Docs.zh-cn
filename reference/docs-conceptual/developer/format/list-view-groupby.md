---
ms.date: 09/13/2016
ms.topic: reference
title: 列表视图 (GroupBy)
description: 列表视图 (GroupBy)
ms.openlocfilehash: e039c38d1e4e93f65a508fe60aaaf35c64ebe2ed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666614"
---
# <a name="list-view-groupby"></a><span data-ttu-id="69ab1-103">列表视图 (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="69ab1-103">List View (GroupBy)</span></span>

<span data-ttu-id="69ab1-104">此示例演示如何实现将列表行分为多个组的列表视图。</span><span class="sxs-lookup"><span data-stu-id="69ab1-104">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="69ab1-105">此列表视图显示 [system.serviceprocess. Servicecontroller 的属性？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 由 [get-help](/powershell/module/Microsoft.PowerShell.Management/Get-Service) Cmdlet 返回的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="69ab1-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="69ab1-106">有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="69ab1-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="69ab1-107">加载此格式设置文件</span><span class="sxs-lookup"><span data-stu-id="69ab1-107">To load this formatting file</span></span>

1. <span data-ttu-id="69ab1-108">将本主题的 "示例" 部分中的 XML 复制到一个文本文件中。</span><span class="sxs-lookup"><span data-stu-id="69ab1-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="69ab1-109">保存文本文件。</span><span class="sxs-lookup"><span data-stu-id="69ab1-109">Save the text file.</span></span> <span data-ttu-id="69ab1-110">请确保将扩展名添加 `format.ps1xml` 到文件，以将其标识为格式化文件。</span><span class="sxs-lookup"><span data-stu-id="69ab1-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="69ab1-111">打开 Windows PowerShell 并运行以下命令，将格式化文件加载到当前会话中： `Update-formatdata -prependpath PathToFormattingFile` 。</span><span class="sxs-lookup"><span data-stu-id="69ab1-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="69ab1-112">此格式化文件定义已由 Windows PowerShell 格式设置文件定义的对象的显示。</span><span class="sxs-lookup"><span data-stu-id="69ab1-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="69ab1-113">在 `prependPath` 运行 cmdlet 时，必须使用参数，并且不能将此格式化文件作为模块加载。</span><span class="sxs-lookup"><span data-stu-id="69ab1-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="69ab1-114">演示</span><span class="sxs-lookup"><span data-stu-id="69ab1-114">Demonstrates</span></span>

<span data-ttu-id="69ab1-115">此格式化文件演示了以下 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="69ab1-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="69ab1-116">视图的 [名称](./name-element-for-view-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="69ab1-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="69ab1-117">定义视图要显示的对象的 [ViewSelectedBy](./viewselectedby-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="69ab1-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="69ab1-118">定义新的对象组显示方式的 [GroupBy](./viewselectedby-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="69ab1-118">The [GroupBy](./viewselectedby-element-format.md) element that defines how a new group of objects is displayed.</span></span>

- <span data-ttu-id="69ab1-119">定义视图显示的属性的 [ListControl](./listcontrol-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="69ab1-119">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="69ab1-120">定义在列表视图的行中显示的[内容的包含项元素。](./listitem-element-for-listitems-for-listcontrol-format.md)</span><span class="sxs-lookup"><span data-stu-id="69ab1-120">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="69ab1-121">定义要显示的属性的 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="69ab1-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="69ab1-122">示例</span><span class="sxs-lookup"><span data-stu-id="69ab1-122">Example</span></span>

<span data-ttu-id="69ab1-123">下面的 XML 定义一个列表视图，当 [system.serviceprocess](/dotnet/api/System.ServiceProcess.ServiceController.Status) 属性的值发生更改时，它将启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="69ab1-123">The following XML defines a list view that starts a new group whenever the value of the [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) property changes.</span></span> <span data-ttu-id="69ab1-124">每个组启动时，将显示自定义标签，其中包含属性的新值。</span><span class="sxs-lookup"><span data-stu-id="69ab1-124">When each group is started, a custom label is displayed that includes the new value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
      <ListControl>
        <ListEntries>
          <ListEntry>
            <ListItems>
              <ListItem>
                <PropertyName>Name</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>DisplayName</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>ServiceType</PropertyName>
              </ListItem>
            </ListItems>
          </ListEntry>
        </ListEntries>
      </ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="69ab1-125">下面的示例演示 Windows PowerShell 如何显示 [system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 加载此格式化文件之后的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="69ab1-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span> <span data-ttu-id="69ab1-126">Windows PowerShell 将自动添加组标签之前和之后添加的空白行。</span><span class="sxs-lookup"><span data-stu-id="69ab1-126">The blank lines added before and after the group label are automatically added by Windows PowerShell.</span></span>

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="69ab1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69ab1-127">See Also</span></span>

[<span data-ttu-id="69ab1-128">格式设置文件示例</span><span class="sxs-lookup"><span data-stu-id="69ab1-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="69ab1-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="69ab1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
