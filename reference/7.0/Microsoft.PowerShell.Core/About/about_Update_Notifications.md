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
# <a name="about-update-notifications"></a><span data-ttu-id="6d0ac-104">关于更新通知</span><span class="sxs-lookup"><span data-stu-id="6d0ac-104">About Update Notifications</span></span>

## <a name="short-description"></a><span data-ttu-id="6d0ac-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="6d0ac-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6d0ac-106">启动 PowerShell 时，通知用户已发布新版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-106">Notifies users on startup of PowerShell that a new version of PowerShell has been released.</span></span>

## <a name="long-description"></a><span data-ttu-id="6d0ac-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="6d0ac-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6d0ac-108">从 PowerShell 7.0 开始，PowerShell 使用更新通知来提醒用户是否存在 PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-108">Beginning with PowerShell 7.0, PowerShell uses update notifications to alert users to the existence of updates to PowerShell.</span></span> <span data-ttu-id="6d0ac-109">PowerShell 每天查询一次联机服务，以确定是否提供较新版本。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-109">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="6d0ac-110">虽然在给定的24小时内第一次会话期间进行更新检查，但出于性能原因，该通知仅会显示在后续会话开始时。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-110">While the update check happens during the first session in a given 24-hour period, for performance reasons, the notification will only be shown on the start of subsequent sessions.</span></span> <span data-ttu-id="6d0ac-111">此外，出于性能方面的考虑，在会话开始之前至少3秒钟后，检查才会开始。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-111">Also for performance reasons, the check will not start until at least 3 seconds after the session begins.</span></span>

<span data-ttu-id="6d0ac-112">默认情况下，PowerShell 订阅两个不同通知通道之一，具体取决于其版本/分支。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-112">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="6d0ac-113">受支持的正式发布 (GA) 版 PowerShell 仅返回已更新 GA 版本的通知。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-113">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="6d0ac-114">预览版和候选发布 (RC) 版本会通知预览版、RC 和 GA 版本的更新。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-114">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="6d0ac-115">可以使用 `POWERSHELL_UPDATECHECK` 环境变量更改更新通知行为。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-115">The update notification behavior can be changed using the `POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="6d0ac-116">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="6d0ac-116">The following values are supported:</span></span>

- <span data-ttu-id="6d0ac-117">`Off` 关闭更新通知功能</span><span class="sxs-lookup"><span data-stu-id="6d0ac-117">`Off` turns off the update notification feature</span></span>
- <span data-ttu-id="6d0ac-118">`Default` 与不定义相同 `POWERSHELL_UPDATECHECK` ：</span><span class="sxs-lookup"><span data-stu-id="6d0ac-118">`Default` is the same as not defining `POWERSHELL_UPDATECHECK`:</span></span>
  - <span data-ttu-id="6d0ac-119">GA 版本通知 GA 版本的更新</span><span class="sxs-lookup"><span data-stu-id="6d0ac-119">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="6d0ac-120">预览版/RC 版本通知 GA 版本和预览版的更新</span><span class="sxs-lookup"><span data-stu-id="6d0ac-120">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="6d0ac-121">`LTS` 仅通知长期服务 (LTS) GA 版本的更新</span><span class="sxs-lookup"><span data-stu-id="6d0ac-121">`LTS` only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

<span data-ttu-id="6d0ac-122">以下终结点当前用于确定每个通道的最新版本：</span><span class="sxs-lookup"><span data-stu-id="6d0ac-122">The following endpoints are currently used for determining the latest version of each channel:</span></span>

- <span data-ttu-id="6d0ac-123">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span><span class="sxs-lookup"><span data-stu-id="6d0ac-123">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span></span>
- <span data-ttu-id="6d0ac-124">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span><span class="sxs-lookup"><span data-stu-id="6d0ac-124">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span></span>
- <span data-ttu-id="6d0ac-125">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span><span class="sxs-lookup"><span data-stu-id="6d0ac-125">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span></span>

<span data-ttu-id="6d0ac-126">更新通知并不提供自动更新 PowerShell 的任何方式。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-126">The update notification doesn't provide any way to automatically update PowerShell.</span></span> <span data-ttu-id="6d0ac-127">将来，可能有更多指令或功能可从 PowerShell 内部更新，但目前，你应该使用用于安装 PowerShell 的相同安装机制来更新它。</span><span class="sxs-lookup"><span data-stu-id="6d0ac-127">In the future, there may be more instructions or capabilities to update from within PowerShell, but today, you should use the same install mechanism you used to install PowerShell to update it.</span></span>
