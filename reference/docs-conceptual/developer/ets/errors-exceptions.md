---
title: 扩展类型系统中的错误和异常
ms.date: 07/09/2020
ms.openlocfilehash: f60c53e33c031168eda53726e0d296bf91139fda
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786282"
---
# <a name="errors-and-exceptions-in-the-extended-type-system"></a>扩展类型系统中的错误和异常

在 ETS 类型数据和访问**PSObject**对象的成员或使用**languageprimitives.physicalequality**等实用工具类之一时，可能会出现错误。

## <a name="runtime-errors"></a>运行时错误

有一个例外，在强制转换时，在运行时从 ETS 引发的所有异常都是**ExtendedTypeSystemException**异常或从**ExtendedTypeSystemException**类派生的异常。 这样脚本开发人员就可以使用脚本中的语句来捕获这些异常 `Trap` 。

## <a name="errors-getting-member-values"></a>获取成员值时出错

获取 ETS 成员的值 (属性、方法或参数化属性) 导致引发**GetValueException**或**GetValueInvocationException**异常时所发生的所有错误。
当 ETS 识别到发生错误时，将引发**GetValueException**异常。 当被引用成员的基础 getter 识别到错误时，将引发**GetValueInvocationException**异常，该异常可能包含或可能不包含导致 get 调用错误的内部异常。

## <a name="errors-setting-member-values"></a>设置成员值时出错

设置 ETS 属性的值时发生的所有错误都将导致引发**SetValueException**或**SetValueInvocationException**异常。 当 ETS 识别到发生错误时，将引发**SetValueException**异常。 当所引用属性的基础 setter 识别到发生错误时，将引发**SetValueInvocationException**异常，该异常可能包含或可能不包含导致集调用错误的内部异常。

## <a name="errors-invoking-a-method"></a>调用方法时出错

调用 ETS 方法时发生的所有错误都会导致引发**MethodException**或**MethodInvocationException**异常。 当 ETS 识别到发生错误时，将引发**MethodException**异常。 当被引用的方法识别到发生错误时，将引发**MethodInvocationException**异常，该异常可能包含或可能不包含导致调用错误的内部异常。

## <a name="casting-errors"></a>转换错误

尝试无效强制转换时，将引发**PSInvalidCastException** 。 由于此异常派生自**InvalidCastException**，因此无法直接从脚本中捕获该异常。 请注意，尝试强制转换的实体需要将**PSInvalidCastException**中的**PSRuntimeException**包装起来，才能由脚本捕获。 如果尝试设置**PSPropertySet**、 **PSMemberSet**、 **PSMethodInfo**或**ReadOnlyPSMemberInfoCollection ' 1**的成员的值，则会引发**NotSupportedException** 。

## <a name="common-runtime-errors"></a>常见运行时错误

发生的任何其他常见运行时错误都属于类型**ExtendedTypeSystemException**异常，无其他特定异常类型。

## <a name="initialization-errors"></a>初始化错误

初始化时可能会发生错误 `types.ps1xml` 。 通常，当 PowerShell 运行时启动时，将显示这些错误。 不过，也可以在加载模块时显示它们。
