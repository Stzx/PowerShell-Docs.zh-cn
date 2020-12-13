---
ms.date: 09/13/2016
ms.topic: reference
title: 创建自定义控件
description: 创建自定义控件
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668042"
---
# <a name="creating-custom-controls"></a>创建自定义控件

自定义控件是最灵活的格式设置文件组件。 与定义数据的正式结构的表、列表和宽视图（如数据表）不同，自定义控件允许您定义单个数据片段的显示方式。 您可以定义一组公共自定义控件，这些控件可供格式设置文件的所有视图使用，您可以定义可用于特定视图的自定义控件，也可以定义一组可用于一组对象的控件。

## <a name="custom-control-example"></a>自定义控件示例

下面的示例演示了在 Certificates.Format.ps1xml 文件中定义的自定义控件。 此自定义控件用于分隔在表视图中显示的 [system.object](/dotnet/api/System.Management.Automation.Signature) 对象。

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a>另请参阅

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
