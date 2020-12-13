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
# <a name="creating-custom-controls"></a><span data-ttu-id="10595-103">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="10595-103">Creating Custom Controls</span></span>

<span data-ttu-id="10595-104">自定义控件是最灵活的格式设置文件组件。</span><span class="sxs-lookup"><span data-stu-id="10595-104">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="10595-105">与定义数据的正式结构的表、列表和宽视图（如数据表）不同，自定义控件允许您定义单个数据片段的显示方式。</span><span class="sxs-lookup"><span data-stu-id="10595-105">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="10595-106">您可以定义一组公共自定义控件，这些控件可供格式设置文件的所有视图使用，您可以定义可用于特定视图的自定义控件，也可以定义一组可用于一组对象的控件。</span><span class="sxs-lookup"><span data-stu-id="10595-106">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="10595-107">自定义控件示例</span><span class="sxs-lookup"><span data-stu-id="10595-107">Custom Control Example</span></span>

<span data-ttu-id="10595-108">下面的示例演示了在 Certificates.Format.ps1xml 文件中定义的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="10595-108">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="10595-109">此自定义控件用于分隔在表视图中显示的 [system.object](/dotnet/api/System.Management.Automation.Signature) 对象。</span><span class="sxs-lookup"><span data-stu-id="10595-109">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="10595-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10595-110">See Also</span></span>

[<span data-ttu-id="10595-111">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="10595-111">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
