---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 6f98c95e6c0144f76393e9d28454833097894512
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197860"
---
# <span data-ttu-id="a43bf-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="a43bf-103">Send-MailMessage</span></span>

## <span data-ttu-id="a43bf-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a43bf-104">SYNOPSIS</span></span>
<span data-ttu-id="a43bf-105">发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a43bf-105">Sends an email message.</span></span>

## <span data-ttu-id="a43bf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a43bf-106">SYNTAX</span></span>

### <span data-ttu-id="a43bf-107">全部</span><span class="sxs-lookup"><span data-stu-id="a43bf-107">All</span></span>

```
Send-MailMessage [-To] <string[]> [-Subject] <string> [[-Body] <string>] [[-SmtpServer] <string>]
 -From <string> [-Attachments <string[]>] [-Bcc <string[]>] [-BodyAsHtml] [-Encoding <Encoding>]
 [-Cc <string[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 [-Priority <MailPriority>] [-Credential <pscredential>] [-UseSsl] [-Port <int>]
 [<CommonParameters>]
```

## <span data-ttu-id="a43bf-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a43bf-108">DESCRIPTION</span></span>

<span data-ttu-id="a43bf-109">`Send-MailMessage`Cmdlet 可从 PowerShell 内部发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a43bf-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="a43bf-110">必须 (SMTP) 服务器指定简单邮件传输协议，否则命令将 `Send-MailMessage` 失败。</span><span class="sxs-lookup"><span data-stu-id="a43bf-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="a43bf-111">使用 **SmtpServer** 参数或将变量设置 `$PSEmailServer` 为有效的 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="a43bf-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="a43bf-112">分配给的值 `$PSEmailServer` 是 PowerShell 的默认 SMTP 设置。</span><span class="sxs-lookup"><span data-stu-id="a43bf-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="a43bf-113">有关详细信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="a43bf-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="a43bf-114">`Send-MailMessage`Cmdlet 已过时。</span><span class="sxs-lookup"><span data-stu-id="a43bf-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="a43bf-115">此 cmdlet 不保证与 SMTP 服务器的安全连接。</span><span class="sxs-lookup"><span data-stu-id="a43bf-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="a43bf-116">虽然 PowerShell 中没有即时替换，但建议你不要使用 `Send-MailMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="a43bf-117">有关详细信息，请参阅 [平台兼容性说明 DE0005](https://aka.ms/SendMailMessage)。</span><span class="sxs-lookup"><span data-stu-id="a43bf-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="a43bf-118">示例</span><span class="sxs-lookup"><span data-stu-id="a43bf-118">EXAMPLES</span></span>

### <span data-ttu-id="a43bf-119">示例1：向其他人发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a43bf-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="a43bf-120">此示例将一封电子邮件发送给其他人。</span><span class="sxs-lookup"><span data-stu-id="a43bf-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="a43bf-121">需要使用 **From** 、 **To** 和 **Subject** 参数 `Send-MailMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="a43bf-122">此示例使用 `$PSEmailServer` SMTP 服务器的默认变量，因此不需要 **SmtpServer** 参数。</span><span class="sxs-lookup"><span data-stu-id="a43bf-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="a43bf-123">`Send-MailMessage`Cmdlet 使用 **From** 参数来指定消息的发送方。</span><span class="sxs-lookup"><span data-stu-id="a43bf-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="a43bf-124">**To** 参数指定消息的接收方。</span><span class="sxs-lookup"><span data-stu-id="a43bf-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="a43bf-125">**Subject** 参数使用文本字符串 **测试邮件** 作为消息，因为不包括可选的 **Body** 参数。</span><span class="sxs-lookup"><span data-stu-id="a43bf-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="a43bf-126">示例2：发送附件</span><span class="sxs-lookup"><span data-stu-id="a43bf-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="a43bf-127">此示例发送一封电子邮件，其中包含附件。</span><span class="sxs-lookup"><span data-stu-id="a43bf-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="a43bf-128">`Send-MailMessage`Cmdlet 使用 **From** 参数来指定消息的发送方。</span><span class="sxs-lookup"><span data-stu-id="a43bf-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="a43bf-129">**To** 参数指定邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="a43bf-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="a43bf-130">**Subject** 参数描述消息的内容。</span><span class="sxs-lookup"><span data-stu-id="a43bf-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="a43bf-131">**Body** 参数是消息的内容。</span><span class="sxs-lookup"><span data-stu-id="a43bf-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="a43bf-132">**附件** 参数指定附加到电子邮件的当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="a43bf-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="a43bf-133">**Priority** 参数将消息设置为 **高** 优先级。</span><span class="sxs-lookup"><span data-stu-id="a43bf-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="a43bf-134">**-DeliveryNotificationOption** 参数指定了两个值： **OnSuccess** 和 **OnFailure** 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure** .</span></span> <span data-ttu-id="a43bf-135">发件人将收到电子邮件通知，以确认消息传递的成功或失败。</span><span class="sxs-lookup"><span data-stu-id="a43bf-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="a43bf-136">**SmtpServer** 参数将 SMTP 服务器设置为 **smtp.fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com** .</span></span>

