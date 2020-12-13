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
# <a name="wide-view-groupby"></a>宽视图 (GroupBy)

此示例演示如何实现显示 System.serviceprocess. Servicecontroller 的组的宽视图 [？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 该 cmdlet 返回的 Fullname 对象 `Get-Service` 。 有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。

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

- 定义新组的显示时间的 [GroupBy](./groupby-element-for-view-format.md) 元素。

- 定义视图显示的属性的 [WideItem](./wideitem-element-for-widecontrol-format.md) 元素。

## <a name="example"></a>示例

下面的 XML 定义显示对象组的宽视图。 当 [system.serviceprocess](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) 属性的值发生更改时，将启动每个新组。

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

下面的示例演示 Windows PowerShell 如何显示 [system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) 加载此格式化文件之后的 Fullname 对象。

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

## <a name="see-also"></a>另请参阅

[格式设置文件示例](./examples-of-formatting-files.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
