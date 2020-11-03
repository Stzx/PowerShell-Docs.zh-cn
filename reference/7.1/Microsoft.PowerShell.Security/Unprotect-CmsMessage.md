---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: eaabf4e45a9441a479059513a428f2d87430dd2a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198760"
---
# <span data-ttu-id="0ff16-103">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="0ff16-103">Unprotect-CmsMessage</span></span>

## <span data-ttu-id="0ff16-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0ff16-104">SYNOPSIS</span></span>
<span data-ttu-id="0ff16-105">使用加密消息语法格式对已加密的内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="0ff16-105">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

## <span data-ttu-id="0ff16-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ff16-106">SYNTAX</span></span>

### <span data-ttu-id="0ff16-107">ByWinEvent (默认值) </span><span class="sxs-lookup"><span data-stu-id="0ff16-107">ByWinEvent (Default)</span></span>

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="0ff16-108">ByContent</span><span class="sxs-lookup"><span data-stu-id="0ff16-108">ByContent</span></span>

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="0ff16-109">ByPath</span><span class="sxs-lookup"><span data-stu-id="0ff16-109">ByPath</span></span>

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### <span data-ttu-id="0ff16-110">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ff16-110">ByLiteralPath</span></span>

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="0ff16-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ff16-111">DESCRIPTION</span></span>

<span data-ttu-id="0ff16-112">`Unprotect-CmsMessage`Cmdlet 将使用加密消息语法加密的内容解密 (CMS) 格式。</span><span class="sxs-lookup"><span data-stu-id="0ff16-112">The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted by using the Cryptographic Message Syntax (CMS) format.</span></span>

