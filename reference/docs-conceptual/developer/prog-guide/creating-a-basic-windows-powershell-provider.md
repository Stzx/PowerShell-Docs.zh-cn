---
ms.date: 09/13/2016
ms.topic: reference
title: 创建基础 Windows PowerShell 提供程序
description: 创建基础 Windows PowerShell 提供程序
ms.openlocfilehash: 03b5784fd063b5457fc64d92a32e286e3bf9cce4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647509"
---
# <a name="creating-a-basic-windows-powershell-provider"></a>创建基础 Windows PowerShell 提供程序

本主题是学习如何创建 Windows PowerShell 提供程序的起点。 此处所述的基本提供程序提供了启动和停止提供程序的方法，但尽管此提供程序不提供访问数据存储或获取或设置数据存储中的数据的方法，但它确实提供了所有提供程序所需的基本功能。

如前所述，此处所述的基本提供程序实现了用于启动和停止提供程序的方法。 Windows PowerShell 运行时调用这些方法来初始化和取消初始化提供程序。

> [!NOTE]
> 可在 Windows PowerShell 提供的 AccessDBSampleProvider01.cs 文件中找到该提供程序的示例。

## <a name="defining-the-windows-powershell-provider-class"></a>定义 Windows PowerShell 提供程序类

创建 Windows PowerShell 提供程序的第一步是定义其 .NET 类。 此基本提供程序定义了一个名为 `AccessDBProvider` 的类，该类派生自 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 基类。

建议将提供程序类放在 `Providers` API 命名空间的命名空间中，例如，xxx。 此提供程序使用 `Microsoft.Samples.PowerShell.Provider` 命名空间，在该命名空间中运行所有 Windows PowerShell 提供程序示例。

> [!NOTE]
> Windows PowerShell 提供程序的类必须显式标记为公共。 未标记为 "公共" 的类将默认为内部类，且不会由 Windows PowerShell 运行时找到。

下面是该基本提供程序的类定义：

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="23-24":::

在类定义之前，必须用语法 [CmdletProvider ( # A1] 来声明 [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 属性，然后才能定义。

如有必要，可以设置属性关键字以进一步声明该类。 请注意，此处声明的 [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 特性包括两个参数。 第一个 attribute 参数指定提供程序的默认友好名称，用户可以在以后修改该名称。 第二个参数指定 Windows PowerShell 定义的功能，提供程序在命令处理过程中将这些功能公开给 Windows PowerShell 运行时。 提供程序功能的可能值是由 [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举定义的。 因为这是一个基本提供程序，所以它不支持任何功能。

> [!NOTE]
> Windows PowerShell 提供程序的完全限定名称包括在注册提供程序时由 Windows PowerShell 确定的程序集名称和其他属性。

## <a name="defining-provider-specific-state-information"></a>定义 Provider-Specific 状态信息

由于 Windows PowerShell 运行时仅根据需要创建提供程序实例，因此 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 基类和所有派生类均被视为无状态。 因此，如果提供程序需要完全控制和状态维护特定于提供程序的数据，则必须从 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 类派生一个类。 派生类应定义维护状态所需的成员，以便在 Windows PowerShell 运行时调用 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法来初始化提供程序时可以访问提供程序特定的数据。

Windows PowerShell 提供程序也可以维护基于连接的状态。 有关维护连接状态的详细信息，请参阅 [创建 PowerShell 驱动器提供程序](./creating-a-windows-powershell-drive-provider.md)。

## <a name="initializing-the-provider"></a>正在初始化提供程序

若要初始化该访问接口，Windows powershell 运行时将在启动 Windows PowerShell 时调用 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法。 大多数情况下，提供程序可以使用此方法的默认实现，该实现只返回描述提供程序的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象。 但是，如果你想要添加更多的初始化信息，你应该实现你自己的 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法，该方法将返回传递给你的提供程序的已修改版本的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象。 通常，此方法应返回传递给它的所提供的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象或包含其他初始化信息的修改后的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象。

此基本提供程序不重写此方法。 但是，以下代码显示了此方法的默认实现：

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

提供程序可以维护特定于提供程序的信息的状态，如 [定义特定于提供程序的数据状态](#defining-provider-specific-state-information)中所述。 在这种情况下，您的实现必须重写 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法才能返回派生类的实例。

## <a name="start-dynamic-parameters"></a>启动动态参数

你的 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法的提供程序实现可能需要其他参数。 在这种情况下，提供程序应重写 [Cmdletprovider. Startdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) 方法，并返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。

此基本提供程序不重写此方法。 但是，以下代码显示了此方法的默认实现：

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a>取消初始化提供程序

为了释放 Windows PowerShell 提供程序使用的资源，提供程序应实现其自己的 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) 方法。 Windows PowerShell 运行时调用此方法，以便在会话关闭时对提供程序进行初始化。

此基本提供程序不重写此方法。 但是，以下代码显示了此方法的默认实现：

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a>代码示例

有关完整的示例代码，请参阅 [AccessDbProviderSample01 代码示例](./accessdbprovidersample01-code-sample.md)。

## <a name="testing-the-windows-powershell-provider"></a>测试 Windows PowerShell 提供程序

Windows PowerShell 提供程序注册到 Windows PowerShell 后，可以通过在命令行上运行支持的 cmdlet 来对其进行测试。 对于此基本提供程序，请运行新的 shell 并使用 `Get-PSProvider` cmdlet 来检索提供程序列表，并确保存在 AccessDb 提供程序。

```powershell
Get-PSProvider
```

随即显示以下输出：

```Output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a>另请参阅

[创建 Windows PowerShell 提供程序](./how-to-create-a-windows-powershell-provider.md)

[设计 Windows PowerShell 提供程序](./designing-your-windows-powershell-provider.md)