### <span data-ttu-id="a43bf-137">示例3：向邮件列表发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a43bf-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="a43bf-138">此示例向邮件列表发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a43bf-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="a43bf-139">`Send-MailMessage`Cmdlet 使用 **From** 参数来指定消息的发送方。</span><span class="sxs-lookup"><span data-stu-id="a43bf-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="a43bf-140">**To** 参数指定邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="a43bf-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="a43bf-141">**Cc** 参数将消息的副本发送到指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="a43bf-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="a43bf-142">**Bcc** 参数发送邮件的直接副本。</span><span class="sxs-lookup"><span data-stu-id="a43bf-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="a43bf-143">直接副本是隐藏在其他收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a43bf-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="a43bf-144">**Subject** 参数是消息，因为不包括可选的 **Body** 参数。</span><span class="sxs-lookup"><span data-stu-id="a43bf-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="a43bf-145">**Credential** 参数指定用于发送消息的域管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="a43bf-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="a43bf-146">**UseSsl** 参数指定安全套接字层 (SSL) 创建安全连接。</span><span class="sxs-lookup"><span data-stu-id="a43bf-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="a43bf-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a43bf-147">PARAMETERS</span></span>

### <span data-ttu-id="a43bf-148">-Attachments</span><span class="sxs-lookup"><span data-stu-id="a43bf-148">-Attachments</span></span>

<span data-ttu-id="a43bf-149">指定要附加到电子邮件的文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="a43bf-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="a43bf-150">可以使用此参数或通过管道将路径和文件名传递给 `Send-MailMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-151">-Bcc</span><span class="sxs-lookup"><span data-stu-id="a43bf-151">-Bcc</span></span>

<span data-ttu-id="a43bf-152">指定接收邮件副本但未列为邮件收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a43bf-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="a43bf-153">输入名称 (可选) 和电子邮件地址，如 `Name <someone@fabrikam.com>` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-154">-Body</span><span class="sxs-lookup"><span data-stu-id="a43bf-154">-Body</span></span>

<span data-ttu-id="a43bf-155">指定电子邮件的内容。</span><span class="sxs-lookup"><span data-stu-id="a43bf-155">Specifies the content of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-156">-BodyAsHtml</span><span class="sxs-lookup"><span data-stu-id="a43bf-156">-BodyAsHtml</span></span>

<span data-ttu-id="a43bf-157">指定 **Body** 参数的值包含 HTML。</span><span class="sxs-lookup"><span data-stu-id="a43bf-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-158">-Cc</span><span class="sxs-lookup"><span data-stu-id="a43bf-158">-Cc</span></span>

