---
description: 启动 PowerShell 时，通知用户已发布新版本的 PowerShell。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: ea6b768ef62679ee039b156b72e69a7ba240389f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200032"
---
# <a name="about-update-notifications"></a>关于更新通知

## <a name="short-description"></a>简短说明

启动 PowerShell 时，通知用户已发布新版本的 PowerShell。

## <a name="long-description"></a>详细说明

从 PowerShell 7.0 开始，PowerShell 使用更新通知来提醒用户是否存在 PowerShell 更新。 PowerShell 每天查询一次联机服务，以确定是否提供较新版本。

> [!NOTE]
> 虽然在给定的24小时内第一次会话期间进行更新检查，但出于性能原因，该通知仅会显示在后续会话开始时。 此外，出于性能方面的考虑，在会话开始之前至少3秒钟后，检查才会开始。

默认情况下，PowerShell 订阅两个不同通知通道之一，具体取决于其版本/分支。 受支持的正式发布 (GA) 版 PowerShell 仅返回已更新 GA 版本的通知。 预览版和候选发布 (RC) 版本会通知预览版、RC 和 GA 版本的更新。

可以使用 `POWERSHELL_UPDATECHECK` 环境变量更改更新通知行为。 支持以下值：

- `Off` 关闭更新通知功能
- `Default` 与不定义相同 `POWERSHELL_UPDATECHECK` ：
  - GA 版本通知 GA 版本的更新
  - 预览版/RC 版本通知 GA 版本和预览版的更新
- `LTS` 仅通知长期服务 (LTS) GA 版本的更新

以下终结点当前用于确定每个通道的最新版本：

- `LTS`: https://aka.ms/pwsh-buildinfo-lts
- `Stable`: https://aka.ms/pwsh-buildinfo-stable
- `Preview`: https://aka.ms/pwsh-buildinfo-preview

更新通知并不提供自动更新 PowerShell 的任何方式。 将来，可能有更多指令或功能可从 PowerShell 内部更新，但目前，你应该使用用于安装 PowerShell 的相同安装机制来更新它。