<span data-ttu-id="0ff16-113">CMS cmdlet 支持使用 IETF 标准格式对内容进行加密和解密，如 [RFC5652](https://tools.ietf.org/html/rfc5652)所述。</span><span class="sxs-lookup"><span data-stu-id="0ff16-113">The CMS cmdlets support encryption and decryption of content using the IETF standard format for cryptographically protecting messages, as documented by [RFC5652](https://tools.ietf.org/html/rfc5652).</span></span>

<span data-ttu-id="0ff16-114">CMS 加密标准采用公钥加密系统，其中用来加密内容的密匙（公匙）和用来解密内容的密匙（私匙）是分离的。</span><span class="sxs-lookup"><span data-stu-id="0ff16-114">The CMS encryption standard uses public key cryptography, where the keys used to encrypt content (the public key) and the keys used to decrypt content (the private key) are separate.</span></span> <span data-ttu-id="0ff16-115">公匙可以广泛共享，它不是敏感数据。</span><span class="sxs-lookup"><span data-stu-id="0ff16-115">Your public key can be shared widely, and is not sensitive data.</span></span> <span data-ttu-id="0ff16-116">如果用此公匙加密了任何内容，只有你的私匙可以解密它。</span><span class="sxs-lookup"><span data-stu-id="0ff16-116">If any content is encrypted with this public key, only your private key can decrypt it.</span></span> <span data-ttu-id="0ff16-117">有关详细信息，请参阅 [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography)（公钥加密）。</span><span class="sxs-lookup"><span data-stu-id="0ff16-117">For more information, see [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="0ff16-118">`Unprotect-CmsMessage` 对已加密为 CMS 格式的内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="0ff16-118">`Unprotect-CmsMessage` decrypts content that has been encrypted in CMS format.</span></span> <span data-ttu-id="0ff16-119">可以运行此 cmdlet 来解密通过运行 cmdlet 加密的内容 `Protect-CmsMessage` 。</span><span class="sxs-lookup"><span data-stu-id="0ff16-119">You can run this cmdlet to decrypt content that you have encrypted by running the `Protect-CmsMessage` cmdlet.</span></span> <span data-ttu-id="0ff16-120">你可以通过加密事件日志记录 ID 号或加密内容的路径来指定要解密的内容。</span><span class="sxs-lookup"><span data-stu-id="0ff16-120">You can specify content that you want to decrypt as a string, by the encryption event log record ID number, or by path to the encrypted content.</span></span> <span data-ttu-id="0ff16-121">`Unprotect-CmsMessage`Cmdlet 将返回已解密的内容。</span><span class="sxs-lookup"><span data-stu-id="0ff16-121">The `Unprotect-CmsMessage` cmdlet returns the decrypted content.</span></span>

<span data-ttu-id="0ff16-122">PowerShell 7.1 中添加了对 Linux 和 macOS 的支持。</span><span class="sxs-lookup"><span data-stu-id="0ff16-122">Support for Linux and macOS was added in PowerShell 7.1.</span></span>

## <span data-ttu-id="0ff16-123">示例</span><span class="sxs-lookup"><span data-stu-id="0ff16-123">EXAMPLES</span></span>

### <span data-ttu-id="0ff16-124">示例1：解密消息</span><span class="sxs-lookup"><span data-stu-id="0ff16-124">Example 1: Decrypt a message</span></span>

<span data-ttu-id="0ff16-125">在下面的示例中，对位于文本路径中的内容进行解密 `C:\Users\Test\Documents\PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="0ff16-125">In the following example, you decrypt content that is located at the literal path `C:\Users\Test\Documents\PowerShell`.</span></span> <span data-ttu-id="0ff16-126">对于 **参数所** 需的值，此示例使用用于执行加密的证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="0ff16-126">For the value of the required **To** parameter, this example uses the thumbprint of the certificate that was used to perform the encryption.</span></span> <span data-ttu-id="0ff16-127">解密后的消息“尝试新的 Break All 命令”是结果。</span><span class="sxs-lookup"><span data-stu-id="0ff16-127">The decrypted message, "Try the new Break All command," is the result.</span></span>

```powershell
$parameters = @{
  LiteralPath = "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
  To = '0f 8j b1 ab e0 ce 35 1d 67 d2 f2 6f a2 d2 00 cl 22 z9 m9 85'
}
Unprotect-CmsMessage -LiteralPath @parameters
```

```Output
Try the new Break All command
```

## <span data-ttu-id="0ff16-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ff16-128">PARAMETERS</span></span>

### <span data-ttu-id="0ff16-129">-Content</span><span class="sxs-lookup"><span data-stu-id="0ff16-129">-Content</span></span>

<span data-ttu-id="0ff16-130">指定加密字符串或包含加密字符串的变量。</span><span class="sxs-lookup"><span data-stu-id="0ff16-130">Specifies an encrypted string, or a variable containing an encrypted string.</span></span>

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ff16-131">-System.diagnostics.eventing.reader.eventlogrecord</span><span class="sxs-lookup"><span data-stu-id="0ff16-131">-EventLogRecord</span></span>

<span data-ttu-id="0ff16-132">指定表示 CMS 加密操作的事件日志记录 ID。</span><span class="sxs-lookup"><span data-stu-id="0ff16-132">Specifies an event log record ID that represents a CMS encryption operation.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByWinEvent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ff16-133">-IncludeContext</span><span class="sxs-lookup"><span data-stu-id="0ff16-133">-IncludeContext</span></span>

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

### <span data-ttu-id="0ff16-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ff16-134">-LiteralPath</span></span>

<span data-ttu-id="0ff16-135">指定要解密的加密内容的路径。</span><span class="sxs-lookup"><span data-stu-id="0ff16-135">Specifies the path to encrypted content that you want to decrypt.</span></span> <span data-ttu-id="0ff16-136">不同于 **Path** ， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="0ff16-136">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0ff16-137">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="0ff16-137">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="0ff16-138">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="0ff16-138">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0ff16-139">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="0ff16-139">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ff16-140">-Path</span><span class="sxs-lookup"><span data-stu-id="0ff16-140">-Path</span></span>

<span data-ttu-id="0ff16-141">指定要解密的加密内容的路径。</span><span class="sxs-lookup"><span data-stu-id="0ff16-141">Specifies the path to encrypted content that you want to decrypt.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ff16-142">-To</span><span class="sxs-lookup"><span data-stu-id="0ff16-142">-To</span></span>

<span data-ttu-id="0ff16-143">指定一个或多个 CMS 消息收件人，以下列任意格式标识：</span><span class="sxs-lookup"><span data-stu-id="0ff16-143">Specifies one or more CMS message recipients, identified in any of the following formats:</span></span>

- <span data-ttu-id="0ff16-144">实际证书（从证书提供程序检索到的）。</span><span class="sxs-lookup"><span data-stu-id="0ff16-144">An actual certificate (as retrieved from the certificate provider).</span></span>
- <span data-ttu-id="0ff16-145">包含证书的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0ff16-145">Path to the a file containing the certificate.</span></span>
- <span data-ttu-id="0ff16-146">指向包含证书的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="0ff16-146">Path to a directory containing the certificate.</span></span>
- <span data-ttu-id="0ff16-147">证书的指纹（用于在证书存储中查找）。</span><span class="sxs-lookup"><span data-stu-id="0ff16-147">Thumbprint of the certificate (used to look in the certificate store).</span></span>
- <span data-ttu-id="0ff16-148">证书的使用者名称（用于在证书存储中查找）。</span><span class="sxs-lookup"><span data-stu-id="0ff16-148">Subject name of the certificate (used to look in the certificate store).</span></span>

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ff16-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0ff16-149">CommonParameters</span></span>

<span data-ttu-id="0ff16-150">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0ff16-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ff16-151">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0ff16-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ff16-152">输入</span><span class="sxs-lookup"><span data-stu-id="0ff16-152">INPUTS</span></span>

### <span data-ttu-id="0ff16-153">System.diagnostics.eventing.reader.eventlogrecord 或 System.string 的信息。</span><span class="sxs-lookup"><span data-stu-id="0ff16-153">System.Diagnostics.Eventing.Reader.EventLogRecord or System.String</span></span>

<span data-ttu-id="0ff16-154">可以通过管道将包含加密内容的对象传递给 `Unprotect-CmsMessage` 。</span><span class="sxs-lookup"><span data-stu-id="0ff16-154">You can pipe an object containing encrypted content to `Unprotect-CmsMessage`.</span></span>

## <span data-ttu-id="0ff16-155">输出</span><span class="sxs-lookup"><span data-stu-id="0ff16-155">OUTPUTS</span></span>

### <span data-ttu-id="0ff16-156">System.String</span><span class="sxs-lookup"><span data-stu-id="0ff16-156">System.String</span></span>

<span data-ttu-id="0ff16-157">未加密的消息。</span><span class="sxs-lookup"><span data-stu-id="0ff16-157">The unencrypted message.</span></span>

## <span data-ttu-id="0ff16-158">注释</span><span class="sxs-lookup"><span data-stu-id="0ff16-158">NOTES</span></span>

## <span data-ttu-id="0ff16-159">相关链接</span><span class="sxs-lookup"><span data-stu-id="0ff16-159">RELATED LINKS</span></span>

[<span data-ttu-id="0ff16-160">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0ff16-160">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="0ff16-161">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="0ff16-161">Get-CmsMessage</span></span>](Get-CmsMessage.md)

[<span data-ttu-id="0ff16-162">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="0ff16-162">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)

