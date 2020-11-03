---
description: 说明 windows PowerShell 4.0 在 Windows RT 8.1 上的限制。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200039"
---
# <a name="about-windows-rt"></a>关于 Windows RT

## <a name="short-description"></a>简短说明

说明 windows PowerShell 4.0 在 Windows RT 8.1 上的限制。

## <a name="long-description"></a>详细说明

Windows RT 8.1 操作系统安装在 (（如 Microsoft Surface 2）上的计算机和设备上，在这种情况下，它是随计算机一起提供的操作系统) 使用高级 RISC 计算机 (ARM) 处理器。

Windows PowerShell 4.0 包含在 Windows RT 8.1 中。 所有适用于 Windows PowerShell 2.0 和更高版本的 cmdlet、提供程序、模块和大多数脚本都在 Windows RT 8.1 上运行，无需更改。

因为 Windows RT 8.1 不包含所有 Windows 功能，所以，某些 Windows PowerShell 功能的工作方式不同或在基于 Windows RT 的设备上不起作用。 下表说明了这些差异。

- Windows PowerShell ISE 不包含在中，并且无法在 Windows RT 8.1 上运行。
  Windows PowerShell ISE 需要 Windows Presentation Foundation，但不包括在 Windows RT 8.1 中。

- 默认情况下，Windows PowerShell 远程处理和 WinRM 服务处于禁用状态。
  若要启用远程处理，请运行 Enable-PSRemoting cmdlet。 同时，运行 Set-Service cmdlet 将 WinRM 服务的启动类型设置为 "自动" 或 "自动 (延迟启动) "。

  当远程处理处于禁用状态时，你可以使用 Windows PowerShell 远程处理在其他计算机上运行命令，但其他计算机无法在 Windows RT 设备上运行命令。 此外，隐式远程处理-即，内置到 cmdlet 或脚本中的远程处理，并且未使用添加的参数显式请求
  - 不适用于在 Windows RT 8.1 上运行的 Windows PowerShell。

- Windows RT 8.1 不支持已加入域的计算和 Kerberos 身份验证。 不能使用 Windows PowerShell 添加或管理这些功能。

- Windows rt 8.1 8.1 上的 Windows PowerShell 中也不支持 Windows RT 不支持 Microsoft .NET 框架类。

- 在 Windows RT 8.1 上不启用事务。 事务 cmdlet （如 Start Transaction 和 transaction 参数，如 UseTransaction）不能正常工作。

- Windows RT 8.1 设备上的所有 Windows PowerShell 会话都使用 ConstrainedLanguage 语言模式。 ConstrainedLanguage 语言模式是用户模式代码完整性的伴随 (UMCI) 。 它允许所有 Windows cmdlet 和 Windows PowerShell 语言元素，但会限制类型，以确保用户无法使用 Windows PowerShell 来绕过或违反 UMCI 保护。

有关 ConstrainedLanguage 语言模式的详细信息，请参阅 [about_Language_Modes](about_Language_Modes.md)。

## <a name="see-also"></a>另请参阅

[about_Language_Modes](about_Language_Modes.md)

[about_Remote](about_Remote.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)
