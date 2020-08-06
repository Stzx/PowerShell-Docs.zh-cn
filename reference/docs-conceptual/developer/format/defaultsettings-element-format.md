---
title: " (格式) 的 DefaultSettings 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787727"
---
# <a name="defaultsettings-element-format"></a>DefaultSettings Element (Format)

定义适用于格式设置文件的所有视图的常见设置。 常见的设置包括显示错误、在表中环绕文本、定义集合的展开方式等。

配置元素 (格式) DefaultSettings 元素 (格式) 

## <a name="syntax"></a>语法

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `DefaultSettings` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[DisplayError Element (Format)](./displayerror-element-format.md)|可选元素。<br /><br /> 指定在显示一段数据的过程中出现错误时，显示字符串 #ERR。|
|[EnumerableExpansions Element (Format)](./enumerableexpansions-element-format.md)|可选元素。<br /><br /> 定义 .NET 对象显示在视图中时的不同显示方式。|
|[PropertyCountForTable (格式) ](./propertycountfortable-element-format.md)|可选元素。<br /><br /> 指定在表视图中显示对象时必须包含的属性的最小数目。|
|[ShowError Element (Format)](./showerror-element-format.md)|可选元素。<br /><br /> 指定在显示一段数据的过程中出现错误时，显示完整的错误记录。|
|[WrapTables Element (Format)](./wraptables-element-format.md)|可选元素。<br /><br /> 指定如果表中的数据无法适应列的宽度，则将其移到下一行。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|[配置元素](./configuration-element-format.md)|表示格式设置文件的顶级元素。|

## <a name="remarks"></a>备注

## <a name="see-also"></a>另请参阅

[配置元素](./configuration-element-format.md)

[DisplayError Element (Format)](./displayerror-element-format.md)

[EnumerableExpansions Element (Format)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (格式) ](./propertycountfortable-element-format.md)

[ShowError Element (Format)](./showerror-element-format.md)

[WrapTables Element (Format)](./wraptables-element-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
