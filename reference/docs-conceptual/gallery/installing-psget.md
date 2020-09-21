---
ms.date: 09/19/2019
contributor: manikb
keywords: 库,powershell,cmdlet,psget
title: 安装 PowerShellGet
ms.openlocfilehash: 4a10699be9ff2b64e5848c6749bdd3dedf55e3c7
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162505"
---
# <a name="installing-powershellget"></a>安装 PowerShellGet

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet 是以下版本的随机模块

- [Windows 10](https://www.microsoft.com/windows) 或更高版本
- [Windows Server 2016](/windows-server/windows-server) 或更高版本
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 或更高版本
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a>从 PowerShell 库获取最新版本

更新 PowerShellGet 前，应始终安装最新的 NuGet 提供程序。 在提升的 PowerShell 会话中运行以下命令。

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>对于使用 PowerShell 5.0（或更高版本）的系统，可以安装最新的 PowerShellGet

若要在 Windows 10、Windows Server 2016、任何安装了 WMF 5.0 或 5.1 的系统或任何安装了 PowerShell 6 的系统上安装 PowerShellGet，请通过提升的 PowerShell 会话运行以下命令。

```powershell
Install-Module -Name PowerShellGet -Force
```

使用 `Update-Module` 获取更高版本。

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a>对于运行 PowerShell 3.0 或 PowerShell 4.0 的计算机

这些说明适用于已安装 **PackageManagement 预览版**或未安装任何版本的 **PowerShellGet** 的计算机。

两组指令都使用 `Save-Module` cmdlet。 `Save-Module` 从已注册的存储库下载并保存模块和所有依赖项。 模块的最新版本已保存到本地计算机上的指定路径，但尚未安装。 要在 PowerShell 3.0 或 4.0 中安装模块，请将已保存模块的文件夹复制到 `$env:ProgramFiles\WindowsPowerShell\Modules`。

有关详细信息，请参阅 [Save-Module](/powershell/module/PowershellGet/Save-Module)。

> [!NOTE]
> PowerShell 3.0 和 PowerShell 4.0 仅支持一种模块版本。 从 PowerShell 5.0 开始，模块安装在 `<modulename>\<version>` 中。 这使你能够并行安装多个版本。 使用 `Save-Module` 下载模块后，必须将 `<modulename>\<version>` 中的文件复制到目标计算机上的 `<modulename>` 文件夹中，如以下说明所示。

#### <a name="preparatory-step-on-computers-running-powershell-30"></a>运行 PowerShell 3.0 的计算机上的准备步骤

以下各节将介绍如何在目录 `$env:ProgramFiles\WindowsPowerShell\Modules` 中安装模块。
在 PowerShell 3.0 中，默认情况下此目录未在 `$env:PSModulePath` 中列出，因此你需要添加它，才能自动加载模块。 

打开提升的 PowerShell 会话并运行以下命令（在未来的会话中将生效）：

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>安装了 PackageManagement 预览版的计算机

> [!NOTE] 
> PackageManagement 预览版是一个可下载的组件，可使 PowerShellGet 用于 PowerShell 版本 3 和 4，但现在不再可用。
> 若要测试是否已在指定计算机上安装该组件，请运行 `Get-Module -ListAvailable PowerShellGet`。

1. 从 PowerShell 会话中，使用 `Save-Module` 下载当前版本的 PowerShellGet。 已下载两个文件夹：**PowerShellGet** 和 **PackageManagement**。 每个文件夹包含一个带有版本号的子文件夹。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. 确保未在其他任何进程中加载 PowerShellGet 和 PackageManagement 模块 。

1. 使用提升的权限重新打开 PowerShell 控制台，并运行以下命令。

   ```powershell
   'PowerShellGet', 'PackageManagement' | % { 
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a>没有 PowerShellGet 的计算机

对于未安装任何版本的 PowerShellGet 的计算机（使用 `Get-Module -ListAvailable PowerShellGet` 测试），需要使用安装了 PowerShellGet 的计算机来下载模块 。

1. 在安装了 **PowerShellGet** 的计算机上，使用 `Save-Module` 下载 **PowerShellGet** 的最新版本。 已下载两个文件夹：**PowerShellGet** 和 **PackageManagement**。 每个文件夹包含一个带有版本号的子文件夹。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. 将 PowerShellGet 和 PackageManagement 文件夹中相应的 `<version>` 子文件夹分别复制到未安装 PowerShellGet 的计算机的 `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` 和 `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` 文件夹中，这需要提升的会话  。
   
1. 例如，如果你可以访问其他计算机上的下载文件夹（如 `ws1`），请通过 UNC 路径（如 `\\ws1\C$\LocalFolder`）从目标计算机打开具有提升权限的 PowerShell 控制台并运行以下命令：

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
