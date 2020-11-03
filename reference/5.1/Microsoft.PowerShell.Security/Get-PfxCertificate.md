---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 1be3034b1fb44b1dce1a592ea5a2c1622b54d28f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197986"
---
# <span data-ttu-id="410dc-103">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="410dc-103">Get-PfxCertificate</span></span>

## <span data-ttu-id="410dc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="410dc-104">SYNOPSIS</span></span>
<span data-ttu-id="410dc-105">获取计算机上的 PFX 证书文件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="410dc-105">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="410dc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="410dc-106">SYNTAX</span></span>

### <span data-ttu-id="410dc-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="410dc-107">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="410dc-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="410dc-108">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="410dc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="410dc-109">DESCRIPTION</span></span>

<span data-ttu-id="410dc-110">`Get-PfxCertificate`Cmdlet 可获取表示每个指定的 PFX 证书文件的对象。</span><span class="sxs-lookup"><span data-stu-id="410dc-110">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="410dc-111">PFX 文件包括证书和私钥。</span><span class="sxs-lookup"><span data-stu-id="410dc-111">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="410dc-112">示例</span><span class="sxs-lookup"><span data-stu-id="410dc-112">EXAMPLES</span></span>

### <span data-ttu-id="410dc-113">示例1：获取 PFX 证书</span><span class="sxs-lookup"><span data-stu-id="410dc-113">Example 1: Get a PFX certificate</span></span>

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

<span data-ttu-id="410dc-114">此命令获取有关系统上的 Test .pfx 证书文件的信息。</span><span class="sxs-lookup"><span data-stu-id="410dc-114">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="410dc-115">示例2：从远程计算机获取 PFX 证书</span><span class="sxs-lookup"><span data-stu-id="410dc-115">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="410dc-116">此命令从 Server01 远程计算机获取 PFX 证书文件。</span><span class="sxs-lookup"><span data-stu-id="410dc-116">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="410dc-117">它使用 `Invoke-Command` 来远程运行 `Get-PfxCertificate` 命令。</span><span class="sxs-lookup"><span data-stu-id="410dc-117">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="410dc-118">如果 PFX 证书文件不受密码保护，则的 **Authentication** 参数的值 `Invoke-Command` 必须是 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="410dc-118">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="410dc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="410dc-119">PARAMETERS</span></span>

### <span data-ttu-id="410dc-120">-FilePath</span><span class="sxs-lookup"><span data-stu-id="410dc-120">-FilePath</span></span>

<span data-ttu-id="410dc-121">指定受保护文件的 PFX 文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="410dc-121">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="410dc-122">如果指定此参数的值，则不需要在命令行键入 `-FilePath`。</span><span class="sxs-lookup"><span data-stu-id="410dc-122">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="410dc-123">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="410dc-123">-LiteralPath</span></span>

<span data-ttu-id="410dc-124">受保护文件的 PFX 文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="410dc-124">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="410dc-125">与 **FilePath** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="410dc-125">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="410dc-126">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="410dc-126">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="410dc-127">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="410dc-127">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="410dc-128">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="410dc-128">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="410dc-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="410dc-129">CommonParameters</span></span>

<span data-ttu-id="410dc-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="410dc-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="410dc-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="410dc-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="410dc-132">输入</span><span class="sxs-lookup"><span data-stu-id="410dc-132">INPUTS</span></span>

### <span data-ttu-id="410dc-133">System.String</span><span class="sxs-lookup"><span data-stu-id="410dc-133">System.String</span></span>

<span data-ttu-id="410dc-134">可以通过管道将包含文件路径的字符串传递给 `Get-PfxCertificate` 。</span><span class="sxs-lookup"><span data-stu-id="410dc-134">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="410dc-135">输出</span><span class="sxs-lookup"><span data-stu-id="410dc-135">OUTPUTS</span></span>

### <span data-ttu-id="410dc-136">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="410dc-136">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="410dc-137">`Get-PfxCertificate` 为获取的每个证书返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="410dc-137">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="410dc-138">注释</span><span class="sxs-lookup"><span data-stu-id="410dc-138">NOTES</span></span>

<span data-ttu-id="410dc-139">使用 `Invoke-Command` cmdlet `Get-PfxCertificate` 远程运行命令时，如果 PFX 证书文件不受密码保护，则的 **Authentication** 参数的值 `Invoke-Command` 必须是 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="410dc-139">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="410dc-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="410dc-140">RELATED LINKS</span></span>

[<span data-ttu-id="410dc-141">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="410dc-141">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="410dc-142">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="410dc-142">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)
