---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198080"
---
# New-WebServiceProxy

## 摘要
创建一个 Web 服务代理对象，用于在 PowerShell 中使用和管理 Web 服务。

## SYNTAX

### NoCredentials（默认值）

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### 凭据

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### UseDefaultCredential

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## DESCRIPTION

`New-WebServiceProxy`Cmdlet 可让你在 PowerShell 中使用 Web 服务。 Cmdlet 连接到 Web 服务，并在 PowerShell 中创建 Web 服务代理对象。 你可以使用代理对象管理 Web 服务。

Web 服务是一种基于 XML 的程序，它通过网络（特别是 Internet）来交换数据。 Microsoft .NET Framework 提供了将 Web 服务表示为 .NET Framework 对象的 Web 服务代理对象。

## 示例

### 示例1：创建 Web 服务的代理

此示例在 Windows PowerShell 中创建计算器 Web 服务的 .NET Framework 代理。

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### 示例2：创建 Web 服务的代理并指定命名空间和类

此示例使用 `New-WebServiceProxy` cmdlet 创建计算器 Web 服务的 .NET Framework 代理。

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

该命令使用 **uri** 参数指定 uri，并使用 **namespace** 和 **class** 参数指定对象的命名空间和类。

### 示例3：显示 Web 服务代理的方法

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

此示例使用 `Get-Member` cmdlet 来显示变量中 Web 服务代理对象的方法 `$calc` 。 在下面的示例中，我们使用这些方法。

请注意，代理对象 New-webserviceproxy 的 **TypeName** 反映了上一示例中指定的命名空间和类名。

### 示例4：使用 Web 服务代理

```powershell
PS> $calc.Multiply(6,7)
42
```

此示例使用存储在变量中的 Web 服务代理 `$calc` 。 该命令使用代理的 **乘法** 方法。

## PARAMETERS

### -Class

指定该 cmdlet 为 Web 服务创建的代理类的名称。 此参数的值与 **Namespace** 参数一起使用，为类提供完全限定的名称。 默认值是从统一资源标识符 (URI) 生成的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认为当前用户。 这是使用 **UseDefaultCredential** 参数的替代方法。

键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。 键入用户名时，此 cmdlet 会提示输入密码。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

指定新类的命名空间。

此参数的值与 **class** 参数的值一起使用，以生成该类的完全限定名称。 默认值为 **microsoft.powershell.commands.newwebserviceproxy.autogeneratedtypes. microsoft.powershell.commands.newwebserviceproxy.autogeneratedtypes 和** 加上从 URI 生成的类型。

你可以设置 **Namespace** 参数的值，以便可以访问具有相同名称的多个 Web 服务。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri

指定 Web 服务的 URI。 输入 URI 或包含服务说明的文件的路径和文件名。

URI 必须返回 `.asmx` 页面或返回服务说明的页面。 若要返回使用 ASP.NET 创建的 Web 服务的服务说明，请追加 "？WSDL "到 Web 服务的 URL (例如， `http://www.contoso.com/MyWebService.asmx?WSDL`) 。

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredential

指示此 cmdlet 使用默认凭据。 此 cmdlet 将生成的代理对象中的 **UseDefaultCredential** 属性设置为 True。 这是使用 **Credential** 参数的替代方法。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给此 cmdlet。

## 输出

### Web 服务代理对象

此 cmdlet 将返回一个 Web 服务代理对象。 该对象的命名空间和类由该命令的参数确定。 默认值是从输入 URI 生成的。

## 注释

`New-WebServiceProxy` 使用 **系统 .net** node.js 类加载指定的 Web services。

## 相关链接

[New-Service](New-Service.md)
