---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 类声明
description: Cmdlet 类声明
ms.openlocfilehash: 854b0a4ca9f6c87c4fad3b71ee726beade585e02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653493"
---
# <a name="cmdlet-class-declaration"></a>Cmdlet 类声明

通过将 **cmdlet** 特性指定为类的元数据，将 Microsoft .NET 框架类声明为 cmdlet。  (**cmdlet** 特性是所有 cmdlet) 唯一必需的属性。
指定 **cmdlet** 属性时，必须指定用于向用户标识 Cmdlet 的动词和名词对。 并且，你必须描述 cmdlet 支持的 Windows PowerShell 功能。 有关用于指定 **cmdlet** 特性的声明语法的详细信息，请参阅 [cmdlet 特性声明](./cmdlet-attribute-declaration.md)。

> [!NOTE]
> 该 **Cmdlet** 特性由 [CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) 类定义。） 此类的属性对应于声明特性时使用的声明参数。

## <a name="nouns"></a>名词

Cmdlet 的名词指定该 cmdlet 操作的资源。 名词将 cmdlet 与其他 cmdlet 区分开来。

Cmdlet 名称中的名词必须是特定的，如果是泛型名词（如 *server*），最好添加一个短前缀，将资源与其他类似资源区分开来。 例如，包含带有前缀的名词的 cmdlet 名称是 `Get-SQLServer` 。 将特定名词与更通用的动词组合后，用户可以通过其操作快速找到 cmdlet，然后通过其资源确定 cmdlet，同时避免不必要的 cmdlet 名称重复。

有关不能在 cmdlet 名称中使用的特殊字符列表，请参阅 [所需的开发指南](./required-development-guidelines.md)。

## <a name="verbs"></a>动词

指定谓词后，开发指南需要使用 Windows PowerShell 提供的一个预定义谓词。 通过使用其中一个预定义的动词，你将确保你编写的 cmdlet 与 Microsoft 和其他用户编写的 cmdlet 之间的一致性。 例如，"Get" 谓词用于检索数据的 cmdlet。

有关谓词准则的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。 有关不能在 cmdlet 名称中使用的特殊字符列表，请参阅 [所需的开发指南](./required-development-guidelines.md)。

## <a name="supporting-windows-powershell-functionality"></a>支持 Windows PowerShell 功能

**Cmdlet** 属性还允许你指定 Cmdlet 支持 Windows PowerShell 提供的某些常见功能。 这包括对常见功能的支持，例如用户反馈确认 (称为支持 ShouldProcess 功能) 和支持事务。 Windows PowerShell 2.0) 中引入了 (对事务的支持。

有关用于指定 **cmdlet** 特性的声明语法的详细信息，请参阅 [cmdlet 特性声明](./cmdlet-attribute-declaration.md)。

## <a name="cmdlet-class-definition"></a>Cmdlet 类定义

下面的代码是 GetProc cmdlet 类的定义。 请注意，使用了 Pascal 大小写，并且类的名称包含 cmdlet 的动词和名词。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="33-34":::

## <a name="pascal-casing"></a>Pascal 大小写

命名 cmdlet 时，请使用 Pascal 大小写。 例如，在 `Get-Item` `Get-ItemProperty` 命名 cmdlet 时，和 cmdlet 会显示正确使用大小写的方式。

## <a name="see-also"></a>另请参阅

[System.web. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)

[CmdletAttribute 声明](./cmdlet-attribute-declaration.md)

[Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
