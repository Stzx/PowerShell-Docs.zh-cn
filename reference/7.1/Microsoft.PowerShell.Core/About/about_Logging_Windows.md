---
description: PowerShell 将引擎、提供程序和 cmdlet 的内部操作记录到 Windows 事件日志中。
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_windows?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging-Windows
ms.openlocfilehash: 960394838097e4bfad1af5f4f0af7a813a50e761
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355011"
---
# <a name="about-logging-windows"></a><span data-ttu-id="e0ad2-104">关于日志记录窗口</span><span class="sxs-lookup"><span data-stu-id="e0ad2-104">About Logging Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="e0ad2-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="e0ad2-105">Short description</span></span>
<span data-ttu-id="e0ad2-106">PowerShell 将引擎、提供程序和 cmdlet 的内部操作记录到 Windows 事件日志中。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-106">PowerShell logs internal operations from the engine, providers, and cmdlets to the Windows event log.</span></span>

## <a name="long-description"></a><span data-ttu-id="e0ad2-107">长说明</span><span class="sxs-lookup"><span data-stu-id="e0ad2-107">Long description</span></span>

<span data-ttu-id="e0ad2-108">PowerShell 记录有关 PowerShell 操作的详细信息，例如启动和停止引擎和提供程序，以及执行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="e0ad2-109">Windows PowerShell 版本3.0、4.0、5.0 和5.1 包含 Windows 事件日志的 **事件** 日志 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="e0ad2-110">在这些版本中，若要显示 **EventLog** cmdlet 的列表，请键入： `Get-Command -Noun EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="e0ad2-111">有关详细信息，请参阅你的 Windows PowerShell 版本的 cmdlet 文档和 about_EventLogs。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="e0ad2-112">查看 Windows 上的 PowerShell 事件日志条目</span><span class="sxs-lookup"><span data-stu-id="e0ad2-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="e0ad2-113">可以使用 Windows 事件查看器查看 PowerShell 日志。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="e0ad2-114">事件日志位于 "应用程序" 和 "服务日志" 组中，并命名为 `PowerShellCore` 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-114">The event log is located in the Application and Services Logs group and is named `PowerShellCore`.</span></span> <span data-ttu-id="e0ad2-115">关联的 ETW 提供程序 `GUID` 为 `{f90714a8-5509-434a-bf6d-b1624c8a19a2}` 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-115">The associated ETW provider `GUID` is `{f90714a8-5509-434a-bf6d-b1624c8a19a2}`.</span></span>

<span data-ttu-id="e0ad2-116">启用脚本块日志记录时，PowerShell 会将以下事件记录到 `PowerShellCore/Operational` 日志中：</span><span class="sxs-lookup"><span data-stu-id="e0ad2-116">When Script Block Logging is enabled, PowerShell logs the following events to the `PowerShellCore/Operational` log:</span></span>

|  <span data-ttu-id="e0ad2-117">字段</span><span class="sxs-lookup"><span data-stu-id="e0ad2-117">Field</span></span>  |       <span data-ttu-id="e0ad2-118">值</span><span class="sxs-lookup"><span data-stu-id="e0ad2-118">Value</span></span>       |
| ------- | ----------------- |
| <span data-ttu-id="e0ad2-119">EventId</span><span class="sxs-lookup"><span data-stu-id="e0ad2-119">EventId</span></span> | `4104` / `0x1008` |
| <span data-ttu-id="e0ad2-120">Channel</span><span class="sxs-lookup"><span data-stu-id="e0ad2-120">Channel</span></span> | `Operational`     |
| <span data-ttu-id="e0ad2-121">级别</span><span class="sxs-lookup"><span data-stu-id="e0ad2-121">Level</span></span>   | `Verbose`         |
| <span data-ttu-id="e0ad2-122">操作码</span><span class="sxs-lookup"><span data-stu-id="e0ad2-122">Opcode</span></span>  | `Create`          |
| <span data-ttu-id="e0ad2-123">任务</span><span class="sxs-lookup"><span data-stu-id="e0ad2-123">Task</span></span>    | `CommandStart`    |
| <span data-ttu-id="e0ad2-124">关键字</span><span class="sxs-lookup"><span data-stu-id="e0ad2-124">Keyword</span></span> | `Runspace`        |

### <a name="registering-the-powershell-event-provider-on-windows"></a><span data-ttu-id="e0ad2-125">在 Windows 上注册 PowerShell 事件提供程序</span><span class="sxs-lookup"><span data-stu-id="e0ad2-125">Registering the PowerShell event provider on Windows</span></span>

<span data-ttu-id="e0ad2-126">与 Linux 或 macOS 不同，Windows 要求先注册事件提供程序，然后才能将事件写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-126">Unlike Linux or macOS, Windows requires the event provider to be registered before events can be written to the event log.</span></span> <span data-ttu-id="e0ad2-127">若要启用 PowerShell 事件提供程序，请从提升的 PowerShell 提示符中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-127">To enable the PowerShell event provider, run the following command from an elevated PowerShell prompt.</span></span>

```powershell
$PSHOME\RegisterManifest.ps1
```

### <a name="unregistering-the-powershell-event-provider-on-windows"></a><span data-ttu-id="e0ad2-128">在 Windows 上注销 PowerShell 事件提供程序</span><span class="sxs-lookup"><span data-stu-id="e0ad2-128">Unregistering the PowerShell event provider on Windows</span></span>

<span data-ttu-id="e0ad2-129">注册事件提供程序会在用于对事件进行解码的二进制库中放置锁。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-129">Registering the event provider places a lock in the binary library used to decode events.</span></span> <span data-ttu-id="e0ad2-130">若要更新此库，必须取消注册该提供程序以释放此锁定。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-130">To update this library, the provider must be unregistered to release this lock.</span></span>

<span data-ttu-id="e0ad2-131">若要注销 PowerShell 提供程序，请从提升的 PowerShell 提示符中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-131">To unregister the PowerShell provider, run the following command from an elevated PowerShell prompt.</span></span>

```powershell
$PSHOME\RegisterManifest.ps1 -Unregister
```

<span data-ttu-id="e0ad2-132">更新 PowerShell 后，运行 `$PSHOME\RegisterManifest.ps1` 以注册更新的事件提供程序。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-132">After updating PowerShell, run `$PSHOME\RegisterManifest.ps1` to register the updated event provider.</span></span>

## <a name="enabling-script-block-logging"></a><span data-ttu-id="e0ad2-133">启用脚本块日志记录</span><span class="sxs-lookup"><span data-stu-id="e0ad2-133">Enabling Script Block Logging</span></span>

<span data-ttu-id="e0ad2-134">启用脚本块日志记录时，PowerShell 将记录其处理的所有脚本块的内容。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-134">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="e0ad2-135">启用后，任何新的 PowerShell 会话都将记录此信息。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-135">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="e0ad2-136">如果使用脚本块日志记录作为诊断目的以外的任何内容，则建议启用受保护的事件日志记录，如下所述。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-136">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="e0ad2-137">可以通过组策略或注册表设置来启用脚本块日志记录。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-137">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="e0ad2-138">使用组策略</span><span class="sxs-lookup"><span data-stu-id="e0ad2-138">Using Group Policy</span></span>

<span data-ttu-id="e0ad2-139">若要启用自动脚本，请 `Turn on PowerShell Script Block
Logging` 在组策略中启用该功能 `Administrative Templates -> Windows
Components -> Windows PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-139">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="e0ad2-140">使用注册表</span><span class="sxs-lookup"><span data-stu-id="e0ad2-140">Using the Registry</span></span>

