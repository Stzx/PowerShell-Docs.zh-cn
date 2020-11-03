---
description: PowerShell 记录来自引擎、提供程序和 cmdlet 的内部操作。
keywords: powershell
Locale: en-US
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging
ms.openlocfilehash: 5d061b38b5b0fa45cf0a86c2f5b7e0efcb8d1f7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200106"
---
# <a name="about-logging"></a><span data-ttu-id="35eae-104">关于日志记录</span><span class="sxs-lookup"><span data-stu-id="35eae-104">About Logging</span></span>

## <a name="short-description"></a><span data-ttu-id="35eae-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="35eae-105">Short description</span></span>

<span data-ttu-id="35eae-106">PowerShell 记录来自引擎、提供程序和 cmdlet 的内部操作。</span><span class="sxs-lookup"><span data-stu-id="35eae-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="35eae-107">长说明</span><span class="sxs-lookup"><span data-stu-id="35eae-107">Long description</span></span>

<span data-ttu-id="35eae-108">PowerShell 记录有关 PowerShell 操作的详细信息，例如启动和停止引擎和提供程序，以及执行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="35eae-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="35eae-109">Windows PowerShell 版本3.0、4.0、5.0 和5.1 包含 Windows 事件日志的 **事件** 日志 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="35eae-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="35eae-110">在这些版本中，若要显示 **EventLog** cmdlet 的列表，请键入： `Get-Command -Noun EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="35eae-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="35eae-111">有关详细信息，请参阅你的 Windows PowerShell 版本的 cmdlet 文档和 about_EventLogs。</span><span class="sxs-lookup"><span data-stu-id="35eae-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="35eae-112">查看 Windows 上的 PowerShell 事件日志条目</span><span class="sxs-lookup"><span data-stu-id="35eae-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="35eae-113">可以使用 Windows 事件查看器查看 PowerShell 日志。</span><span class="sxs-lookup"><span data-stu-id="35eae-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="35eae-114">事件日志位于 "应用程序" 和 "服务日志" 组中，并命名为 `Microsoft-Windows-PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="35eae-114">The event log is located in the Application and Services Logs group and is named `Microsoft-Windows-PowerShell`.</span></span> <span data-ttu-id="35eae-115">关联的 ETW 提供程序 `GUID` 为 `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}` 。</span><span class="sxs-lookup"><span data-stu-id="35eae-115">The associated ETW provider `GUID` is `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}`.</span></span>

<span data-ttu-id="35eae-116">启用脚本块日志记录时，PowerShell 会将以下事件记录到 `Microsoft-Windows-PowerShell/Operational` 日志中：</span><span class="sxs-lookup"><span data-stu-id="35eae-116">When Script Block Logging is enabled, PowerShell logs the following events to the `Microsoft-Windows-PowerShell/Operational` log:</span></span>

|<span data-ttu-id="35eae-117">字段</span><span class="sxs-lookup"><span data-stu-id="35eae-117">Field</span></span>| <span data-ttu-id="35eae-118">值</span><span class="sxs-lookup"><span data-stu-id="35eae-118">Value</span></span>|
|-|-|
|<span data-ttu-id="35eae-119">EventId</span><span class="sxs-lookup"><span data-stu-id="35eae-119">EventId</span></span>|`4104` / `0x1008`|
|<span data-ttu-id="35eae-120">通道</span><span class="sxs-lookup"><span data-stu-id="35eae-120">Channel</span></span>|`Operational`|
|<span data-ttu-id="35eae-121">Level</span><span class="sxs-lookup"><span data-stu-id="35eae-121">Level</span></span>|`Verbose`|
|<span data-ttu-id="35eae-122">操作码</span><span class="sxs-lookup"><span data-stu-id="35eae-122">Opcode</span></span>|`Create`|
|<span data-ttu-id="35eae-123">任务</span><span class="sxs-lookup"><span data-stu-id="35eae-123">Task</span></span>|`CommandStart`|
|<span data-ttu-id="35eae-124">关键字</span><span class="sxs-lookup"><span data-stu-id="35eae-124">Keyword</span></span>|`Runspace`|

## <a name="enabling-script-block-logging"></a><span data-ttu-id="35eae-125">启用脚本块日志记录</span><span class="sxs-lookup"><span data-stu-id="35eae-125">Enabling Script Block Logging</span></span>

<span data-ttu-id="35eae-126">启用脚本块日志记录时，PowerShell 将记录其处理的所有脚本块的内容。</span><span class="sxs-lookup"><span data-stu-id="35eae-126">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="35eae-127">启用后，任何新的 PowerShell 会话都将记录此信息。</span><span class="sxs-lookup"><span data-stu-id="35eae-127">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="35eae-128">如果使用脚本块日志记录作为诊断目的以外的任何内容，则建议启用受保护的事件日志记录，如下所述。</span><span class="sxs-lookup"><span data-stu-id="35eae-128">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="35eae-129">可以通过组策略或注册表设置来启用脚本块日志记录。</span><span class="sxs-lookup"><span data-stu-id="35eae-129">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="35eae-130">使用组策略</span><span class="sxs-lookup"><span data-stu-id="35eae-130">Using Group Policy</span></span>

