---
external help file: Microsoft.PowerShell.Security.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 4dae7806cbec85347a8dfa01348be72061214c6c
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "93198927"
---
# <span data-ttu-id="bbfec-103">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="bbfec-103">ConvertFrom-SecureString</span></span>

## <span data-ttu-id="bbfec-104">摘要</span><span class="sxs-lookup"><span data-stu-id="bbfec-104">SYNOPSIS</span></span>
<span data-ttu-id="bbfec-105">将安全字符串转换为加密的标准字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-105">Converts a secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="bbfec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bbfec-106">SYNTAX</span></span>

### <span data-ttu-id="bbfec-107">Secure（默认值）</span><span class="sxs-lookup"><span data-stu-id="bbfec-107">Secure (Default)</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="bbfec-108">打开</span><span class="sxs-lookup"><span data-stu-id="bbfec-108">Open</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="bbfec-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bbfec-109">DESCRIPTION</span></span>

<span data-ttu-id="bbfec-110">**Convertfrom-csv** cmdlet 将 ( **SecureString** ) 的安全字符串转换为加密的标准 **字符串 (的** ) 。</span><span class="sxs-lookup"><span data-stu-id="bbfec-110">The **ConvertFrom-SecureString** cmdlet converts a secure string ( **System.Security.SecureString** ) into an encrypted standard string ( **System.String** ).</span></span> <span data-ttu-id="bbfec-111">和安全字符串不同，加密的标准字符串可保存在文件中以供以后使用。</span><span class="sxs-lookup"><span data-stu-id="bbfec-111">Unlike a secure string, an encrypted standard string can be saved in a file for later use.</span></span> <span data-ttu-id="bbfec-112">使用 cmdlet 可以将加密的标准字符串转换回其安全字符串格式 `ConvertTo-SecureString` 。</span><span class="sxs-lookup"><span data-stu-id="bbfec-112">The encrypted standard string can be converted back to its secure string format by using the `ConvertTo-SecureString` cmdlet.</span></span>

<span data-ttu-id="bbfec-113">如果使用 **Key** 或 **SecureKey** 参数指定加密密钥，则使用高级加密标准 (AES) 加密算法。</span><span class="sxs-lookup"><span data-stu-id="bbfec-113">If an encryption key is specified by using the **Key** or **SecureKey** parameters, the Advanced Encryption Standard (AES) encryption algorithm is used.</span></span> <span data-ttu-id="bbfec-114">指定的密钥必须具有 128、192 或 256 字节的长度，因为这些是 AES 加密算法支持的密钥长度。</span><span class="sxs-lookup"><span data-stu-id="bbfec-114">The specified key must have a length of 128, 192, or 256 bits because those are the key lengths supported by the AES encryption algorithm.</span></span> <span data-ttu-id="bbfec-115">如果未指定密钥，则使用 Windows 数据保护 API (DPAPI) 加密标准字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="bbfec-115">If no key is specified, the Windows Data Protection API (DPAPI) is used to encrypt the standard string representation.</span></span>

## <span data-ttu-id="bbfec-116">示例</span><span class="sxs-lookup"><span data-stu-id="bbfec-116">EXAMPLES</span></span>

### <span data-ttu-id="bbfec-117">示例1：创建安全字符串</span><span class="sxs-lookup"><span data-stu-id="bbfec-117">Example 1: Create a secure string</span></span>

```powershell
$SecureString = Read-Host -AsSecureString
```

<span data-ttu-id="bbfec-118">此命令从你在命令提示符处键入的字符创建安全字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-118">This command creates a secure string from characters that you type at the command prompt.</span></span> <span data-ttu-id="bbfec-119">输入命令后，键入要存储为安全字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-119">After entering the command, type the string you want to store as a secure string.</span></span> <span data-ttu-id="bbfec-120">将显示一个星号 (`*`) ，用于表示你键入的每个字符。</span><span class="sxs-lookup"><span data-stu-id="bbfec-120">An asterisk (`*`) is displayed to represent each character that you type.</span></span>

### <span data-ttu-id="bbfec-121">示例2：将安全字符串转换为加密的标准字符串</span><span class="sxs-lookup"><span data-stu-id="bbfec-121">Example 2: Convert a secure string to an encrypted standard string</span></span>

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

<span data-ttu-id="bbfec-122">此命令将变量中的安全字符串转换 `$SecureString` 为加密的标准字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-122">This command converts the secure string in the `$SecureString` variable to an encrypted standard string.</span></span> <span data-ttu-id="bbfec-123">生成的加密标准字符串存储在变量中 `$StandardString` 。</span><span class="sxs-lookup"><span data-stu-id="bbfec-123">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

### <span data-ttu-id="bbfec-124">示例3：使用192位密钥将安全字符串转换为加密的标准字符串</span><span class="sxs-lookup"><span data-stu-id="bbfec-124">Example 3: Convert a secure string to an encrypted standard string with a 192-bit key</span></span>

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

<span data-ttu-id="bbfec-125">这些命令使用高级加密标准 (AES) 算法将变量中存储的安全字符串转换 `$SecureString` 为具有192位密钥的加密的标准字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-125">These commands use the Advanced Encryption Standard (AES) algorithm to convert the secure string stored in the `$SecureString` variable to an encrypted standard string with a 192-bit key.</span></span> <span data-ttu-id="bbfec-126">生成的加密标准字符串存储在变量中 `$StandardString` 。</span><span class="sxs-lookup"><span data-stu-id="bbfec-126">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