<span data-ttu-id="a43bf-159">指定电子邮件的抄送 (CC) 发送到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a43bf-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="a43bf-160">输入名称 (可选) 和电子邮件地址，如 `Name <someone@fabrikam.com>` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="a43bf-161">-Credential</span></span>

<span data-ttu-id="a43bf-162">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a43bf-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="a43bf-163">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="a43bf-163">The default is the current user.</span></span>

<span data-ttu-id="a43bf-164">键入用户名，如 **User01** 或 **Domain01\User01** 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-164">Type a user name, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="a43bf-165">或者输入 **PSCredential** 对象，例如 cmdlet 中的一个 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="a43bf-166">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="a43bf-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a43bf-167">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="a43bf-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-168">-DeliveryNotificationOption</span><span class="sxs-lookup"><span data-stu-id="a43bf-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="a43bf-169">指定电子邮件的送达通知选项。</span><span class="sxs-lookup"><span data-stu-id="a43bf-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="a43bf-170">你可以指定多个值。</span><span class="sxs-lookup"><span data-stu-id="a43bf-170">You can specify multiple values.</span></span>
<span data-ttu-id="a43bf-171">None 为默认值。</span><span class="sxs-lookup"><span data-stu-id="a43bf-171">None is the default value.</span></span> <span data-ttu-id="a43bf-172">此参数的别名为 **DNO** 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-172">The alias for this parameter is **DNO** .</span></span>

<span data-ttu-id="a43bf-173">送达通知将发送到 **From** 参数中的地址。</span><span class="sxs-lookup"><span data-stu-id="a43bf-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="a43bf-174">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="a43bf-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a43bf-175">`None`：无通知。</span><span class="sxs-lookup"><span data-stu-id="a43bf-175">`None`: No notification.</span></span>
- <span data-ttu-id="a43bf-176">`OnSuccess`：通知传送是否成功。</span><span class="sxs-lookup"><span data-stu-id="a43bf-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="a43bf-177">`OnFailure`：通知传送是否失败。</span><span class="sxs-lookup"><span data-stu-id="a43bf-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="a43bf-178">`Delay`：通知传送是否已延迟。</span><span class="sxs-lookup"><span data-stu-id="a43bf-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="a43bf-179">`Never`：从不通知。</span><span class="sxs-lookup"><span data-stu-id="a43bf-179">`Never`: Never notify.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-180">-Encoding</span><span class="sxs-lookup"><span data-stu-id="a43bf-180">-Encoding</span></span>

<span data-ttu-id="a43bf-181">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="a43bf-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="a43bf-182">默认值是 `Default`。</span><span class="sxs-lookup"><span data-stu-id="a43bf-182">The default value is `Default`.</span></span>

<span data-ttu-id="a43bf-183">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="a43bf-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a43bf-184">`ASCII` 使用 ASCII (7 位) 字符集。</span><span class="sxs-lookup"><span data-stu-id="a43bf-184">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="a43bf-185">`BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="a43bf-185">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="a43bf-186">`Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-186">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="a43bf-187">`OEM` 使用与系统的当前 OEM 代码页相对应的编码。</span><span class="sxs-lookup"><span data-stu-id="a43bf-187">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="a43bf-188">`Unicode` 使用带有小 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="a43bf-188">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="a43bf-189">`UTF7` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="a43bf-189">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="a43bf-190">`UTF8` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="a43bf-190">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="a43bf-191">`UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="a43bf-191">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-192">-From</span><span class="sxs-lookup"><span data-stu-id="a43bf-192">-From</span></span>

<span data-ttu-id="a43bf-193">**From** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a43bf-193">The **From** parameter is required.</span></span> <span data-ttu-id="a43bf-194">此参数指定发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a43bf-194">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="a43bf-195">输入名称 (可选) 和电子邮件地址，如 `Name <someone@fabrikam.com>` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-195">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-196">-Port</span><span class="sxs-lookup"><span data-stu-id="a43bf-196">-Port</span></span>

