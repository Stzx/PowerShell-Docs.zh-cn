---
ms.date: 09/19/2019
contributor: manikb
keywords: 库,powershell,cmdlet,psget
title: 安装 PowerShellGet
ms.openlocfilehash: f42eb0df101eb63a5dc267196fa9f666747b8e35
ms.sourcegitcommit: 23ea4a36ee85f923684657de5313a5adf0b6b094
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83727789"
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
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>对于使用 PowerShell 5.0（或更高版本）的系统，可以安装最新的 PowerShellGet

若要在 Windows 10、Windows Server 2016、任何安装了 WMF 5.0 或 5.1 的系统或任何安装了 PowerShell 6 的系统上安装 PowerShellGet，请通过提升的 PowerShell 会话运行以下命令。

```powershell
Install-Module -Name PowerShellGet -Force
Exit
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
> PowerShell 3.0 和 PowerShell 4.0 仅支持一种模块版本。 从 PowerShell 5.0 开始，模块安装在 `<modulename>\<version>` 中。 这使你能够并行安装多个版本。 使用 `Save-Module` 下载模块后，必须将 `<modulename>\<version>` 中的文件复制到目标计算机上的 `<modulename>` 文件夹中。

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>安装了 PackageManagement 预览版的计算机

1. 在 PowerShell 会话中，使用 `Save-Module` 将模块保存到本地目录。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. 确保未在其他任何进程中加载 PowerShellGet 和 PackageManagement 模块 。
1. 删除文件夹的内容：`$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` 和 `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`。
1. 使用提升的权限重新打开 PowerShell 控制台，并运行以下命令。

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a>没有 PowerShellGet 的计算机

对于未安装任何版本的 **PowerShellGet** 的计算机，需要使用安装了 **PowerShellGet** 的计算机来下载模块。

1. 在安装了 **PowerShellGet** 的计算机上，使用 `Save-Module` 下载 **PowerShellGet** 的最新版本。 已下载两个文件夹：**PowerShellGet** 和 **PackageManagement**。 每个文件夹包含一个带有版本号的子文件夹。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. 将 **PowerShellGet** 和 **PackageManagement** 文件夹复制到未安装 **PowerShellGet** 的计算机上。

   目标目录为：`$env:ProgramFiles\WindowsPowerShell\Modules`
