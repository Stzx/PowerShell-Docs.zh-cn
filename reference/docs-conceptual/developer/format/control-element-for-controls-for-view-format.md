---
title: View (Format) 控件的控件元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783800"
---
# <a name="control-element-for-controls-for-view--format"></a>Control Element for Controls for View (Format)

定义可供视图使用的控件以及用于引用控件的名称。

配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 控件 (格式) 控件元素

## <a name="syntax"></a>语法

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>特性和元素

以下各节描述了元素的属性、子元素和父元素 `Control` 。

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[用于控件的名称元素 (格式) ](./name-element-for-control-for-controls-for-view-format.md)|必需的元素。<br /><br /> 指定控件的名称。|
|[CustomControl Element for Control for Controls for View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)|必需的元素。<br /><br /> 定义此视图使用的控件。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[控件元素 (格式) ](./controls-element-for-view-format.md)|定义可供特定视图使用的视图控件。|

## <a name="remarks"></a>备注

此控件可由以下元素指定：

- [CustomControlName Element for ExpressionBinding for Controls for View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [CustomControlName Element for ExpressionBinding for CustomControl for View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [CustomControlName Element for ExpressionBinding for GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [CustomControlName Element for GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a>另请参阅

[CustomControl Element for Control for Controls for View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md)

[CustomControlName Element for ExpressionBinding for Controls for View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[CustomControlName Element for ExpressionBinding for CustomControl for View (Format)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomControlName Element for ExpressionBinding for GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[CustomControlName Element for ExpressionBinding for GroupBy (Format)](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[控件元素 (格式) ](./controls-element-for-view-format.md)

[Name Element for Control for Controls for View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[编写 PowerShell 格式设置文件](./writing-a-powershell-formatting-file.md)
