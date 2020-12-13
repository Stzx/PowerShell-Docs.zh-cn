---
ms.date: 09/13/2016
ms.topic: reference
title: 宽视图 (GroupBy)
description: 宽视图 (GroupBy)
ms.openlocfilehash: 807bea2a5d44c38e2c9977f792bea2fb9bca0fc3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667668"
---
# <a name="wide-view-groupby"></a><span data-ttu-id="41f3b-103">宽视图 (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="41f3b-103">Wide View (GroupBy)</span></span>

<span data-ttu-id="41f3b-104">此示例演示如何实现显示 System.serviceprocess. Servicecontroller 的组的宽视图 [？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 该 cmdlet 返回的 Fullname 对象 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="41f3b-104">This example shows how to implement a wide view that displays groups of [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="41f3b-105">有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="41f3b-105">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="41f3b-106">加载此格式设置文件</span><span class="sxs-lookup"><span data-stu-id="41f3b-106">To load this formatting file</span></span>

1. <span data-ttu-id="41f3b-107">将本主题的 "示例" 部分中的 XML 复制到一个文本文件中。</span><span class="sxs-lookup"><span data-stu-id="41f3b-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="41f3b-108">保存文本文件。</span><span class="sxs-lookup"><span data-stu-id="41f3b-108">Save the text file.</span></span> <span data-ttu-id="41f3b-109">请确保将扩展名添加 `format.ps1xml` 到文件，以将其标识为格式化文件。</span><span class="sxs-lookup"><span data-stu-id="41f3b-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="41f3b-110">打开 Windows PowerShell 并运行以下命令，将格式化文件加载到当前会话中： `Update-formatdata -prependpath PathToFormattingFile` 。</span><span class="sxs-lookup"><span data-stu-id="41f3b-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="41f3b-111">此格式化文件定义已由 Windows PowerShell 格式设置文件定义的对象的显示。</span><span class="sxs-lookup"><span data-stu-id="41f3b-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting files.</span></span> <span data-ttu-id="41f3b-112">在 `prependPath` 运行 cmdlet 时，必须使用参数，并且不能将此格式化文件作为模块加载。</span><span class="sxs-lookup"><span data-stu-id="41f3b-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="41f3b-113">演示</span><span class="sxs-lookup"><span data-stu-id="41f3b-113">Demonstrates</span></span>

<span data-ttu-id="41f3b-114">此格式化文件演示了以下 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="41f3b-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="41f3b-115">视图的 [名称](./name-element-for-view-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="41f3b-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="41f3b-116">定义视图要显示的对象的 [ViewSelectedBy](./viewselectedby-element-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="41f3b-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="41f3b-117">定义新组的显示时间的 [GroupBy](./groupby-element-for-view-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="41f3b-117">The [GroupBy](./groupby-element-for-view-format.md) element that defines when a new group is displayed.</span></span>

- <span data-ttu-id="41f3b-118">定义视图显示的属性的 [WideItem](./wideitem-element-for-widecontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="41f3b-118">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="41f3b-119">示例</span><span class="sxs-lookup"><span data-stu-id="41f3b-119">Example</span></span>

<span data-ttu-id="41f3b-120">下面的 XML 定义显示对象组的宽视图。</span><span class="sxs-lookup"><span data-stu-id="41f3b-120">The following XML defines a wide view that displays groups of objects.</span></span> <span data-ttu-id="41f3b-121">当 [system.serviceprocess](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) 属性的值发生更改时，将启动每个新组。</span><span class="sxs-lookup"><span data-stu-id="41f3b-121">Each new group is started when the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <Label>Service Type</Label>
        <PropertyName>ServiceType</PropertyName>
      </GroupBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="41f3b-122">下面的示例演示 Windows PowerShell 如何显示 [system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 加载此格式化文件之后的 Fullname 对象。</span><span class="sxs-lookup"><span data-stu-id="41f3b-122">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
   Service Type: Win32OwnProcess

Fax                             FCSAM

   Service Type: Win32ShareProcess

fdPHost                         FDResPub
FontCache

   Service Type: Win32OwnProcess

FontCache3.0.0.0                FSysAgent
FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="41f3b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41f3b-123">See Also</span></span>

[<span data-ttu-id="41f3b-124">格式设置文件示例</span><span class="sxs-lookup"><span data-stu-id="41f3b-124">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="41f3b-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="41f3b-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
