---
ms.date: 07/29/2020
title: PowerShell 5.0 中的新语言功能
description: PowerShell 5.0 添加了使用类似于其他面向对象的编程语言的语法和语义定义类和其他用户定义的类型的功能。
ms.openlocfilehash: 31ff54ba6f2800a0680c1a2db3832ca97246973d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663303"
---
# <a name="new-language-features-in-powershell-50"></a>PowerShell 5.0 中的新语言功能

PowerShell 5.0 添加了使用类似于其他面向对象的编程语言的语法和语义定义类和其他用户定义的类型的功能。 目标是使开发人员和 IT 专业人员在更广泛的用例中使用 PowerShell，从而简化 PowerShell 项目开发（如 DSC 资源），并加速覆盖管理面。

PowerShell 5.0 引入了以下 PowerShell 中的新语言元素：

### <a name="class-keyword"></a>Class 关键字

`class` 关键字定义了一个新类。 这是真正的 .NET Framework 类型。 Class 成员是公开的，但仅在模块作用域内公开。 不能引用类型名称作为字符串（例如，`New-Object` 不起作用），并且在此版本中，也不能在该类定义的脚本或模块文件外部使用类型文本（例如，`[MyClass]`）。

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>Enum 关键字和枚举

已添加对 `enum` 关键字的支持，它使用换行符作为分隔符。 当前，不能根据自身定义枚举器。 但是，可以根据一个枚举初始化另一个枚举，如下面的示例中所示。 此外，不能指定基类型；它始终是 `[int]`。

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

枚举器值必须是分析时间常量。 不能将其设置为调用命令的结果。

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

枚举支持算术运算，如下面的示例中所示。

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` 现在是一个真正的动态关键字。 PowerShell 用于分析指定的模块的根模块，搜索包含 DscResource 属性的类。

### <a name="implementingassembly"></a>ImplementingAssembly

已将新字段 ImplementingAssembly 添加到了 ModuleInfo。 如果脚本模块定义类，或者二进制模块的加载程序集，则会将此字段设置为为脚本模块创建的动态程序集。 当 ModuleType  为 Manifest  时，不会对该字段进行设置。

**ImplementingAssembly** 字段上的反射可发现模块中的资源。 这意味着你可以发现用 PowerShell 或其他托管语言编写的资源。

## <a name="further-reading"></a>其他阅读材料

- [about_Classes](/powershell/module/microsoft.powershell.core/about/about_classes)
- [about_Enum](/powershell/module/microsoft.powershell.core/about/about_enum)
- [about_Classes_and_DSC](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