<span data-ttu-id="a43bf-197">指定 SMTP 服务器上的备用端口。</span><span class="sxs-lookup"><span data-stu-id="a43bf-197">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="a43bf-198">默认值为 25，这是默认的 SMTP 端口。</span><span class="sxs-lookup"><span data-stu-id="a43bf-198">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-199">-Priority</span><span class="sxs-lookup"><span data-stu-id="a43bf-199">-Priority</span></span>

<span data-ttu-id="a43bf-200">指定电子邮件的优先级。</span><span class="sxs-lookup"><span data-stu-id="a43bf-200">Specifies the priority of the email message.</span></span> <span data-ttu-id="a43bf-201">默认值为 Normal。</span><span class="sxs-lookup"><span data-stu-id="a43bf-201">Normal is the default.</span></span> <span data-ttu-id="a43bf-202">此参数可接受的值为 Normal、High 和 Low。</span><span class="sxs-lookup"><span data-stu-id="a43bf-202">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-203">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="a43bf-203">-SmtpServer</span></span>

<span data-ttu-id="a43bf-204">指定发送电子邮件的 SMTP 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="a43bf-204">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="a43bf-205">默认值为 `$PSEmailServer` 首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="a43bf-205">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="a43bf-206">如果未设置首选项变量，并且未使用此参数，则该 `Send-MailMessage` 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="a43bf-206">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-207">-Subject</span><span class="sxs-lookup"><span data-stu-id="a43bf-207">-Subject</span></span>

<span data-ttu-id="a43bf-208">**Subject** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a43bf-208">The **Subject** parameter is required.</span></span> <span data-ttu-id="a43bf-209">此参数指定电子邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="a43bf-209">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-210">-To</span><span class="sxs-lookup"><span data-stu-id="a43bf-210">-To</span></span>

<span data-ttu-id="a43bf-211">**To** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a43bf-211">The **To** parameter is required.</span></span> <span data-ttu-id="a43bf-212">此参数指定收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a43bf-212">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="a43bf-213">如果有多个收件人，请用逗号分隔其地址 (`,`) 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-213">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="a43bf-214">输入名称 (可选) 和电子邮件地址，如 `Name <someone@fabrikam.com>` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-214">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-215">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="a43bf-215">-UseSsl</span></span>

<span data-ttu-id="a43bf-216">安全套接字层 (SSL) 协议用于建立到远程计算机的安全连接以发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a43bf-216">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="a43bf-217">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="a43bf-217">By default, SSL is not used.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a43bf-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a43bf-218">CommonParameters</span></span>

<span data-ttu-id="a43bf-219">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a43bf-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a43bf-220">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a43bf-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a43bf-221">输入</span><span class="sxs-lookup"><span data-stu-id="a43bf-221">INPUTS</span></span>

### <span data-ttu-id="a43bf-222">System.String</span><span class="sxs-lookup"><span data-stu-id="a43bf-222">System.String</span></span>

<span data-ttu-id="a43bf-223">你可以通过管道将附件的路径和文件名传递给 `Send-MailMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a43bf-223">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="a43bf-224">输出</span><span class="sxs-lookup"><span data-stu-id="a43bf-224">OUTPUTS</span></span>

### <span data-ttu-id="a43bf-225">无</span><span class="sxs-lookup"><span data-stu-id="a43bf-225">None</span></span>

<span data-ttu-id="a43bf-226">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="a43bf-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a43bf-227">注释</span><span class="sxs-lookup"><span data-stu-id="a43bf-227">NOTES</span></span>

## <span data-ttu-id="a43bf-228">相关链接</span><span class="sxs-lookup"><span data-stu-id="a43bf-228">RELATED LINKS</span></span>

[<span data-ttu-id="a43bf-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a43bf-229">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="a43bf-230">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="a43bf-230">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)
