---
title: 列表视图（标签） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53442bb1-74a3-49f9-9150-3bc3081a7565
caps.latest.revision: 6
ms.openlocfilehash: 27de41c88e224f7610c10a764e51524016ecc8cb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362786"
---
# <a name="list-view-labels"></a><span data-ttu-id="4a55b-102">列表视图 (Label)</span><span class="sxs-lookup"><span data-stu-id="4a55b-102">List View (Labels)</span></span>

<span data-ttu-id="4a55b-103">此示例演示如何实现一个列表视图，以显示列表中每一行的自定义标签。</span><span class="sxs-lookup"><span data-stu-id="4a55b-103">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="4a55b-104">此列表视图显示[system.serviceprocess. Servicecontroller 的属性？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController)由[get-help](/powershell/module/Microsoft.PowerShell.Management/Get-Service) Cmdlet 返回的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="4a55b-104">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="4a55b-105">有关列表视图组件的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="4a55b-105">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="4a55b-106">加载此格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4a55b-106">To load this formatting file</span></span>

1. <span data-ttu-id="4a55b-107">将本主题的 "示例" 部分中的 XML 复制到一个文本文件中。</span><span class="sxs-lookup"><span data-stu-id="4a55b-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="4a55b-108">保存文本文件。</span><span class="sxs-lookup"><span data-stu-id="4a55b-108">Save the text file.</span></span> <span data-ttu-id="4a55b-109">请确保将 @no__t 0 扩展添加到文件，以将其标识为格式文件。</span><span class="sxs-lookup"><span data-stu-id="4a55b-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="4a55b-110">打开 Windows PowerShell 并运行以下命令，将格式化文件加载到当前会话中： `Update-formatdata -prependpath PathToFormattingFile`。</span><span class="sxs-lookup"><span data-stu-id="4a55b-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4a55b-111">此格式化文件定义已由 Windows PowerShell 格式设置文件定义的对象的显示。</span><span class="sxs-lookup"><span data-stu-id="4a55b-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="4a55b-112">当你运行 cmdlet 时，必须使用 @no__t 参数，并且无法将此格式化文件作为模块加载。</span><span class="sxs-lookup"><span data-stu-id="4a55b-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4a55b-113">示例</span><span class="sxs-lookup"><span data-stu-id="4a55b-113">Demonstrates</span></span>

<span data-ttu-id="4a55b-114">此格式化文件演示了以下 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="4a55b-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="4a55b-115">视图的[名称](./name-element-for-view-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="4a55b-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="4a55b-116">定义视图要显示的对象的[ViewSelectedBy](./viewselectedby-element-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="4a55b-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="4a55b-117">定义视图显示的属性的[ListControl](./listcontrol-element-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="4a55b-117">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="4a55b-118">定义在列表视图的行中显示的[内容的包含项元素。](./listitem-element-for-listitems-for-listcontrol-format.md)</span><span class="sxs-lookup"><span data-stu-id="4a55b-118">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="4a55b-119">[标签](./label-element-for-listitem-for-listcontrol-format.md)元素，用于定义在列表视图的行中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="4a55b-119">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="4a55b-120">定义要显示的属性的[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="4a55b-120">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="4a55b-121">示例</span><span class="sxs-lookup"><span data-stu-id="4a55b-121">Example</span></span>

<span data-ttu-id="4a55b-122">下面的 XML 定义了一个在每一行中显示自定义标签的列表视图。</span><span class="sxs-lookup"><span data-stu-id="4a55b-122">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="4a55b-123">在这种情况下，该标签包含属性名称，其中每个字母都大写，而 "属性" 为单词。</span><span class="sxs-lookup"><span data-stu-id="4a55b-123">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="4a55b-124">在每一行中，属性的名称后跟属性的值。</span><span class="sxs-lookup"><span data-stu-id="4a55b-124">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
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
            <Label>NAME property</Label>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <Label>DISPLAYNAME property</Label>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <Label>STATUS property</Label>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <Label>SERVICETYPE property</Label>
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

<span data-ttu-id="4a55b-125">下面的示例演示 Windows PowerShell 如何显示[system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController)加载此格式化文件之后的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="4a55b-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
NAME property        : Fax
DISPLAYNAME property : Fax
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FCSAM
DISPLAYNAME property : Microsoft Antimalware Service
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : fdPHost
DISPLAYNAME property : Function Discovery Provider Host
STATUS property      : Stopped
SERVICETYPE property : Win32ShareProcess

NAME property        : FDResPub
DISPLAYNAME property : Function Discovery Resource Publication
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache
DISPLAYNAME property : Windows Font Cache Service
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache3.0.0.0
DISPLAYNAME property : Windows Presentation Foundation Font Cache 3.0.0.0
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FSysAgent
DISPLAYNAME property : Microsoft Forefront System Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : FwcAgent
DISPLAYNAME property : Firewall Client Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="4a55b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a55b-126">See Also</span></span>

[<span data-ttu-id="4a55b-127">格式化文件的示例</span><span class="sxs-lookup"><span data-stu-id="4a55b-127">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="4a55b-128">编写 PowerShell 格式化文件</span><span class="sxs-lookup"><span data-stu-id="4a55b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)