---
title: 在 Cmdlet 中调用 Cmdlet 和脚本 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d5f76242c02763c41b81215bbb031e19869066a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786571"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>调用 Cmdlet 中的 Cmdlet 和脚本

Cmdlet 可以从 cmdlet 的输入处理方法中调用其他 cmdlet 和脚本。 这样，便可以将现有 cmdlet 和脚本的功能添加到 cmdlet，而无需重写代码。

## <a name="the-invoke-method"></a>Invoke 方法

所有 cmdlet 都可以通过从 cmdlet 重写的输入处理方法中调用[BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)方法来调用现有的 cmdlet，例如，该 cmdlet 会重写[此方法。](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) 但是，你只能调用直接从[system.web](/dotnet/api/System.Management.Automation.Cmdlet)类派生的 cmdlet。 不能调用派生自[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)类的 cmdlet。

" [System.object](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) " 方法具有以下变体。

。[调用](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)此变体将调用 Cmdlet 对象，并返回 "T" 类型对象的集合。

。[调用](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)此变体将调用 Cmdlet 对象并返回强类型化的 emumerator。 此变体允许用户使用集合中的对象执行自定义操作。

## <a name="examples"></a>示例

|示例|说明|
|-------------|-----------------|
|[在 Cmdlet 中调用 Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|此示例演示如何从另一个 cmdlet 中调用 cmdlet。|
|[在 Cmdlet 中调用脚本](./how-to-invoke-scripts-within-a-cmdlet.md)|此示例演示如何从另一个 cmdlet 中调用提供给 cmdlet 的脚本。|

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
