---
title: 扩展类型系统成员集
ms.date: 07/09/2020
ms.openlocfilehash: 3f4e44ed7b498bb7c4a71f7b131270ed4f2ef981
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786248"
---
# <a name="ets-member-sets"></a>ETS 成员集

成员集允许您将**PSObject**对象的成员分区为两个子集，以便可以通过其子集名称同时引用子集的成员。 这两种类型的子集包括属性集和成员集。 例如，如果 PowerShell 使用成员集，则存在一个名为**使用 defaultdisplaypropertyset**的特定属性集，用于在运行时确定要为给定**PSObject**对象显示哪些属性。

## <a name="property-sets"></a>属性集

属性集可以包含**PSObject**类型的任意数量的属性。 通常情况下，只要需要同一类型)  (属性集，就可以使用属性集。 通过 `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` 使用属性集的名称和引用属性的名称调用构造函数来创建属性集。 然后，创建的**PSPropertySet**对象可用作指向集中属性的别名。 [PSPropertySet](/dotnet/api/system.management.automation.pspropertyset)类具有以下属性和方法。

- **IsInstance**属性：获取一个**布尔**值，该值指示属性的源。
- **MemberType**属性：获取属性集中的属性类型。
- **Name**属性：获取属性集的名称。
- **ReferencedPropertyNames**属性：获取属性集中属性的名称。
- **TypeNameOfValue**属性：获取用于将此集定义为属性集的**PropertySet**枚举常数。
- **Value**属性：获取或设置**PSPropertySet**对象。
- `PSPropertySet.Copy`方法：创建**PSPropertySet**对象的精确副本。
- `PSMemberSet.ToString`方法：将**PSPropertySet**对象转换为字符串。

## <a name="member-sets"></a>成员集

成员集可以包含任意数量的任意类型的扩展成员。 成员集是通过调用`PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`
带有成员集名称和引用成员名称的构造函数。 然后，创建的**PSPropertySet**对象可用作指向集中成员的别名。 [PSMemberSet](/dotnet/api/system.management.automation.psmemberset)类具有以下属性和方法。

- **IsInstance**属性：获取指示成员源的**布尔**值。
- **Members**属性：获取成员集的所有成员。
- **MemberType**属性：获取将此集定义为成员集**的成员集枚举常数**。
- **方法**属性：获取成员集中包含的方法。
- **Properties**属性：获取成员集中包含的属性。
- **TypeNameOfValue**属性：获取将此集定义为成员集**的成员集枚举常数**。
- **Value**属性：获取**PSMemberSet**对象。
- `PSMemberSet.Copy`方法：创建**PSMemberSet**对象的精确副本。
- `PSMemberSet.ToString`方法：将**PSMemberSet**对象转换为字符串。
