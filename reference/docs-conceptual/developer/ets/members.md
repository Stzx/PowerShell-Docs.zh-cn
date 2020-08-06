---
title: 扩展类型系统类成员
ms.date: 07/09/2020
ms.openlocfilehash: 24a57b7fd0b3db47d0d7138859aa0502ca9016f0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786265"
---
# <a name="extended-type-system-class-members"></a>扩展类型系统类成员

ETS 是指若干不同类型的成员，这些成员的类型由**PSMemberTypes**枚举定义。 这些成员类型包括属性、方法、成员和成员集，它们分别由其自己的 CLR 类型定义。 例如， **NoteProperty**由其自己的**PSNoteProperty**类型定义。 这些单独的 CLR 类型具有其自己的唯一属性和从[PSMemberInfo 类](/dotnet/api/system.management.automation.psmemberinfo)继承的公共属性。

## <a name="the-psmemberinfo-class"></a>PSMemberInfo 类

**PSMemberInfo**类充当所有 ETS 成员类型的基类。 此类为所有成员 CLR 类型提供以下基本属性。

- **Name**属性：成员的名称。 此名称可由基本对象定义，或者在公开改编成员或扩展成员时由 PowerShell 定义。
- **值**属性：从特定成员返回的值。 每个成员类型定义它如何处理其成员值。
- **TypeNameOfValue**属性：这是值属性返回的值的 CLR 类型的名称。

## <a name="accessing-members"></a>访问成员

可以通过**PSObject**对象的**成员**、**方法**和**属性**属性访问成员的集合。

## <a name="ets-properties"></a>ETS 属性

ETS 属性是可作为属性来处理的成员。 实质上，它们可以出现在表达式的左侧。 它们包括别名属性、代码属性、PowerShell 属性、便笺属性和脚本属性。 有关这些类型的属性的详细信息，请参阅[ETS properties](properties.md)。

## <a name="ets-methods"></a>ETS 方法

ETS 方法是可以采用参数的成员，可能返回结果，并且不能出现在表达式的左侧。 它们包括代码方法、PowerShell 方法和脚本方法。
有关这些类型的方法的详细信息，请参阅[ETS 方法](methods.md)。