<span data-ttu-id="bbfec-127">第一个命令将密钥存储在 `$Key` 变量中。</span><span class="sxs-lookup"><span data-stu-id="bbfec-127">The first command stores a key in the `$Key` variable.</span></span> <span data-ttu-id="bbfec-128">该密钥是24个十进制数字的数组，其中每个数字都必须小于256，才能容纳在一个无符号字节内。</span><span class="sxs-lookup"><span data-stu-id="bbfec-128">The key is an array of 24 decimal numerals, each of which must be less than 256 to fit within a single unsigned byte.</span></span>

<span data-ttu-id="bbfec-129">由于每个十进制数字代表单个字节 (8 位) ，因此， (8 x 24) ，该密钥的总大小为192位。</span><span class="sxs-lookup"><span data-stu-id="bbfec-129">Because each decimal numeral represents a single byte (8 bits), the key has 24 digits for a total of 192 bits (8 x 24).</span></span> <span data-ttu-id="bbfec-130">这是用于 AES 算法的有效的密钥长度值。</span><span class="sxs-lookup"><span data-stu-id="bbfec-130">This is a valid key length for the AES algorithm.</span></span>

<span data-ttu-id="bbfec-131">第二个命令使用变量中的密钥 `$Key` 将安全字符串转换为加密的标准字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-131">The second command uses the key in the `$Key` variable to convert the secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="bbfec-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bbfec-132">PARAMETERS</span></span>

### <span data-ttu-id="bbfec-133">-Key</span><span class="sxs-lookup"><span data-stu-id="bbfec-133">-Key</span></span>

<span data-ttu-id="bbfec-134">将加密密钥指定为字节数组。</span><span class="sxs-lookup"><span data-stu-id="bbfec-134">Specifies the encryption key as a byte array.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bbfec-135">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="bbfec-135">-SecureKey</span></span>

<span data-ttu-id="bbfec-136">将加密密钥指定为安全字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-136">Specifies the encryption key as a secure string.</span></span> <span data-ttu-id="bbfec-137">在将安全字符串值用作密钥之前，需将其转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="bbfec-137">The secure string value is converted to a byte array before being used as the key.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bbfec-138">-SecureString</span><span class="sxs-lookup"><span data-stu-id="bbfec-138">-SecureString</span></span>

<span data-ttu-id="bbfec-139">指定安全字符串转换为加密的标准字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfec-139">Specifies the secure string to convert to an encrypted standard string.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bbfec-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bbfec-140">CommonParameters</span></span>

<span data-ttu-id="bbfec-141">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="bbfec-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bbfec-142">有关详细信息，请参阅 about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216) 。</span><span class="sxs-lookup"><span data-stu-id="bbfec-142">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bbfec-143">输入</span><span class="sxs-lookup"><span data-stu-id="bbfec-143">INPUTS</span></span>

### <span data-ttu-id="bbfec-144">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="bbfec-144">System.Security.SecureString</span></span>

<span data-ttu-id="bbfec-145">可以通过管道将 **SecureString** 对象传递给 Convertfrom-csv-SecureString。</span><span class="sxs-lookup"><span data-stu-id="bbfec-145">You can pipe a **SecureString** object to ConvertFrom-SecureString.</span></span>

## <span data-ttu-id="bbfec-146">输出</span><span class="sxs-lookup"><span data-stu-id="bbfec-146">OUTPUTS</span></span>

### <span data-ttu-id="bbfec-147">System.String</span><span class="sxs-lookup"><span data-stu-id="bbfec-147">System.String</span></span>

<span data-ttu-id="bbfec-148">ConvertFrom-SecureString 返回标准字符串对象。</span><span class="sxs-lookup"><span data-stu-id="bbfec-148">ConvertFrom-SecureString returns a standard string object.</span></span>

## <span data-ttu-id="bbfec-149">注释</span><span class="sxs-lookup"><span data-stu-id="bbfec-149">NOTES</span></span>

- <span data-ttu-id="bbfec-150">若要从在命令提示符处键入的字符创建安全字符串，请使用 cmdlet 的 **AsSecureString** 参数 `Read-Host` 。</span><span class="sxs-lookup"><span data-stu-id="bbfec-150">To create a secure string from characters that are typed at the command prompt, use the **AsSecureString** parameter of the `Read-Host` cmdlet.</span></span>
- <span data-ttu-id="bbfec-151">使用 **key** 或 **SecureKey** 参数指定密钥时，密钥长度必须正确。</span><span class="sxs-lookup"><span data-stu-id="bbfec-151">When you use the **Key** or **SecureKey** parameters to specify a key, the key length must be correct.</span></span> <span data-ttu-id="bbfec-152">例如，128位的密钥可以指定为16个十进制数字的字节数组。</span><span class="sxs-lookup"><span data-stu-id="bbfec-152">For example, a key of 128 bits can be specified as a byte array of 16 decimal numerals.</span></span>
  <span data-ttu-id="bbfec-153">同样，192位和256位的密钥分别对应于24和32十进制数字的字节数组。</span><span class="sxs-lookup"><span data-stu-id="bbfec-153">Similarly, 192-bit and 256-bit keys correspond to byte arrays of 24 and 32 decimal numerals, respectively.</span></span>
- <span data-ttu-id="bbfec-154">一些字符（如图释）对应于包含它们的字符串中的几个码位。</span><span class="sxs-lookup"><span data-stu-id="bbfec-154">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="bbfec-155">避免使用这些字符，因为在密码中使用时，它们可能会导致问题和误解。</span><span class="sxs-lookup"><span data-stu-id="bbfec-155">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="bbfec-156">相关链接</span><span class="sxs-lookup"><span data-stu-id="bbfec-156">RELATED LINKS</span></span>

[<span data-ttu-id="bbfec-157">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="bbfec-157">ConvertTo-SecureString</span></span>](ConvertTo-SecureString.md)

[<span data-ttu-id="bbfec-158">Read-Host</span><span class="sxs-lookup"><span data-stu-id="bbfec-158">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)
