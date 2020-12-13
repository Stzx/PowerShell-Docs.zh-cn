---
ms.date: 09/13/2016
ms.topic: reference
title: 必需的开发指南
description: 必需的开发指南
ms.openlocfilehash: 98db075b314eb7f54f2deb56022799d9f830f9ef
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655755"
---
# <a name="required-development-guidelines"></a>必需的开发指南

编写 cmdlet 时必须遵循以下准则。 它们分为准则，用于设计 cmdlet 以及编写 cmdlet 代码的准则。 如果未遵循这些指导原则，则 cmdlet 可能会失败，并且你的用户在使用 cmdlet 时可能会遇到不佳的体验。

## <a name="in-this-topic"></a>主题内容

### <a name="design-guidelines"></a>设计准则

- [仅使用批准的动词 (RD01) ](./required-development-guidelines.md#use-only-approved-verbs-rd01)

- [Cmdlet 名称：不能 (RD02 使用的字符) ](./required-development-guidelines.md#cmdlet-names-characters-that-cannot-be-used-rd02)

- [不能 (RD03 使用的参数名称) ](./required-development-guidelines.md#parameters-names-that-cannot-be-used-rd03)

- [ (RD04) 支持确认请求 ](./required-development-guidelines.md#support-confirmation-requests-rd04)

- [ (RD05) 的交互式会话支持强制参数 ](./required-development-guidelines.md#support-force-parameter-for-interactive-sessions-rd05)

- [ (RD06 的文档输出对象) ](./required-development-guidelines.md#document-output-objects-rd06)

### <a name="code-guidelines"></a>代码准则

- [从 Cmdlet 或 PSCmdlet 类派生 (RC01) ](./required-development-guidelines.md#derive-from-the-cmdlet-or-pscmdlet-classes-rc01)

- [ (RC02 指定 Cmdlet 特性) ](./required-development-guidelines.md#specify-the-cmdlet-attribute-rc02)

- [重写输入处理方法 (RC03) ](./required-development-guidelines.md#override-an-input-processing-method-rc03)

- [ (RC04 指定 OutputType 特性) ](./required-development-guidelines.md#specify-the-outputtype-attribute-rc04)

- [请勿保留 (RC05 的输出对象的句柄) ](./required-development-guidelines.md#do-not-retain-handles-to-output-objects-rc05)

- [ (RC06) 可靠地处理错误 ](./required-development-guidelines.md#handle-errors-robustly-rc06)

- [使用 Windows PowerShell 模块 (RC07 部署 Cmdlet) ](./required-development-guidelines.md#use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07)

## <a name="design-guidelines"></a>设计准则

设计 cmdlet 时必须遵循以下指导原则，以确保在使用 cmdlet 和其他 cmdlet 之间保持一致的用户体验。 如果找到适用于你的情况的设计准则，请务必查看类似准则的代码准则。

### <a name="use-only-approved-verbs-rd01"></a>仅使用批准的动词 (RD01) 

Cmdlet 属性中指定的动词必须来自 Windows PowerShell 提供的已识别的动词集。 它不得为禁止的同义词之一。 使用以下枚举定义的常量字符串指定 cmdlet 谓词：

- [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)

- [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)

- [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)

- [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

- [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

- [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)

- [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)

有关已批准的动词名称的详细信息，请参阅 [Cmdlet 谓词](./approved-verbs-for-windows-powershell-commands.md)。

用户需要一组可发现的和预期的 cmdlet 名称。 使用适当的动词，使用户能够快速评估 cmdlet 的作用，并轻松发现系统功能。 例如，以下命令行命令将获取系统上名称以 "start" 开头的所有命令的列表： `get-command start-*` 。 在 cmdlet 中使用名词，将 cmdlet 与其他 cmdlet 区分开来。 名词指示将对其执行操作的资源。 操作本身由谓词表示。

### <a name="cmdlet-names-characters-that-cannot-be-used-rd02"></a>Cmdlet 名称：不能 (RD02 使用的字符) 

命名 cmdlet 时，请不要使用以下任何特殊字符。

|字符|名称|
|---------------|----------|
|#|数字符号|
|,|逗号|
|()|括号|
|{}|住|
|[]|方括号|
|&|前面|
|-|连字符 **注意：**  可以使用连字符分隔名词中的动词，但不能在名词内或动词内使用它。|
|/|斜杠标记|
|\\| 反斜杠|
|$|美元符号|
|^|caret|
|;|分号|
|:|开头|
|"|双引号|
|'|单引号|
|<>|尖括号|
|&#124;|竖线|
|?|问号|
|@|at 符号|
|`|反向计时 (重音符) |
|*|星号|
|%|百分号|
|+|加号|
|=|等号|
|~|波浪|

### <a name="parameters-names-that-cannot-be-used-rd03"></a>不能 (RD03 使用的参数名称) 

Windows PowerShell 为所有 cmdlet 提供了一个通用参数，以及在特定情况下添加的附加参数。 设计自己的 cmdlet 时，不能使用以下名称： Confirm、Debug、ErrorAction、ErrorVariable、OutBuffer、OutVariable、WarningAction、WarningVariable、WhatIf、UseTransaction 和 Verbose。 有关这些参数的详细信息，请参阅 [通用参数名称](./common-parameter-names.md)。

### <a name="support-confirmation-requests-rd04"></a> (RD04) 支持确认请求

对于执行修改系统的操作的 cmdlet，这些 cmdlet 应调用 [ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法来请求确认，在特殊情况下，调用 [ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 方法中的方法来调用。  (，则应仅在调用[ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法之后调用[ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法。 ) 的方法是，则为。

若要进行这些调用，cmdlet 必须指定它支持确认请求，方法是设置 `SupportsShouldProcess` cmdlet 属性的关键字。 有关设置此属性的详细信息，请参阅 [Cmdlet 特性声明](./cmdlet-attribute-declaration.md)。

> [!NOTE]
> 如果 cmdlet 类的 Cmdlet 特性指示该 cmdlet 支持对 [ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法的调用，并且该 cmdlet 无法对 [ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法进行调用，则用户可能会意外地修改该系统。请注意，用户可能会意外地修改系统。

对于任何系统修改，请使用 [ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法。 用户首选项和参数，用于 `WhatIf` 控制 [ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法。 与此相反， [ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 调用会执行其他检查，以检查是否存在潜在的危险修改。 此方法不由任何用户首选项或参数控制 `WhatIf` 。 如果你的 cmdlet 调用 [ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 方法，则它应具有一个 `Force` 参数，该参数会绕过对这两个方法的调用，并继续执行该操作。 这一点很重要，因为它允许在非交互式脚本和主机中使用 cmdlet。

如果 cmdlet 支持这些调用，则用户可以确定是否应实际执行该操作。 例如，在停止一组关键进程（包括系统、Winlogon 和 Spoolsv.exe 进程）之前， [停止进程](/powershell/module/microsoft.powershell.management/stop-process) cmdlet 会调用 [ShouldContinue *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 方法。

有关支持这些方法的详细信息，请参阅 [请求确认](./requesting-confirmation-from-cmdlets.md)。

### <a name="support-force-parameter-for-interactive-sessions-rd05"></a> (RD05) 的交互式会话支持强制参数

如果 cmdlet 以交互方式使用，请始终提供 Force 参数来重写交互式操作，如提示或读取输入) 的行。 这一点很重要，因为它允许在非交互式脚本和主机中使用 cmdlet。 交互式主机可以实现以下方法。

- [PSHostUserInterface * 的命令行管理](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.Prompt)

- [Pshostuserinterface. "PromptForChoice"](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForChoice)

- [Ihostuisupportsmultiplechoiceselection. "PromptForChoice"](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection.PromptForChoice)

- [PromptForCredential * 的 Pshostuserinterface *。](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForCredential)

- [Pshostuserinterface * 的功能的 *](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLine)

- [ReadLineAsSecureString * 的 Pshostuserinterface *。](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLineAsSecureString)

### <a name="document-output-objects-rd06"></a> (RD06 的文档输出对象) 

Windows PowerShell 使用写入管道的对象。 为了使用户能够利用每个 cmdlet 返回的对象，你必须记录返回的对象，并且必须记录这些返回对象的成员的用途。

## <a name="code-guidelines"></a>代码准则

编写 cmdlet 代码时必须遵循以下准则。 如果你发现适用于你的情况的代码准则，请务必查看类似指导原则的设计指南。

### <a name="derive-from-the-cmdlet-or-pscmdlet-classes-rc01"></a>从 Cmdlet 或 PSCmdlet 类派生 (RC01) 

Cmdlet 必须派生自[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) [基类或派生](/dotnet/api/System.Management.Automation.Cmdlet)自的派生类的派生类。 派生自 [system.object](/dotnet/api/System.Management.Automation.Cmdlet) 类的 cmdlet 不依赖于 Windows PowerShell 运行时。 可以直接从任何 Microsoft .NET Framework 语言调用它们。 派生自 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 类的 cmdlet 依赖于 Windows PowerShell 运行时。 因此，它们在运行空间内执行。

实现的所有 cmdlet 类必须是公共类。 有关这些 cmdlet 类的详细信息，请参阅 [Cmdlet 概述](./cmdlet-overview.md)。

### <a name="specify-the-cmdlet-attribute-rc02"></a> (RC02 指定 Cmdlet 特性) 

要使 cmdlet 能够被 Windows PowerShell 识别，其 .NET Framework 类必须使用 Cmdlet 特性修饰。 此属性指定 cmdlet 的以下功能。

- 用于标识 cmdlet 的动词和名词对。

- 指定多个参数集时使用的默认参数集。 当 Windows PowerShell 没有足够的信息来确定要使用的参数时，将使用默认参数集。

- 指示此 cmdlet 是否支持对 [ShouldProcess *](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法的调用。 此方法在 cmdlet 更改系统之前向用户显示一条确认消息。 有关如何发出确认请求的详细信息，请参阅 [请求确认](./requesting-confirmation-from-cmdlets.md)。

- 指示与确认消息相关联的操作的影响级别 (或严重性) 。 在大多数情况下，应使用默认值 "中"。 有关影响级别如何影响向用户显示的确认请求的详细信息，请参阅 [请求确认](./requesting-confirmation-from-cmdlets.md)。

有关如何声明 cmdlet 特性的详细信息，请参阅 [CmdletAttribute 声明](./cmdlet-attribute-declaration.md)。

### <a name="override-an-input-processing-method-rc03"></a>重写输入处理方法 (RC03) 

要使 cmdlet 参与 Windows PowerShell 环境，必须重写以下 *输入处理方法* 中的至少一个。

[BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 此方法被调用一次，并且它用于提供处理前功能的情况。

[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 此方法被调用多次，并用于提供按记录提供的功能，则为。

[System.web. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 此方法被调用一次，并且用于提供后处理功能的功能。

### <a name="specify-the-outputtype-attribute-rc04"></a> (RC04 指定 OutputType 特性) 

Windows PowerShell 2.0 中引入的 OutputType 属性 () 指定 cmdlet 返回给管道的 .NET Framework 类型。 通过指定 cmdlet 的输出类型，可使 cmdlet 返回的对象更容易被其他 cmdlet 发现。 有关修饰具有此属性的 cmdlet 类的详细信息，请参阅 [OutputType 特性声明](./outputtype-attribute-declaration.md)。

### <a name="do-not-retain-handles-to-output-objects-rc05"></a>请勿保留 (RC05 的输出对象的句柄) 

你的 cmdlet 不应将任何句柄保留到传递给 [WriteObject *](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 方法的对象。 这些对象将传递到管道中的下一个 cmdlet，或者由脚本使用。 如果保留对象的句柄，则两个实体将拥有每个对象，这将导致错误。

### <a name="handle-errors-robustly-rc06"></a> (RC06) 可靠地处理错误

管理环境在本质上检测并对所管理的系统进行重要更改。 因此，cmdlet 会正确处理错误，这一点非常重要。 有关错误记录的详细信息，请参阅 [Windows PowerShell 错误报告](./error-reporting-concepts.md)。

- 当错误阻止某个 cmdlet 继续处理任何其他记录时，它是终止错误。 该 cmdlet 必须调用 [ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) 方法，该方法引用了 [ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) 对象的目标系统。 如果 cmdlet 未捕获到异常，Windows PowerShell 运行时本身将引发包含较少信息的终止错误。

- 对于非终止错误，该错误不会停止对来自管道的下一条记录的操作 (例如，由不同进程) 生成的记录），该 cmdlet 必须调用引用 ErrorRecord 对象的[WriteError *](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法（该方法称为[](/dotnet/api/System.Management.Automation.ErrorRecord)对象）。 非终止错误的一个示例是特定进程无法停止时出现的错误。 通过调用 [WriteError *](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 方法，用户可以持续执行请求的操作，并保留失败的特定操作的信息。 你的 cmdlet 应尽可能独立地处理每条记录。

- [ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)和[WriteError *](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法所引用的[ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)对象在其核心中需要异常。 "的核心中，它需要一个例外。"）。 确定要使用的异常时，请遵循 .NET Framework 设计准则。 如果错误在语义上与现有异常相同，请使用该异常或从该异常派生。 否则，直接从 [system.exception 类型派生](/dotnet/api/System.Exception) 新的异常或异常层次结构。

[ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)对象还需要一个为用户分组错误的错误类别。 用户可以通过将 shell 变量的值设置为 CategoryView，查看基于类别的错误 `$ErrorView` 。 可能的类别由 [ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory) 枚举来定义。

- 如果 cmdlet 创建新线程，并且在该线程中运行的代码引发未处理的异常，则 Windows PowerShell 将不会捕获该错误，将终止该进程。

- 如果对象在其析构函数中包含导致未经处理的异常的代码，则 Windows PowerShell 将不会捕获该错误，将终止该进程。 如果对象调用导致未经处理的异常的 Dispose 方法，也会发生这种情况。

### <a name="use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07"></a>使用 Windows PowerShell 模块 (RC07 部署 Cmdlet) 

创建用于打包和部署 cmdlet 的 Windows PowerShell 模块。 Windows PowerShell 2.0 中引入了对模块的支持。 你可以使用包含 cmdlet 类的程序集直接作为二进制模块文件 (这在) 测试 cmdlet 时非常有用，或者你可以创建引用 cmdlet 程序集的模块清单。  (你还可以在使用模块时添加现有的管理单元程序集。 ) 有关模块的详细信息，请参阅 [编写 Windows PowerShell 模块](../module/writing-a-windows-powershell-module.md)。

## <a name="see-also"></a>另请参阅

[强烈建议的开发指南](./strongly-encouraged-development-guidelines.md)

[咨询性的开发指南](./advisory-development-guidelines.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
