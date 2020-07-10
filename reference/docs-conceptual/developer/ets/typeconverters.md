---
title: 扩展类型系统类型转换器
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: f709a64febe68733b79ed8af804714d3f3ddeaac
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217921"
---
# <a name="ets-type-converters"></a>ETS 类型转换器

当对方法进行调用时，ETS 使用两种基本类型的转换器 `LanguagePrimitives.ConvertTo(System.Object, System.Type)` 。 调用此方法时，PowerShell 将尝试使用其标准 PowerShell 语言转换器或自定义转换器执行类型转换。 如果 PowerShell 无法执行转换，则会引发**PSInvalidCastException**异常。

## <a name="standard-windows-powershell-language-converters"></a>标准 Windows PowerShell 语言转换器

这些标准转换在任何自定义转换之前进行检查，且不能重写。 下表列出了调用方法时 PowerShell 执行的类型转换 `ConvertTo(System.Object, System.Type)` 。 请注意，引用**valueToConvert**和**resultType**参数将引用该方法的参数 `ConvertTo(System.Object,System.Type)` 。

| From (valueToConvert)  |   (resultType)   |                                                                               返回                                                                               |
| --------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Null                  | 字符串            | ""                                                                                                                                                                  |
| Null                  | Char              | '\0'                                                                                                                                                                |
| Null                  | 数值           | `0`在**resultType**参数中指定的类型的。                                                                                                          |
| Null                  | 布尔           | 调用方法的结果 `IsTrue(System.Object)(Null)` 。                                                                                                        |
| Null                  | PSObject          | 类型**PSObject**的新对象。                                                                                                                                    |
| Null                  | 非值类型    | 无效.                                                                                                                                                               |
| Null                  | 可以为 null 的 &lt; T&gt; | 无效.                                                                                                                                                               |
| 派生类         | 基类        | **valueToConvert**                                                                                                                                                  |
| 任何内容              | Void              | **Automationnull.value**                                                                                                                                            |
| 任何内容              | 字符串            | 调用 `ToString` 机制。                                                                                                                                         |
| 任何内容              | 布尔           | `IsTrue(System.Object) (valueToConvert)`                                                                                                                            |
| 任何内容              | PSObject          | 调用方法的结果 `AsPSObject(System.Object) (valueToConvert)` 。                                                                                         |
| 任何内容              | Xml 文档      | 将**valueToConvert**转换为字符串，然后**调用**构造函数。                                                                                      |
| Array                 | Array             | 尝试转换数组的每个元素。                                                                                                                      |
| 单一实例             | 数组             | `Array[0]`等于**valueToConvert** ，它转换为数组的元素类型。                                                                            |
| IDictionary           | 哈希表        | 调用哈希表 (valueToConvert) 的结果。                                                                                                                       |
| 字符串                | Char[]            | `valueToConvert.ToCharArray`                                                                                                                                        |
| 字符串                | RegEx             | 调用的结果 `Regx(valueToConvert)` 。                                                                                                                          |
| 字符串                | 类型              | 使用**valueToConvert**参数来搜索**RunspaceConfiguration**，返回相应的类型。                                                 |
| 字符串                | Numeric           | 如果**valueToConvert**是 ""，则返回 `0` **resultType**。 否则，将使用区域性 "区域性固定" 来生成数字值。                       |
| Integer               | System.Enum       | 如果整数由枚举定义，则将整数转换为常量。 如果未定义整数，则会引发**PSInvalidCastException**异常。 |

## <a name="custom-conversions"></a>自定义转换

如果 PowerShell 无法使用标准 PowerShell 语言转换器转换类型，则它会检查自定义转换器。 PowerShell 会按照此部分中所述的顺序查找多种类型的自定义转换器。 请注意，引用**valueToConvert**和**resultType**参数将引用该方法的参数 `ConvertTo(System.Object, System.Type)` 。 如果自定义转换器引发异常，则不会再尝试转换该对象，并且该异常将被包装在**PSInvalidCastException**异常中，然后将引发此异常。

## <a name="powershell-type-converter"></a>PowerShell 类型转换器

PowerShell 类型转换器用于转换单个类型或类型族，如派生自**system.exception 类的所有类型。** 若要创建 PowerShell 类型转换器，必须实现 PSTypeConverter 类并将该实现与目标类相关联。 可以通过两种方式将 PowerShell 类型转换器与其目标类相关联。

- 通过类型配置文件
- 通过将**TypeConverterAttribute**属性应用于目标类

从[PSTypeConverter](/dotnet/api/system.management.automation.pstypeconverter)抽象类派生的 PowerShell 类型转换器提供将对象转换为特定类型或从特定类型转换的方法。 如果**valueToConvert**参数包含一个对象，该对象具有与之关联的 PowerShell 类型转换器，则 powershell 会调用`PSTypeConverter.ConvertTo(System.Object, System.Type,System.IFormatProvider, System.Boolean)`
关联转换器的方法，将对象转换为**resultType**参数指定的类型。 如果**resultType**参数引用具有与之关联的 PowerShell 类型转换器的类型，则 powershell 会调用`PSTypeConverter.ConvertFrom(System.Object,System.Type, System.IFormatProvider, System.Boolean)`
关联转换器的方法，用于转换由**resultType**参数指定的类型的对象。

## <a name="system-type-converter"></a>系统类型转换器

系统类型转换器用于转换特定的目标类。 此类型的转换器不能用于转换类的系列。 若要创建系统类型转换器，必须实现[TypeConverter](/dotnet/api/system.management.automation.runspaces.typedata.typeconverter#System_Management_Automation_Runspaces_TypeData_TypeConverter)类并将该实现与目标类相关联。 可以通过两种方法将系统类型转换器与其目标类相关联。

- 通过类型配置文件
- 通过将 TypeConverterAttribute 属性应用于目标类

## <a name="parse-converter"></a>分析转换器

如果**valueToConvert**参数是一个字符串，并且**resultType**参数的对象类型有 `Parse` 方法，则 `Parse` 调用方法来转换字符串。

## <a name="constructor-converter"></a>构造函数转换器

如果**resultType**参数的对象类型具有一个构造函数，该构造函数的单个参数与**valueToConvert**参数的对象的类型相同，则将调用此构造函数。

## <a name="implicit-cast-operator-converter"></a>隐式转换运算符转换器

如果**valueToConvert**参数具有转换为**resultType**的隐式强制转换运算符，则调用其转换运算符。 如果**resultType**参数具有从**valueToConvert**转换的隐式强制转换运算符，则调用其转换运算符。

## <a name="explicit-cast-operator-converter"></a>显式强制转换运算符转换器

如果**valueToConvert**参数具有转换为**resultType**的显式转换运算符，则调用其转换运算符。 如果**resultType**参数具有从**valueToConvert**转换的显式转换运算符，则调用其转换运算符。
