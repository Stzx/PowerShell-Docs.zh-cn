---
ms.date: 09/13/2016
ms.topic: reference
title: 列表视图 (Basic)
description: 列表视图 (Basic)
ms.openlocfilehash: d80ac9c6143b976d8bc13e2b184e4f5a2f8a37ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666631"
---
# <a name="list-view-basic"></a><span data-ttu-id="4627c-103">列表视图 (Basic)</span><span class="sxs-lookup"><span data-stu-id="4627c-103">List View (Basic)</span></span>

<span data-ttu-id="4627c-104">此示例演示如何实现显示 System.serviceprocess. Servicecontroller 的基本列表视图 [？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 由 [get-help](/powershell/module/microsoft.powershell.management/get-service) Cmdlet 返回的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="4627c-104">This example shows how to implement a basic list view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="4627c-105">有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="4627c-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="4627c-106">加载此格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4627c-106">To load this formatting file</span></span>

1. <span data-ttu-id="4627c-107">将本主题的 "示例" 部分中的 XML 复制到一个文本文件中。</span><span class="sxs-lookup"><span data-stu-id="4627c-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="4627c-108">保存文本文件。</span><span class="sxs-lookup"><span data-stu-id="4627c-108">Save the text file.</span></span> <span data-ttu-id="4627c-109">请确保将扩展名添加 `format.ps1xml` 到文件，以将其标识为格式化文件。</span><span class="sxs-lookup"><span data-stu-id="4627c-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="4627c-110">打开 Windows PowerShell 并运行以下命令，将格式化文件加载到当前会话中： `Update-formatdata -prependpath PathToFormattingFile` 。</span><span class="sxs-lookup"><span data-stu-id="4627c-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4627c-111">此格式化文件定义已由 Windows PowerShell 格式设置文件定义的对象的显示。</span><span class="sxs-lookup"><span data-stu-id="4627c-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="4627c-112">在 `prependPath` 运行 cmdlet 时，必须使用参数，并且不能将此格式化文件作为模块加载。</span><span class="sxs-lookup"><span data-stu-id="4627c-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4627c-113">演示</span><span class="sxs-lookup"><span data-stu-id="4627c-113">Demonstrates</span></span>

<span data-ttu-id="4627c-114">此格式化文件演示了以下 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="4627c-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="4627c-115">视图的 [名称](./name-element-for-view-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="4627c-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="4627c-116">定义视图要显示的对象的 [ViewSelectedBy](./viewselectedby-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="4627c-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="4627c-117">定义视图显示的属性的 [ListControl](./listcontrol-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="4627c-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="4627c-118">定义在列表视图的行中显示的[内容的包含项元素。](./listitem-element-for-listitems-for-listcontrol-format.md)</span><span class="sxs-lookup"><span data-stu-id="4627c-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="4627c-119">定义要显示的属性的 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="4627c-119">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="4627c-120">示例</span><span class="sxs-lookup"><span data-stu-id="4627c-120">Example</span></span>

<span data-ttu-id="4627c-121">下面的 XML 定义显示 System.serviceprocess. Servicecontroller 的四个属性的列表视图 [。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) 对象。</span><span class="sxs-lookup"><span data-stu-id="4627c-121">The following XML defines a list view that displays four properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="4627c-122">在每一行中，属性的名称后跟属性的值。</span><span class="sxs-lookup"><span data-stu-id="4627c-122">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
  <View>
    <Name>System.ServiceProcess.ServiceController</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
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
              <PropertyName>Status</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>ServiceType</PropertyName>
            </ListItem>
          </ListItems>
        </ListEntry>
      </ListEntries>
    </ListControl>
  </View>
</Configuration>
```

<span data-ttu-id="4627c-123">下面的示例演示 Windows PowerShell 如何显示 [system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 加载此格式化文件之后的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="4627c-123">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Name        : Fax
DisplayName : Fax
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
Status      : Running
ServiceType : Win32OwnProcess

Name        : fdPHost
DisplayName : Function Discovery Provider Host
Status      : Stopped
ServiceType : Win32ShareProcess

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
Status      : Running
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
Status      : Running
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="4627c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4627c-124">See Also</span></span>

[<span data-ttu-id="4627c-125">格式设置文件示例</span><span class="sxs-lookup"><span data-stu-id="4627c-125">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="4627c-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4627c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
