---
title: 扩展类型系统属性
ms.date: 07/09/2020
ms.openlocfilehash: c0a994e5b946117dcc1a2d647d07ae62af883861
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786197"
---
# <a name="ets-properties"></a>ETS 属性

属性是可作为属性来处理的成员。 实质上，它们可以出现在表达式的左侧。 可用的属性包括 "别名"、"代码"、"注释" 和 "脚本" 属性。

## <a name="alias-property"></a>Alias 属性

Alias 属性是一个属性，该属性引用**PSObject**对象包含的另一个属性。 它主要用于重命名引用的属性。 但是，它还可以用于将引用的属性的值转换为另一种类型。 对于 ETS，此类型的属性始终是扩展成员，由[PSAliasProperty](/dotnet/api/system.management.automation.psaliasproperty)类定义。 类包含以下属性。

- **ConversionType**属性：用于转换引用成员的值的 CLR 类型。
- **IsGettable**属性：指示是否可以检索所引用属性的值。
  通过检查所引用属性的**IsGettable**属性，可动态确定此属性。
- **IsSettable**属性：指示是否可以设置所引用属性的值。 通过检查所引用属性的**IsSettable**属性，可动态确定此属性。
- **MemberType**属性： **AliasProperty**枚举常量，用于将此属性定义为别名属性。
- **ReferencedMemberName**属性：此别名引用的引用属性的名称。
- **TypeNameOfValue**属性：所引用属性的值的 CLR 类型的完整名称。
- **值**属性：引用属性的值。

## <a name="code-property"></a>Code 属性

"代码" 属性是一个属性，它是在 CLR 语言中定义的 getter 和 setter。 为了使代码属性变为可用，开发人员必须以某种 CLR 语言编写该属性，然后编译并交付生成的程序集。 此程序集必须在需要 code 属性的运行空间中可用。 对于 ETS，此类型的属性始终是扩展成员，由[PSCodeProperty](/dotnet/api/system.management.automation.pscodeproperty)类定义。 类包含以下属性。

- **GetterCodeReference**属性：用于获取代码属性值的方法。
- **IsGettable**属性：指示是否可检索代码属性的值， **SetterCodeReference**属性：用于设置代码属性值的方法。
- **IsSettable**属性：指示是否可以设置代码属性的值， **SetterCodeReference**属性不为 null。
- **MemberType**属性：将此属性定义为代码属性的**CodeProperty**枚举常数。
- **SetterCodeReference**属性：用于获取代码属性值的方法。
- **TypeNameOfValue**属性：由 properties 获取操作返回的代码属性值的 CLR 类型。
- **值**属性：代码属性的值。 检索此属性时，将调用 GetterCodeReference 属性中的 getter 代码，传递当前**PSObject**对象并返回调用返回的值。 设置此属性时，将调用**SetterCodeReference**属性中的 setter 代码，并将当前**PSObject**对象传递为第一个参数，并将用于设置该值的对象设置为第二个参数。

## <a name="note-property"></a>Note 属性

Note 属性是具有名称/值对的属性。 对于 ETS，此类型的属性始终是扩展成员，由[PSNoteProperty](/dotnet/api/system.management.automation.psnoteproperty)类定义。 类包含以下属性。

- **IsGettable**属性：指示是否可以检索 note 属性的值。
- **IsSettable**属性：指示是否可以设置注释属性的值。
- **MemberType**属性：将此属性定义为便笺属性的**NoteProperty**枚举常量。
- **TypeNameOfValue**属性： note 属性的 get 操作返回的对象的完全限定的类型名称。
- **值**： note 属性的值。

## <a name="powershell-property"></a>PowerShell 属性

PowerShell 属性是在基对象上定义的属性，或通过适配器提供的属性。 它可以引用 CLR 字段和 CLR 属性。 对于 ETS，此类型的属性可以是基成员或适配器成员，由[PSProperty](/dotnet/api/system.management.automation.psproperty)类定义。 类包含以下属性。

- **IsGettable**属性：指示是否可以检索基准或改编属性的值。
- **IsSettable**属性：指示是否可以设置基本或改编属性的值。
- **MemberType**属性：将此属性定义为 PowerShell 属性的属性枚举常量。
- **TypeNameOfValue**属性：属性值类型的完全限定名称。 例如，对于值为字符串的属性，其属性值**类型为 system.string。**
- **值**属性：属性的值。 如果对不支持该操作的属性调用 get 或 set 操作，则会引发**GetValueException**或**SetValueException**异常

## <a name="powershell-script-property"></a>PowerShell 脚本属性

脚本属性是具有 getter 和 setter 脚本的属性。 对于 ETS，此类型的属性始终是扩展成员，由[PSScriptProperty](/dotnet/api/system.management.automation.psscriptproperty)类定义。 类包含以下属性。

- **GetterScript**属性：用于检索脚本属性值的脚本。
- **IsGettable**属性：指示**GetterScript**属性是否公开脚本块。
- **IsSettable**属性：指示**SetterScript**属性是否公开脚本块。
- **MemberType**属性：将此属性标识为脚本属性的 ScriptProperty 枚举常数。
- **SetterScript**属性：用于设置脚本属性值的脚本。
- **TypeNameOfValue**属性： getter 脚本返回的对象的完全限定的类型名称。 在这种情况下，始终返回**system.object** 。
- **Value**属性： Script 属性的值。 Get 调用 getter 脚本并返回所提供的值。 集调用 setter 脚本。
