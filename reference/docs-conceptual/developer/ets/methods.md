---
title: 扩展类型系统类方法
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: 97c11093d2faeb2a73b349c479d6de34ae2ea788
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217920"
---
# <a name="ets-class-methods"></a>ETS 类方法

ETS 方法是可以采用参数的成员，可能返回结果，并且不能出现在表达式的左侧。 ETS 中的可用方法包括代码、Windows PowerShell 和脚本方法。

> [!NOTE]
> 在脚本中，使用与其他成员相同的语法访问方法，并在方法名称末尾添加括号。

## <a name="code-methods"></a>代码方法

代码方法是在 CLR 语言中定义的扩展成员。 它为基本对象上定义的方法提供了类似的功能;但是，可以将代码方法动态添加到**PSObject**对象。 为了使代码方法变得可用，开发人员必须以某种 CLR 语言编写该属性，然后编译并交付生成的程序集。 此程序集必须在需要代码方法的运行空间中可用。 请注意，代码方法的实现必须是线程安全的。 可以通过提供以下公共方法和属性的[PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)对象来访问这些方法。

- `PSCodeMethod.Copy`方法：创建**PSCodeMethod**对象的精确副本。
- `PSCodeMethod.Invoke(System.Object[])`方法：调用基础代码方法。
- `PSCodeMethod.ToString`方法：将**PSCodeMethod**对象转换为字符串。
- `PSCodeMethod.CodeReference`属性：获取代码方法所基于的基础方法。
- **PSMemberInfo. IsInstance**属性：获取指示成员源的**布尔**值。
- **PSCodeMethod. MemberType**属性：获取将此方法标识为代码方法的**PSMemberTypes。**
- **PSMemberInfo.Name**属性：获取基础代码方法的名称。
- **PSCodeMethod. OverloadDefinitions**属性：获取基础代码方法的所有重载的定义。
- **PSCodeMethod. TypeNameOfValue**属性：获取代码方法的完整名称。
- **PSMemberInfo**属性：获取**PSCodeMethod**对象。

## <a name="windows-powershell-methods"></a>Windows PowerShell 方法

PowerShell 方法是在基对象上定义的或可通过适配器访问的 CLR 方法。 可以通过提供以下公共方法和属性的**PSMethod**对象来访问这些方法。

- `PSMethod.Copy`方法：创建**PSMethod**对象的精确副本。
- `PSMethod.Invoke(System.Object[])`方法：调用基础方法。
- `PSMethod.ToString`方法：将**PSMethod**对象转换为字符串。
- **PSMemberInfo. IsInstance**属性：获取指示成员源的**布尔**值。
- **PSMethod. MemberType**属性：获取将此方法标识为 PowerShell 方法的**PSMemberTypes**枚举常数。
- **PSMemberInfo.Name**属性：获取基础方法的名称。
- **PSMethod. OverloadDefinitions**属性：获取基础方法的所有重载的定义。
- **PSMethod. TypeNameOfValue**属性：获取此方法的 ETS 类型。
- **PSMemberInfo**属性：获取**PSMethod**对象。

## <a name="script-methods"></a>脚本方法

脚本方法是在 PowerShell 语言中定义的扩展成员。 它为基本对象上定义的方法提供了类似的功能;但是，可以将脚本方法动态添加到**PSObject**对象。 可以通过提供以下公共方法和属性的[PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod)对象来访问这些方法。

- `PSScriptMethod.Copy`方法：创建**PSScriptMethod**对象的精确副本。
- `PSScriptMethod.Invoke(System.Object[])`方法：调用基础脚本方法。
- `PSScriptMethod.ToString`方法：将**PSScriptMethod**对象转换为字符串。
- **PSMemberInfo. IsInstance**属性：获取指示成员源的**布尔**值。
- **PSScriptMethod. MemberType**属性：获取用于将此方法标识为脚本方法的**PSMemberTypes。**
- **PSMemberInfo.Name**属性：获取基础代码方法的名称。
- **PSScriptMethod. OverloadDefinitions**属性：获取基础脚本方法的所有重载的定义。
- **PSScriptMethod. TypeNameOfValue**属性：获取此方法的 ETS 类型。
- **PSScriptMethod**属性：获取用于调用方法的脚本。
- **PSMemberInfo**属性：获取**PSScriptMethod**对象。