<span data-ttu-id="e0ad2-141">运行以下函数：</span><span class="sxs-lookup"><span data-stu-id="e0ad2-141">Run the following function:</span></span>

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

## <a name="protected-event-logging"></a><span data-ttu-id="e0ad2-142">受保护的事件日志记录</span><span class="sxs-lookup"><span data-stu-id="e0ad2-142">Protected Event Logging</span></span>

<span data-ttu-id="e0ad2-143">提高系统日志记录的级别，可以提高记录的内容可能包含敏感数据的可能性。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-143">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="e0ad2-144">例如，启用脚本日志记录后，可以将脚本使用的凭据或其他敏感数据写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-144">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="e0ad2-145">当包含记录的敏感数据的计算机受到威胁时，日志可以为攻击者提供扩展其范围所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-145">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="e0ad2-146">为了保护此信息，Windows 10 引入了受保护的事件日志记录。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-146">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="e0ad2-147">受保护的事件日志记录使参与的应用程序可以加密写入事件日志的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-147">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="e0ad2-148">稍后，你可以通过更安全且集中的日志收集器来解密和处理这些日志。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-148">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="e0ad2-149">使用 IETF 加密消息语法 (CMS) 标准保护事件日志内容。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-149">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="e0ad2-150">CMS 使用公钥加密。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-150">CMS uses public key cryptography.</span></span> <span data-ttu-id="e0ad2-151">用于对内容进行加密和解密的密钥保持独立。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-151">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="e0ad2-152">公钥可以广泛共享，并且不是敏感数据。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-152">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="e0ad2-153">使用此公钥加密的任何内容只能通过私钥进行解密。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-153">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="e0ad2-154">有关公钥加密的详细信息，请参阅 [维基百科-公钥加密](https://en.wikipedia.org/wiki/Public-key_cryptography)。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-154">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="e0ad2-155">若要启用受保护的事件日志记录策略，请将一个公钥部署到具有要保护的事件日志数据的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-155">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="e0ad2-156">对应的私钥用于在更安全的位置（如中心事件日志收集器或 [SIEM][] 聚合器）后处理事件日志。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-156">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="e0ad2-157">可以在 Azure 中设置 SIEM。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-157">You can set up SIEM in Azure.</span></span> <span data-ttu-id="e0ad2-158">有关详细信息，请参阅 [通用 SIEM 集成](/cloud-app-security/siem)。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-158">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="e0ad2-159">通过组策略启用受保护的事件日志记录</span><span class="sxs-lookup"><span data-stu-id="e0ad2-159">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="e0ad2-160">若要启用受保护的事件日志记录，请 `Enable Protected Event Logging` 在组策略中启用该功能 `Administrative Templates -> Windows Components
-> Event Logging` 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-160">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="e0ad2-161">此设置需要一个加密证书，你可以使用以下几种形式之一提供该证书：</span><span class="sxs-lookup"><span data-stu-id="e0ad2-161">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="e0ad2-162">64编码的 x.509 证书的内容 (例如，如 `Export` 证书管理器) 中的选项所提供的那样。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-162">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="e0ad2-163">可在本地计算机证书存储 (中找到的证书的指纹，可通过 PKI 基础结构) 部署。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-163">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="e0ad2-164">证书的完整路径 (可以是本地的，也可以是远程共享) 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-164">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="e0ad2-165">包含证书的目录的路径或证书 (可以是本地的，也可以是远程共享) 。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-165">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="e0ad2-166">可在本地计算机证书存储 (中找到的证书的使用者名称，可通过 PKI 基础结构) 部署。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-166">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="e0ad2-167">生成的证书必须具有 `Document Encryption` () 的增强型密钥用法 `1.3.6.1.4.1.311.80.1` ，并 `Data Encipherment` 启用或 `Key
Encipherment` 启用密钥用法。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-167">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="e0ad2-168">不应将私钥部署到计算机日志记录事件。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-168">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="e0ad2-169">应将其保存在一个安全的位置，以便对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-169">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="e0ad2-170">解密受保护的事件日志记录消息</span><span class="sxs-lookup"><span data-stu-id="e0ad2-170">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="e0ad2-171">下面的脚本将检索并解密，前提是你有私钥：</span><span class="sxs-lookup"><span data-stu-id="e0ad2-171">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="e0ad2-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ad2-172">See also</span></span>

[<span data-ttu-id="e0ad2-173">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="e0ad2-173">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="e0ad2-174">向蓝色团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0ad2-174">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="e0ad2-175">通用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="e0ad2-175">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
<span data-ttu-id="e0ad2-176">SIEM</span><span class="sxs-lookup"><span data-stu-id="e0ad2-176">[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management</span></span>
