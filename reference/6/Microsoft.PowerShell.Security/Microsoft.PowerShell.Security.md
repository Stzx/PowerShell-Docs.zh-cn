---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=855959
Help Version: 6.2.5.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: a94c8c7e-9810-47c0-b8af-65089c13a35a
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
schema: 2.0.0
title: Microsoft.PowerShell.Security
ms.openlocfilehash: f97eb0139e73ca0222c4b98ea290ed9d8bec14e5
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "93199519"
---
# <span data-ttu-id="18701-103">Microsoft.PowerShell.Security 模块</span><span class="sxs-lookup"><span data-stu-id="18701-103">Microsoft.PowerShell.Security Module</span></span>

## <span data-ttu-id="18701-104">说明</span><span class="sxs-lookup"><span data-stu-id="18701-104">Description</span></span>

<span data-ttu-id="18701-105">本部分包含与 PowerShell Microsoft PowerShell 一起安装的 cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="18701-105">This section contains the help topics for the cmdlets that are installed with PowerShell Microsoft.PowerShell.Security module.</span></span> <span data-ttu-id="18701-106">Security 模块包含用于管理 Windows 的基本安全功能的 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="18701-106">The Security module contains cmdlets and providers that manage the basic security features of Windows.</span></span>

## <span data-ttu-id="18701-107">Microsoft PowerShell。安全 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="18701-107">Microsoft.PowerShell.Security Cmdlets</span></span>

### [<span data-ttu-id="18701-108">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="18701-108">ConvertFrom-SecureString</span></span>](ConvertFrom-SecureString.md)
<span data-ttu-id="18701-109">将安全字符串转换为加密的标准字符串。</span><span class="sxs-lookup"><span data-stu-id="18701-109">Converts a secure string to an encrypted standard string.</span></span>

### [<span data-ttu-id="18701-110">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="18701-110">ConvertTo-SecureString</span></span>](ConvertTo-SecureString.md)
<span data-ttu-id="18701-111">将加密的标准字符串转换为安全字符串。</span><span class="sxs-lookup"><span data-stu-id="18701-111">Converts encrypted standard strings to secure strings.</span></span>

### [<span data-ttu-id="18701-112">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="18701-112">Get-Acl</span></span>](Get-Acl.md)
<span data-ttu-id="18701-113">获取某个资源（如文件或注册表项）的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="18701-113">Gets the security descriptor for a resource, such as a file or registry key.</span></span>

### [<span data-ttu-id="18701-114">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="18701-114">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)
<span data-ttu-id="18701-115">获取有关文件的 Authenticode 签名的信息。</span><span class="sxs-lookup"><span data-stu-id="18701-115">Gets information about the Authenticode signature for a file.</span></span>

### [<span data-ttu-id="18701-116">Get-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="18701-116">Get-CmsMessage</span></span>](Get-CmsMessage.md)
<span data-ttu-id="18701-117">获取已使用加密消息语法格式进行加密的内容。</span><span class="sxs-lookup"><span data-stu-id="18701-117">Gets content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>

### [<span data-ttu-id="18701-118">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="18701-118">Get-Credential</span></span>](Get-Credential.md)
<span data-ttu-id="18701-119">获取基于用户名和密码的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="18701-119">Gets a credential object based on a user name and password.</span></span>

### [<span data-ttu-id="18701-120">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="18701-120">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)
<span data-ttu-id="18701-121">获取当前会话的执行策略。</span><span class="sxs-lookup"><span data-stu-id="18701-121">Gets the execution policies for the current session.</span></span>

### [<span data-ttu-id="18701-122">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="18701-122">Get-PfxCertificate</span></span>](Get-PfxCertificate.md)
<span data-ttu-id="18701-123">获取计算机上的 PFX 证书文件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="18701-123">Gets information about PFX certificate files on the computer.</span></span>

### [<span data-ttu-id="18701-124">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="18701-124">New-FileCatalog</span></span>](New-FileCatalog.md)
<span data-ttu-id="18701-125">创建一个 Windows 目录文件，该文件包含指定路径中的文件和文件夹的加密哈希。</span><span class="sxs-lookup"><span data-stu-id="18701-125">Creates a Windows catalog file containing cryptographic hashes for files and folders in specified paths.</span></span>

### [<span data-ttu-id="18701-126">Protect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="18701-126">Protect-CmsMessage</span></span>](Protect-CmsMessage.md)
<span data-ttu-id="18701-127">使用加密消息语法格式加密内容。</span><span class="sxs-lookup"><span data-stu-id="18701-127">Encrypts content by using the Cryptographic Message Syntax format.</span></span>

### [<span data-ttu-id="18701-128">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="18701-128">Set-Acl</span></span>](Set-Acl.md)
<span data-ttu-id="18701-129">更改指定项（如文件或注册表项）的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="18701-129">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

### [<span data-ttu-id="18701-130">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="18701-130">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)
<span data-ttu-id="18701-131">将 Authenticode 签名添加到 PowerShell 脚本或其他文件中。</span><span class="sxs-lookup"><span data-stu-id="18701-131">Adds an Authenticode signature to a PowerShell script or other file.</span></span>

### [<span data-ttu-id="18701-132">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="18701-132">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
<span data-ttu-id="18701-133">设置 Windows 计算机的 PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="18701-133">Sets the PowerShell execution policies for Windows computers.</span></span>

### [<span data-ttu-id="18701-134">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="18701-134">Test-FileCatalog</span></span>](Test-FileCatalog.md)
<span data-ttu-id="18701-135">验证)  ( 的目录文件中包含的哈希是否与实际文件的哈希值相匹配，以便验证其真实性。</span><span class="sxs-lookup"><span data-stu-id="18701-135">Validates whether the hashes contained in a catalog file (.cat) matches the hashes of the actual files in order to validate their authenticity.</span></span>

### [<span data-ttu-id="18701-136">Unprotect-CmsMessage</span><span class="sxs-lookup"><span data-stu-id="18701-136">Unprotect-CmsMessage</span></span>](Unprotect-CmsMessage.md)
<span data-ttu-id="18701-137">使用加密消息语法格式对已加密的内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="18701-137">Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.</span></span>
