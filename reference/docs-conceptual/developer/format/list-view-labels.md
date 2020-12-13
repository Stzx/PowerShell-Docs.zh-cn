---
ms.date: 09/13/2016
ms.topic: reference
title: 列表视图 (Label)
description: 列表视图 (Label)
ms.openlocfilehash: 2d341ae95d025e0f95b5d88b96afb846b62b092f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666682"
---
# <a name="list-view-labels"></a>列表视图 (Label)

此示例演示如何实现一个列表视图，以显示列表中每一行的自定义标签。 此列表视图显示 [system.serviceprocess. Servicecontroller 的属性？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 由 [get-help](/powershell/module/Microsoft.PowerShell.Management/Get-Service) Cmdlet 返回的 Fullname 对象。 有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。

### <a name="to-load-this-formatting-file"></a>加载此格式设置文件

1. 将本主题的 "示例" 部分中的 XML 复制到一个文本文件中。

2. 保存文本文件。 请确保将扩展名添加 `format.ps1xml` 到文件，以将其标识为格式化文件。

3. 打开 Windows PowerShell 并运行以下命令，将格式化文件加载到当前会话中： `Update-formatdata -prependpath PathToFormattingFile` 。

   > [!WARNING]
   > 此格式化文件定义已由 Windows PowerShell 格式设置文件定义的对象的显示。 在 `prependPath` 运行 cmdlet 时，必须使用参数，并且不能将此格式化文件作为模块加载。

## <a name="demonstrates"></a>演示

此格式化文件演示了以下 XML 元素：

- 视图的 [名称](./name-element-for-view-format.md) 元素。

- 定义视图要显示的对象的 [ViewSelectedBy](./viewselectedby-element-format.md) 元素。

- 定义视图显示的属性的 [ListControl](./listcontrol-element-format.md) 元素。

- 定义在列表视图的行中显示的[内容的包含项元素。](./listitem-element-for-listitems-for-listcontrol-format.md)

- [标签](./label-element-for-listitem-for-listcontrol-format.md)元素，用于定义在列表视图的行中显示的内容。

- 定义要显示的属性的 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 元素。

## <a name="example"></a>示例

下面的 XML 定义了一个在每一行中显示自定义标签的列表视图。 在这种情况下，该标签包含属性名称，其中每个字母都大写，而 "属性" 为单词。 在每一行中，属性的名称后跟属性的值。

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

下面的示例演示 Windows PowerShell 如何显示 [system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 加载此格式化文件之后的 Fullname 对象。

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

## <a name="see-also"></a>另请参阅

[格式设置文件示例](./examples-of-formatting-files.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