<span data-ttu-id="35eae-131">若要启用自动脚本，请 `Turn on PowerShell Script Block
Logging` 在组策略中启用该功能 `Administrative Templates -> Windows
Components -> Windows PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="35eae-131">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="35eae-132">使用注册表</span><span class="sxs-lookup"><span data-stu-id="35eae-132">Using the Registry</span></span>

<span data-ttu-id="35eae-133">运行以下函数：</span><span class="sxs-lookup"><span data-stu-id="35eae-133">Run the following function:</span></span>

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a><span data-ttu-id="35eae-134">受保护的事件日志记录</span><span class="sxs-lookup"><span data-stu-id="35eae-134">Protected Event Logging</span></span>

<span data-ttu-id="35eae-135">提高系统日志记录的级别，可以提高记录的内容可能包含敏感数据的可能性。</span><span class="sxs-lookup"><span data-stu-id="35eae-135">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="35eae-136">例如，启用脚本日志记录后，可以将脚本使用的凭据或其他敏感数据写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="35eae-136">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="35eae-137">当包含记录的敏感数据的计算机受到威胁时，日志可以为攻击者提供扩展其范围所需的信息。</span><span class="sxs-lookup"><span data-stu-id="35eae-137">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="35eae-138">为了保护此信息，Windows 10 引入了受保护的事件日志记录。</span><span class="sxs-lookup"><span data-stu-id="35eae-138">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="35eae-139">受保护的事件日志记录使参与的应用程序可以加密写入事件日志的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="35eae-139">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="35eae-140">稍后，你可以通过更安全且集中的日志收集器来解密和处理这些日志。</span><span class="sxs-lookup"><span data-stu-id="35eae-140">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="35eae-141">使用 IETF 加密消息语法 (CMS) 标准保护事件日志内容。</span><span class="sxs-lookup"><span data-stu-id="35eae-141">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="35eae-142">CMS 使用公钥加密。</span><span class="sxs-lookup"><span data-stu-id="35eae-142">CMS uses public key cryptography.</span></span> <span data-ttu-id="35eae-143">用于对内容进行加密和解密的密钥保持独立。</span><span class="sxs-lookup"><span data-stu-id="35eae-143">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="35eae-144">公钥可以广泛共享，并且不是敏感数据。</span><span class="sxs-lookup"><span data-stu-id="35eae-144">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="35eae-145">使用此公钥加密的任何内容只能通过私钥进行解密。</span><span class="sxs-lookup"><span data-stu-id="35eae-145">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="35eae-146">有关公钥加密的详细信息，请参阅 [维基百科-公钥加密](https://en.wikipedia.org/wiki/Public-key_cryptography)。</span><span class="sxs-lookup"><span data-stu-id="35eae-146">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="35eae-147">若要启用受保护的事件日志记录策略，请将一个公钥部署到具有要保护的事件日志数据的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="35eae-147">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="35eae-148">对应的私钥用于在更安全的位置（如中心事件日志收集器或 [SIEM][] 聚合器）后处理事件日志。</span><span class="sxs-lookup"><span data-stu-id="35eae-148">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="35eae-149">可以在 Azure 中设置 SIEM。</span><span class="sxs-lookup"><span data-stu-id="35eae-149">You can set up SIEM in Azure.</span></span> <span data-ttu-id="35eae-150">有关详细信息，请参阅 [通用 SIEM 集成](/cloud-app-security/siem)。</span><span class="sxs-lookup"><span data-stu-id="35eae-150">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="35eae-151">通过组策略启用受保护的事件日志记录</span><span class="sxs-lookup"><span data-stu-id="35eae-151">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="35eae-152">若要启用受保护的事件日志记录，请 `Enable Protected Event Logging` 在组策略中启用该功能 `Administrative Templates -> Windows Components
-> Event Logging` 。</span><span class="sxs-lookup"><span data-stu-id="35eae-152">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="35eae-153">此设置需要一个加密证书，你可以使用以下几种形式之一提供该证书：</span><span class="sxs-lookup"><span data-stu-id="35eae-153">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="35eae-154">64编码的 x.509 证书的内容 (例如，如 `Export` 证书管理器) 中的选项所提供的那样。</span><span class="sxs-lookup"><span data-stu-id="35eae-154">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="35eae-155">可在本地计算机证书存储 (中找到的证书的指纹，可通过 PKI 基础结构) 部署。</span><span class="sxs-lookup"><span data-stu-id="35eae-155">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="35eae-156">证书的完整路径 (可以是本地的，也可以是远程共享) 。</span><span class="sxs-lookup"><span data-stu-id="35eae-156">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="35eae-157">包含证书的目录的路径或证书 (可以是本地的，也可以是远程共享) 。</span><span class="sxs-lookup"><span data-stu-id="35eae-157">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="35eae-158">可在本地计算机证书存储 (中找到的证书的使用者名称，可通过 PKI 基础结构) 部署。</span><span class="sxs-lookup"><span data-stu-id="35eae-158">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="35eae-159">生成的证书必须具有 `Document Encryption` () 的增强型密钥用法 `1.3.6.1.4.1.311.80.1` ，并 `Data Encipherment` 启用或 `Key
Encipherment` 启用密钥用法。</span><span class="sxs-lookup"><span data-stu-id="35eae-159">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="35eae-160">不应将私钥部署到计算机日志记录事件。</span><span class="sxs-lookup"><span data-stu-id="35eae-160">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="35eae-161">应将其保存在一个安全的位置，以便对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="35eae-161">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="35eae-162">解密受保护的事件日志记录消息</span><span class="sxs-lookup"><span data-stu-id="35eae-162">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="35eae-163">下面的脚本将检索并解密，前提是你有私钥：</span><span class="sxs-lookup"><span data-stu-id="35eae-163">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="35eae-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35eae-164">See also</span></span>

[<span data-ttu-id="35eae-165">向蓝色团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="35eae-165">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="35eae-166">通用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="35eae-166">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
<span data-ttu-id="35eae-167">SIEM</span><span class="sxs-lookup"><span data-stu-id="35eae-167">[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management</span></span>
