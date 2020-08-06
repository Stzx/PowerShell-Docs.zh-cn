---
title: 宽视图 (基本) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d92c29c33c5104b6186ae53ccf544be197d657b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772393"
---
# <a name="wide-view-basic"></a>宽视图 (Basic)

此示例演示如何实现显示[system.serviceprocess. Servicecontroller 的基本视图？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController)该 cmdlet 返回的 Fullname 对象 `Get-Service` 。 有关宽视图组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。

### <a name="to-load-this-formatting-file"></a>加载此格式设置文件

1. 将本主题的 "示例" 部分中的 XML 复制到一个文本文件中。

2. 保存文本文件。 请确保将扩展名添加 `format.ps1xml` 到文件，以将其标识为格式化文件。

3. 打开 Windows PowerShell 并运行以下命令，将格式化文件加载到当前会话中： `Update-formatdata -prependpath PathToFormattingFile` 。

   > [!WARNING]
   > 此格式化文件定义已由 Windows PowerShell 格式设置文件定义的对象的显示。 在 `prependPath` 运行 cmdlet 时，必须使用参数，并且不能将此格式化文件作为模块加载。

## <a name="demonstrates"></a>演示

此格式化文件演示了以下 XML 元素：

- 视图的[名称](./name-element-for-view-format.md)元素。

- 定义视图要显示的对象的[ViewSelectedBy](./viewselectedby-element-format.md)元素。

- 定义视图显示的属性的[WideItem](./wideitem-element-for-widecontrol-format.md)元素。

## <a name="example"></a>示例

下面的 XML 定义显示[system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName)属性值的宽视图。

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
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

下面的示例演示 Windows PowerShell 如何显示[system.serviceprocess. Servicecontroller？Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController)加载此格式化文件之后的 Fullname 对象。

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a>另请参阅

[格式设置文件示例](./examples-of-formatting-files.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
