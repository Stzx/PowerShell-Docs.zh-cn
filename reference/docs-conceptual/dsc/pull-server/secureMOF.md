---
ms.date: 07/06/2020
keywords: dsc,powershell,配置,安装程序
title: 保护 MOF 文件
description: 本文介绍了如何确保目标节点已加密 MOF 文件。
ms.openlocfilehash: ca94a901468626e5644880574457d899a012d311
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "97090341"
---
# <a name="securing-the-mof-file"></a><span data-ttu-id="37b1c-104">保护 MOF 文件</span><span class="sxs-lookup"><span data-stu-id="37b1c-104">Securing the MOF File</span></span>

> <span data-ttu-id="37b1c-105">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="37b1c-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="37b1c-106">DSC 通过应用存储于 MOF 文件中的信息来管理服务器节点的配置，其中本地配置管理器 (LCM) 在该文件中实现所需的结束状态。</span><span class="sxs-lookup"><span data-stu-id="37b1c-106">DSC manages the configuration of server nodes by applying information stored in a MOF file, where the Local Configuration Manager (LCM) implements the desired end state.</span></span> <span data-ttu-id="37b1c-107">由于此文件包含配置的详细信息，确保其安全非常重要。</span><span class="sxs-lookup"><span data-stu-id="37b1c-107">Because this file contains the details of the configuration, it's important to keep it secure.</span></span> <span data-ttu-id="37b1c-108">本文介绍了如何确保目标节点已加密文件。</span><span class="sxs-lookup"><span data-stu-id="37b1c-108">This article describes how to ensure the target node has encrypted the file.</span></span>

<span data-ttu-id="37b1c-109">自 PowerShell 版本 5.0 起，在将 MOF 文件应用于使用 `Start-DSCConfiguration` cmdlet 的节点时，默认情况下将加密整个 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="37b1c-109">Beginning with PowerShell version 5.0, the entire MOF file is encrypted by default when it is applied to the node using the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="37b1c-110">仅在使用请求服务协议实现解决方案（如果证书未被托管）时，才需用到本文所述相关过程，以确保目标节点下载的配置在被应用之前可由系统解密和读取（例如 Windows Server 中可用的请求服务）。</span><span class="sxs-lookup"><span data-stu-id="37b1c-110">The process described in this article is required only when implementing a solution using the pull service protocol if certificates are not managed, to ensure configurations downloaded by the target node can be decrypted and read by the system before they are applied (for example, the pull service available in Windows Server).</span></span> <span data-ttu-id="37b1c-111">注册到 [Azure 自动化 DSC](/azure/automation/automation-dsc-overview) 的节点将自动安装证书并使其由服务进行托管，无需承担管理开销。</span><span class="sxs-lookup"><span data-stu-id="37b1c-111">Nodes registered to [Azure Automation DSC](/azure/automation/automation-dsc-overview) will automatically have certificates installed and managed by the service with no administrative overhead required.</span></span>

> [!NOTE]
> <span data-ttu-id="37b1c-112">本主题讨论用于加密的证书。</span><span class="sxs-lookup"><span data-stu-id="37b1c-112">This topic discusses certificates used for encryption.</span></span> <span data-ttu-id="37b1c-113">对于加密，自签名证书就已足够，因为私钥始终保密，而加密并不表示信任该文档。</span><span class="sxs-lookup"><span data-stu-id="37b1c-113">For encryption, a self-signed certificate is sufficient, because the private key is always kept secret and encryption does not imply trust of the document.</span></span> <span data-ttu-id="37b1c-114">自签名证书 _不_ 得用于身份验证目的。</span><span class="sxs-lookup"><span data-stu-id="37b1c-114">Self-signed certificates should _not_ be used for authentication purposes.</span></span> <span data-ttu-id="37b1c-115">应使用来自受信任的证书颁发机构 (CA) 的证书进行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="37b1c-115">You should use a certificate from a trusted Certification Authority (CA) for any authentication purposes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37b1c-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="37b1c-116">Prerequisites</span></span>

<span data-ttu-id="37b1c-117">要成功加密所用凭据以保护 DSC 配置，请确保你有以下各项：</span><span class="sxs-lookup"><span data-stu-id="37b1c-117">To successfully encrypt the credentials used to secure a DSC configuration, make sure you have the following:</span></span>

- <span data-ttu-id="37b1c-118">**颁发和分发证书的方法**。</span><span class="sxs-lookup"><span data-stu-id="37b1c-118">**Some means of issuing and distributing certificates**.</span></span> <span data-ttu-id="37b1c-119">本主题及其中示例假定你使用 Active Directory 证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="37b1c-119">This topic and its examples assume you are using Active Directory Certification Authority.</span></span> <span data-ttu-id="37b1c-120">有关 Active Directory 证书服务的更多背景信息，请参阅 [Active Directory 证书服务概述](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="37b1c-120">For more background information on Active Directory Certificate Services, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>
- <span data-ttu-id="37b1c-121">**对目标节点的管理访问权限**。</span><span class="sxs-lookup"><span data-stu-id="37b1c-121">**Administrative access to the target node or nodes**.</span></span>
- <span data-ttu-id="37b1c-122">**每个目标节点的个人存储区中均保存了可加密的证书**。</span><span class="sxs-lookup"><span data-stu-id="37b1c-122">**Each target node has an encryption-capable certificate saved its Personal Store**.</span></span> <span data-ttu-id="37b1c-123">在 Windows PowerShell 中，该存储区的路径为 Cert:\LocalMachine\My。</span><span class="sxs-lookup"><span data-stu-id="37b1c-123">In Windows PowerShell, the path to the store is Cert:\LocalMachine\My.</span></span> <span data-ttu-id="37b1c-124">本主题中的示例使用“工作站身份验证”模板，你可以在[默认证书模板](/previous-versions/windows/it-pro/windows-server-2003/cc740061(v=ws.10))中找到它（以及其他证书模板）。</span><span class="sxs-lookup"><span data-stu-id="37b1c-124">The examples in this topic use the "workstation authentication" template, which you can find (along with other certificate templates) at [Default Certificate Templates](/previous-versions/windows/it-pro/windows-server-2003/cc740061(v=ws.10)).</span></span>
- <span data-ttu-id="37b1c-125">如果你将在计算机而不是目标节点上运行此配置，请 **导出证书的公钥**，然后将其导入到你将要从中运行配置的计算机。</span><span class="sxs-lookup"><span data-stu-id="37b1c-125">If you will be running this configuration on a computer other than the target node, **export the public key of the certificate**, and then import it to the computer you will run the configuration from.</span></span> <span data-ttu-id="37b1c-126">请确保仅导出 **公** 钥；保护私钥安全。</span><span class="sxs-lookup"><span data-stu-id="37b1c-126">Make sure that you export only the **public** key; keep the private key secure.</span></span>

> [!NOTE]
> <span data-ttu-id="37b1c-127">当涉及加密时，脚本资源具有限制。</span><span class="sxs-lookup"><span data-stu-id="37b1c-127">Script Resources have limitations when it comes to encryption.</span></span> <span data-ttu-id="37b1c-128">有关详细信息，请参阅[脚本资源](../reference/resources/windows/scriptResource.md#known-limitations)</span><span class="sxs-lookup"><span data-stu-id="37b1c-128">For more information, see [Script Resource](../reference/resources/windows/scriptResource.md#known-limitations)</span></span>

## <a name="overall-process"></a><span data-ttu-id="37b1c-129">整体进程</span><span class="sxs-lookup"><span data-stu-id="37b1c-129">Overall process</span></span>

 1. <span data-ttu-id="37b1c-130">设置证书、密钥和指纹，确保每个目标节点具有证书的副本，且配置计算机具有公钥和指纹。</span><span class="sxs-lookup"><span data-stu-id="37b1c-130">Set up the certificates, keys, and thumbprints, making sure that each target node has copies of the certificate and the configuration computer has the public key and thumbprint.</span></span>
 1. <span data-ttu-id="37b1c-131">创建包含公钥的路径和指纹的配置数据块。</span><span class="sxs-lookup"><span data-stu-id="37b1c-131">Create a configuration data block that contains the path and thumbprint of the public key.</span></span>
 1. <span data-ttu-id="37b1c-132">创建配置脚本，该脚本定义目标节点的所需配置，并通过命令本地配置管理器使用证书及其指纹解密配置数据来设置目标节点上的解密。</span><span class="sxs-lookup"><span data-stu-id="37b1c-132">Create a configuration script that defines your desired configuration for the target node and sets up decryption on the target nodes by commanding the Local Configuration manager to decrypt the configuration data using the certificate and its thumbprint.</span></span>
 1. <span data-ttu-id="37b1c-133">运行配置，这将设置本地配置管理器设置并启动 DSC 配置。</span><span class="sxs-lookup"><span data-stu-id="37b1c-133">Run the configuration, which will set the Local Configuration Manager settings and start the DSC configuration.</span></span>

![凭据加密的流程流](media/secureMOF/CredentialEncryptionDiagram1.png)

## <a name="certificate-requirements"></a><span data-ttu-id="37b1c-135">证书要求</span><span class="sxs-lookup"><span data-stu-id="37b1c-135">Certificate Requirements</span></span>

<span data-ttu-id="37b1c-136">若要执行凭据加密，公钥证书必须在受用于创作 DSC 配置的计算机 **信任** 的 _目标节点_ 上可用。</span><span class="sxs-lookup"><span data-stu-id="37b1c-136">To enact credential encryption, a public key certificate must be available on the _Target Node_ that is **trusted** by the computer being used to author the DSC configuration.</span></span> <span data-ttu-id="37b1c-137">若要将此公钥证书用于 DSC 凭据加密，它需具有以下特定要求：</span><span class="sxs-lookup"><span data-stu-id="37b1c-137">This public key certificate has specific requirements for it to be used for DSC credential encryption:</span></span>

1. <span data-ttu-id="37b1c-138">**密钥用法**：</span><span class="sxs-lookup"><span data-stu-id="37b1c-138">**Key Usage**:</span></span>
   - <span data-ttu-id="37b1c-139">必须包含：“KeyEncipherment”和“DataEncipherment”。</span><span class="sxs-lookup"><span data-stu-id="37b1c-139">Must contain: 'KeyEncipherment' and 'DataEncipherment'.</span></span>
   - <span data-ttu-id="37b1c-140">不应包含：“数字签名”。</span><span class="sxs-lookup"><span data-stu-id="37b1c-140">Should _not_ contain: 'Digital Signature'.</span></span>
1. <span data-ttu-id="37b1c-141">**增强型密钥用法**：</span><span class="sxs-lookup"><span data-stu-id="37b1c-141">**Enhanced Key Usage**:</span></span>
   - <span data-ttu-id="37b1c-142">必须包含：文档加密 (1.3.6.1.4.1.311.80.1)。</span><span class="sxs-lookup"><span data-stu-id="37b1c-142">Must contain: Document Encryption (1.3.6.1.4.1.311.80.1).</span></span>
   - <span data-ttu-id="37b1c-143">不应包含：客户端身份验证 (1.3.6.1.5.5.7.3.2) 和服务器身份验证 (1.3.6.1.5.5.7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="37b1c-143">Should _not_ contain: Client Authentication (1.3.6.1.5.5.7.3.2) and Server Authentication (1.3.6.1.5.5.7.3.1).</span></span>
1. <span data-ttu-id="37b1c-144">证书的私钥在\*目标节点_上可用。</span><span class="sxs-lookup"><span data-stu-id="37b1c-144">The Private Key for the certificate is available on the \*Target Node_.</span></span>
1. <span data-ttu-id="37b1c-145">证书的 **提供程序** 必须是“Microsoft RSA SChannel Cryptographic Provider”。</span><span class="sxs-lookup"><span data-stu-id="37b1c-145">The **Provider** for the certificate must be "Microsoft RSA SChannel Cryptographic Provider".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37b1c-146">虽然可以使用包含“数字签名”密钥用法或某个身份验证 EKU 的证书，但这会导致加密密钥更容易被误用，而且更容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="37b1c-146">Although you can use a certificate containing a Key Usage of 'Digital Signature' or one of the Authentication EKU's, this will enable the encryption key to be more easily misused and vulnerable to attack.</span></span> <span data-ttu-id="37b1c-147">因此，最好是使用为保护 DSC 凭据而专门创建的省略了这些密钥用法和 EKU 的证书。</span><span class="sxs-lookup"><span data-stu-id="37b1c-147">So it is best practice to use a certificate created specifically for the purpose of securing DSC credentials that omits these Key Usage and EKUs.</span></span>

<span data-ttu-id="37b1c-148">_目标节点_ 上满足这些条件的任何现有证书都可以用于保护 DSC 凭据。</span><span class="sxs-lookup"><span data-stu-id="37b1c-148">Any existing certificate on the _Target Node_ that meets these criteria can be used to secure DSC credentials.</span></span>

## <a name="certificate-creation"></a><span data-ttu-id="37b1c-149">证书创建</span><span class="sxs-lookup"><span data-stu-id="37b1c-149">Certificate creation</span></span>

<span data-ttu-id="37b1c-150">可以采用两种方法创建和使用所需的加密证书（公钥-私钥对）。</span><span class="sxs-lookup"><span data-stu-id="37b1c-150">There are two approaches you can take to create and use the required Encryption Certificate (public-private key pair).</span></span>

1. <span data-ttu-id="37b1c-151">在 **目标节点** 上创建密钥对，并仅将公钥导出到 **创作节点**</span><span class="sxs-lookup"><span data-stu-id="37b1c-151">Create it on the **Target Node** and export just the public key to the **Authoring Node**</span></span>
1. <span data-ttu-id="37b1c-152">在 **创作节点** 上创建密钥对，并将整个密钥对导出到 **目标节点**</span><span class="sxs-lookup"><span data-stu-id="37b1c-152">Create it on the **Authoring Node** and export the entire key pair to the **Target Node**</span></span>

<span data-ttu-id="37b1c-153">建议使用方法 1，因为用于解密 MOF 中凭据的私钥始终停留在目标节点上。</span><span class="sxs-lookup"><span data-stu-id="37b1c-153">Method 1 is recommended because the private key used to decrypt credentials in the MOF stays on the Target Node at all times.</span></span>

### <a name="creating-the-certificate-on-the-target-node"></a><span data-ttu-id="37b1c-154">在目标节点上创建证书</span><span class="sxs-lookup"><span data-stu-id="37b1c-154">Creating the Certificate on the Target Node</span></span>

<span data-ttu-id="37b1c-155">私钥必须是保密的，因为它可用于解密 **目标节点** 上的 MOF。为此，最简单的方法是在 **目标节点** 上创建私钥证书，并将 **公钥证书** 复制到用于将 DSC 配置编写到 MOF 文件中的计算机内。</span><span class="sxs-lookup"><span data-stu-id="37b1c-155">The private key must be kept secret, because is used to decrypt the MOF on the **Target Node** The easiest way to do that is to create the private key certificate on the **Target Node**, and copy the **public key certificate** to the computer being used to author the DSC configuration into a MOF file.</span></span> <span data-ttu-id="37b1c-156">下面的示例：</span><span class="sxs-lookup"><span data-stu-id="37b1c-156">The following example:</span></span>

1. <span data-ttu-id="37b1c-157">在 **目标节点** 上创建证书</span><span class="sxs-lookup"><span data-stu-id="37b1c-157">creates a certificate on the **Target node**</span></span>
1. <span data-ttu-id="37b1c-158">在 **目标节点** 上导出公钥证书。</span><span class="sxs-lookup"><span data-stu-id="37b1c-158">exports the public key certificate on the **Target node**.</span></span>
1. <span data-ttu-id="37b1c-159">将公钥证书导入到 **创作节点** 上 **我的** 证书存储。</span><span class="sxs-lookup"><span data-stu-id="37b1c-159">imports the public key certificate into the **my** certificate store on the **Authoring node**.</span></span>

#### <a name="on-the-target-node-create-and-export-the-certificate"></a><span data-ttu-id="37b1c-160">在目标节点上：创建并导出证书</span><span class="sxs-lookup"><span data-stu-id="37b1c-160">On the Target Node: create and export the certificate</span></span>

> <span data-ttu-id="37b1c-161">目标节点：Windows Server 2016 和 Windows 10</span><span class="sxs-lookup"><span data-stu-id="37b1c-161">Target Node: Windows Server 2016 and Windows 10</span></span>

```powershell
# note: These steps need to be performed in an Administrator PowerShell session
$cert = New-SelfSignedCertificate -Type DocumentEncryptionCertLegacyCsp -DnsName 'DscEncryptionCert' -HashAlgorithm SHA256
# export the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
```

<span data-ttu-id="37b1c-162">一旦导出完成，需要将 `DscPublicKey.cer` 复制到 **创作节点**。</span><span class="sxs-lookup"><span data-stu-id="37b1c-162">Once exported, the `DscPublicKey.cer` would need to be copied to the **Authoring Node**.</span></span>

> <span data-ttu-id="37b1c-163">目标节点：Windows Server 2012 R2/Windows 8.1 及更早版本</span><span class="sxs-lookup"><span data-stu-id="37b1c-163">Target Node: Windows Server 2012 R2/Windows 8.1 and earlier</span></span>

> [!WARNING]
> <span data-ttu-id="37b1c-164">因为 Windows 10 和 Windows Server 2016 之前版本的 Windows 操作系统上的 `New-SelfSignedCertificate` cmdlet 不支持 Type 参数，因此，在这些操作系统上创建此证书需要其他方法。</span><span class="sxs-lookup"><span data-stu-id="37b1c-164">Because the `New-SelfSignedCertificate` cmdlet on Windows Operating Systems prior to Windows 10 and Windows Server 2016 do not support the **Type** parameter, an alternate method of creating this certificate is required on these operating systems.</span></span> <span data-ttu-id="37b1c-165">在这种情况下，可以使用 `makecert.exe` 或者 `certutil.exe` 来创建证书。</span><span class="sxs-lookup"><span data-stu-id="37b1c-165">In this case you can use `makecert.exe` or `certutil.exe` to create the certificate.</span></span> <span data-ttu-id="37b1c-166">本示例使用 Microsoft 脚本中心中的 [New-SelfSignedCertificateEx.ps1](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6) 脚本作为创建证书的替代方法。</span><span class="sxs-lookup"><span data-stu-id="37b1c-166">This example uses the [New-SelfSignedCertificateEx.ps1](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6) script from Microsoft Script Center as an alternate way to create the certificate.</span></span> <span data-ttu-id="37b1c-167">PowerShell 库的 [PSPKI](https://www.powershellgallery.com/packages/PSPKI/) 模块中提供了此脚本的更新版本。</span><span class="sxs-lookup"><span data-stu-id="37b1c-167">An updated version of this script is available in the [PSPKI](https://www.powershellgallery.com/packages/PSPKI/) module in the PowerShell Gallery.</span></span>

```powershell
# note: These steps need to be performed in an Administrator PowerShell session
# and in the folder that contains New-SelfSignedCertificateEx.ps1
. .\New-SelfSignedCertificateEx.ps1
New-SelfsignedCertificateEx `
    -Subject "CN=${ENV:ComputerName}" `
    -EKU 'Document Encryption' `
    -KeyUsage 'KeyEncipherment, DataEncipherment' `
    -SAN ${ENV:ComputerName} `
    -FriendlyName 'DSC Credential Encryption certificate' `
    -Exportable `
    -StoreLocation 'LocalMachine' `
    -KeyLength 2048 `
    -ProviderName 'Microsoft Enhanced Cryptographic Provider v1.0' `
    -AlgorithmName 'RSA' `
    -SignatureAlgorithm 'SHA256'
# Locate the newly created certificate
$Cert = Get-ChildItem -Path cert:\LocalMachine\My | Where-Object {
        ($_.FriendlyName -eq 'DSC Credential Encryption certificate') -and ($_.Subject -eq "CN=${ENV:ComputerName}")
    } | Select-Object -First 1
# export the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
```

<span data-ttu-id="37b1c-168">一旦导出完成，需要将 ```DscPublicKey.cer``` 复制到 **创作节点**。</span><span class="sxs-lookup"><span data-stu-id="37b1c-168">Once exported, the ```DscPublicKey.cer``` would need to be copied to the **Authoring Node**.</span></span>

#### <a name="on-the-authoring-node-import-the-certs-public-key"></a><span data-ttu-id="37b1c-169">在创作节点上：导入证书的公钥</span><span class="sxs-lookup"><span data-stu-id="37b1c-169">On the Authoring Node: import the cert's public key</span></span>

```powershell
# Import to the my store
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\My
```

### <a name="creating-the-certificate-on-the-authoring-node"></a><span data-ttu-id="37b1c-170">在创作节点上创建证书</span><span class="sxs-lookup"><span data-stu-id="37b1c-170">Creating the Certificate on the Authoring Node</span></span>

<span data-ttu-id="37b1c-171">或者，可以在 **创作节点** 上创建加密证书，并与 **私钥** 以 PFX 文件导出，然后在 **目标节点** 上导入。</span><span class="sxs-lookup"><span data-stu-id="37b1c-171">Alternately, the encryption certificate can be created on the **Authoring Node**, exported with the **private key** as a PFX file and then imported on the **Target Node**.</span></span> <span data-ttu-id="37b1c-172">这是当前用于在 _Nano Server_ 上实现 DSC 凭据加密的方法。</span><span class="sxs-lookup"><span data-stu-id="37b1c-172">This is the current method for implementing DSC credential encryption on _Nano Server_.</span></span> <span data-ttu-id="37b1c-173">尽管 PFX 使用密码保护，但在传输过程中也应保证其安全性。</span><span class="sxs-lookup"><span data-stu-id="37b1c-173">Although the PFX is secured with a password it should be kept secure during transit.</span></span> <span data-ttu-id="37b1c-174">下面的示例：</span><span class="sxs-lookup"><span data-stu-id="37b1c-174">The following example:</span></span>

1. <span data-ttu-id="37b1c-175">在 **创作节点** 上创建证书</span><span class="sxs-lookup"><span data-stu-id="37b1c-175">creates a certificate on the **Authoring node**.</span></span>
1. <span data-ttu-id="37b1c-176">在 **创作节点** 上导出证书（包括私钥）。</span><span class="sxs-lookup"><span data-stu-id="37b1c-176">exports the certificate including the private key on the **Authoring node**.</span></span>
1. <span data-ttu-id="37b1c-177">从 **创作节点** 中删除私钥，但将公钥证书保留在 **我的** 存储。</span><span class="sxs-lookup"><span data-stu-id="37b1c-177">removes the private key from the **Authoring node**, but keeps the public key certificate in the **my** store.</span></span>
1. <span data-ttu-id="37b1c-178">将私钥证书导入到目标节点上的 My(Personal) 证书存储。</span><span class="sxs-lookup"><span data-stu-id="37b1c-178">imports the private key certificate into the My(Personal) certificate store on the **Target node**.</span></span>
   - <span data-ttu-id="37b1c-179">必须将其添加到根存储，以便受到 **目标节点** 的信任。</span><span class="sxs-lookup"><span data-stu-id="37b1c-179">it must be added to the root store so that it will be trusted by the **Target node**.</span></span>

#### <a name="on-the-authoring-node-create-and-export-the-certificate"></a><span data-ttu-id="37b1c-180">在创作节点上：创建并导出证书</span><span class="sxs-lookup"><span data-stu-id="37b1c-180">On the Authoring Node: create and export the certificate</span></span>

> <span data-ttu-id="37b1c-181">目标节点：Windows Server 2016 和 Windows 10</span><span class="sxs-lookup"><span data-stu-id="37b1c-181">Target Node: Windows Server 2016 and Windows 10</span></span>

```powershell
# note: These steps need to be performed in an Administrator PowerShell session
$cert = New-SelfSignedCertificate -Type DocumentEncryptionCertLegacyCsp -DnsName 'DscEncryptionCert' -HashAlgorithm SHA256
# export the private key certificate
$mypwd = ConvertTo-SecureString -String "YOUR_PFX_PASSWD" -Force -AsPlainText
$cert | Export-PfxCertificate -FilePath "$env:temp\DscPrivateKey.pfx" -Password $mypwd -Force
# remove the private key certificate from the node but keep the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
$cert | Remove-Item -Force
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\My
```

<span data-ttu-id="37b1c-182">一旦导出完成，需要将 `DscPrivateKey.pfx` 复制到 **目标节点**。</span><span class="sxs-lookup"><span data-stu-id="37b1c-182">Once exported, the `DscPrivateKey.pfx` would need to be copied to the **Target Node**.</span></span>

> <span data-ttu-id="37b1c-183">目标节点：Windows Server 2012 R2/Windows 8.1 及更早版本</span><span class="sxs-lookup"><span data-stu-id="37b1c-183">Target Node: Windows Server 2012 R2/Windows 8.1 and earlier</span></span>

> [!WARNING]
> <span data-ttu-id="37b1c-184">因为 Windows 10 和 Windows Server 2016 之前版本的 Windows 操作系统上的 `New-SelfSignedCertificate` cmdlet 不支持 Type 参数，因此，在这些操作系统上创建此证书需要其他方法。</span><span class="sxs-lookup"><span data-stu-id="37b1c-184">Because the `New-SelfSignedCertificate` cmdlet on Windows Operating Systems prior to Windows 10 and Windows Server 2016 do not support the **Type** parameter, an alternate method of creating this certificate is required on these operating systems.</span></span> <span data-ttu-id="37b1c-185">在这种情况下，可以使用 `makecert.exe` 或者 `certutil.exe` 来创建证书。</span><span class="sxs-lookup"><span data-stu-id="37b1c-185">In this case you can use `makecert.exe` or `certutil.exe` to create the certificate.</span></span> <span data-ttu-id="37b1c-186">一种替代方法是从 Microsoft 脚本中心下载 [New-SelfSignedCertificateEx.ps1](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6) 脚本并改为使用它来创建证书：</span><span class="sxs-lookup"><span data-stu-id="37b1c-186">An alternate method is to download the [New-SelfSignedCertificateEx.ps1](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6) script from Microsoft Script Center and use it to create the certificate instead:</span></span>

```powershell
# note: These steps need to be performed in an Administrator PowerShell session
# and in the folder that contains New-SelfSignedCertificateEx.ps1
. .\New-SelfSignedCertificateEx.ps1
New-SelfsignedCertificateEx `
    -Subject "CN=${ENV:ComputerName}" `
    -EKU 'Document Encryption' `
    -KeyUsage 'KeyEncipherment, DataEncipherment' `
    -SAN ${ENV:ComputerName} `
    -FriendlyName 'DSC Credential Encryption certificate' `
    -Exportable `
    -StoreLocation 'LocalMachine' `
    -KeyLength 2048 `
    -ProviderName 'Microsoft Enhanced Cryptographic Provider v1.0' `
    -AlgorithmName 'RSA' `
    -SignatureAlgorithm 'SHA256'
# Locate the newly created certificate
$Cert = Get-ChildItem -Path cert:\LocalMachine\My | Where-Object {
        ($_.FriendlyName -eq 'DSC Credential Encryption certificate') -and ($_.Subject -eq "CN=${ENV:ComputerName}")
    } | Select-Object -First 1
# export the public key certificate
$mypwd = ConvertTo-SecureString -String "YOUR_PFX_PASSWD" -Force -AsPlainText
$cert | Export-PfxCertificate -FilePath "$env:temp\DscPrivateKey.pfx" -Password $mypwd -Force
# remove the private key certificate from the node but keep the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
$cert | Remove-Item -Force
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\My
```

#### <a name="on-the-target-node-import-the-certs-private-key-as-a-trusted-root"></a><span data-ttu-id="37b1c-187">在目标节点上：将证书的私钥作为受信任的根导入</span><span class="sxs-lookup"><span data-stu-id="37b1c-187">On the Target Node: import the cert's private key as a trusted root</span></span>

```powershell
# Import to the root store so that it is trusted
$mypwd = ConvertTo-SecureString -String "YOUR_PFX_PASSWD" -Force -AsPlainText
Import-PfxCertificate -FilePath "$env:temp\DscPrivateKey.pfx" -CertStoreLocation Cert:\LocalMachine\My -Password $mypwd > $null
```

## <a name="configuration-data"></a><span data-ttu-id="37b1c-188">配置数据</span><span class="sxs-lookup"><span data-stu-id="37b1c-188">Configuration data</span></span>

<span data-ttu-id="37b1c-189">配置数据块定义在哪个目标节点上进行操作、是否加密凭据、加密方式以及其他信息。</span><span class="sxs-lookup"><span data-stu-id="37b1c-189">The configuration data block defines which target nodes to operate on, whether or not to encrypt the credentials, the means of encryption, and other information.</span></span> <span data-ttu-id="37b1c-190">有关配置数据块的详细信息，请参阅[分隔配置和环境数据](../configurations/configData.md)。</span><span class="sxs-lookup"><span data-stu-id="37b1c-190">For more information on the configuration data block, see [Separating Configuration and Environment Data](../configurations/configData.md).</span></span>

<span data-ttu-id="37b1c-191">可以为与凭据加密相关的每个节点配置的元素有：</span><span class="sxs-lookup"><span data-stu-id="37b1c-191">The elements that can be configured for each node that are related to credential encryption are:</span></span>

- <span data-ttu-id="37b1c-192">**NodeName** - 为其配置凭据加密的目标节点的名称。</span><span class="sxs-lookup"><span data-stu-id="37b1c-192">**NodeName** - the name of the target node that the credential encryption is being configured for.</span></span>
- <span data-ttu-id="37b1c-193">**PsDscAllowPlainTextPassword** - 是否允许将未加密的凭据传递给此节点。</span><span class="sxs-lookup"><span data-stu-id="37b1c-193">**PsDscAllowPlainTextPassword** - whether unencrypted credentials will be allowed to be passed to this node.</span></span> <span data-ttu-id="37b1c-194">**不建议** 使用此元素。</span><span class="sxs-lookup"><span data-stu-id="37b1c-194">This is **not recommended**.</span></span>
- <span data-ttu-id="37b1c-195">**Thumbprint** -将用于在 _目标节点_ 上的 DSC 配置中解密凭据的证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="37b1c-195">**Thumbprint** - the thumbprint of the certificate that will be used to decrypt the credentials in the DSC Configuration on the _Target Node_.</span></span> <span data-ttu-id="37b1c-196">**此证书必须存在于目标节点上的本地计算机证书存储中。**</span><span class="sxs-lookup"><span data-stu-id="37b1c-196">**This certificate must exist in the Local Machine certificate store on the Target Node.**</span></span>
- <span data-ttu-id="37b1c-197">**CertificateFile** - 应该用于为 _目标节点_ 加密凭据的证书文件（只包含公钥）。</span><span class="sxs-lookup"><span data-stu-id="37b1c-197">**CertificateFile** - the certificate file (containing the public key only) that should be used to encrypt the credentials for the _Target Node_.</span></span> <span data-ttu-id="37b1c-198">它必须是 DER 编码的二进制 X.509 或 Base-64 编码的 X.509 格式证书文件。</span><span class="sxs-lookup"><span data-stu-id="37b1c-198">This must be either a DER encoded binary X.509 or Base-64 encoded X.509 format certificate file.</span></span>

<span data-ttu-id="37b1c-199">此示例显示了一个配置数据块，该数据块指定了要操作的名为 targetNode 的目标节点、公钥证书文件（名为 targetNode.cer）的路径和公钥的指纹。</span><span class="sxs-lookup"><span data-stu-id="37b1c-199">This example shows a configuration data block that specifies a target node to act on named targetNode, the path to the public key certificate file (named targetNode.cer), and the thumbprint for the public key.</span></span>

```powershell
$ConfigData= @{
    AllNodes = @(
            @{
                # The name of the node we are describing
                NodeName = "targetNode"

                # The path to the .cer file containing the
                # public key of the Encryption Certificate
                # used to encrypt credentials for this node
                CertificateFile = "C:\publicKeys\targetNode.cer"


                # The thumbprint of the Encryption Certificate
                # used to decrypt the credentials on target node
                Thumbprint = "AC23EA3A9E291A75757A556D0B71CBBF8C4F6FD8"
            }
        )
    }
```

## <a name="configuration-script"></a><span data-ttu-id="37b1c-200">配置脚本</span><span class="sxs-lookup"><span data-stu-id="37b1c-200">Configuration script</span></span>

<span data-ttu-id="37b1c-201">在配置脚本中，使用 `PsCredential` 参数确保凭据存储时间尽可能短。</span><span class="sxs-lookup"><span data-stu-id="37b1c-201">In the configuration script itself, use the `PsCredential` parameter to ensure that credentials are stored for the shortest possible time.</span></span> <span data-ttu-id="37b1c-202">运行提供的示例时，DSC 将提示你输入凭据，然后使用配置数据块中与目标节点相关联的 CertificateFile 加密 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="37b1c-202">When you run the supplied example, DSC will prompt you for credentials and then encrypt the MOF file using the CertificateFile that is associated with the target node in the configuration data block.</span></span> <span data-ttu-id="37b1c-203">此代码示例将文件从受保护共享复制到用户。</span><span class="sxs-lookup"><span data-stu-id="37b1c-203">This code example copies a file from a share that is secured to a user.</span></span>

```powershell
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
    )

    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\Server\share\path\file.ext"
            DestinationPath = "C:\destinationPath"
            Credential = $credential
        }
    }
}
```

## <a name="setting-up-decryption"></a><span data-ttu-id="37b1c-204">设置加密</span><span class="sxs-lookup"><span data-stu-id="37b1c-204">Setting up decryption</span></span>

<span data-ttu-id="37b1c-205">必须使用 CertificateID 资源验证证书的指纹，从而告知每个目标节点上的本地配置管理器用于解密凭据的证书，然后 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) 才能生效。</span><span class="sxs-lookup"><span data-stu-id="37b1c-205">Before [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) can work, you have to tell the Local Configuration Manager on each target node which certificate to use to decrypt the credentials, using the CertificateID resource to verify the certificate's thumbprint.</span></span> <span data-ttu-id="37b1c-206">此示例函数将查找适当的本地证书（你可能需要对它进行自定义，以便它准确地找到你想使用的证书）：</span><span class="sxs-lookup"><span data-stu-id="37b1c-206">This example function will find the appropriate local certificate (you might have to customize it so it will find the exact certificate you want to use):</span></span>

```powershell
# Get the certificate that works for encryption
function Get-LocalEncryptionCertificateThumbprint
{
    (dir Cert:\LocalMachine\my) | %{
        # Verify the certificate is for Encryption and valid
        if ($_.PrivateKey.KeyExchangeAlgorithm -and $_.Verify())
        {
            return $_.Thumbprint
        }
    }
}
```

<span data-ttu-id="37b1c-207">使用证书指纹标识证书后，即可更新配置脚本以使用该值：</span><span class="sxs-lookup"><span data-stu-id="37b1c-207">With the certificate identified by its thumbprint, the configuration script can be updated to use the value:</span></span>

```powershell
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
    )

    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\Server\share\path\file.ext"
            DestinationPath = "C:\destinationPath"
            Credential = $credential
        }

        LocalConfigurationManager
        {
             CertificateId = $node.Thumbprint
        }
    }
}
```

## <a name="running-the-configuration"></a><span data-ttu-id="37b1c-208">运行配置</span><span class="sxs-lookup"><span data-stu-id="37b1c-208">Running the configuration</span></span>

<span data-ttu-id="37b1c-209">此时，你可以运行配置，此操作将输出两个文件：</span><span class="sxs-lookup"><span data-stu-id="37b1c-209">At this point, you can run the configuration, which will output two files:</span></span>

- <span data-ttu-id="37b1c-210">`*.meta.mof ` 文件，它对本地配置管理器进行配置，使其使用存储在本地计算机存储区上并由其指纹标识的证书来解密凭据。</span><span class="sxs-lookup"><span data-stu-id="37b1c-210">A `*.meta.mof `file that configures the Local Configuration Manager to decrypt the credentials using the certificate that is stored on the local machine store and identified by its thumbprint.</span></span>
  <span data-ttu-id="37b1c-211">[Set-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/Set-DscLocalConfigurationManager) 应用 `*.meta.mof ` 文件。</span><span class="sxs-lookup"><span data-stu-id="37b1c-211">[Set-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/Set-DscLocalConfigurationManager) applies the `*.meta.mof `file.</span></span>
- <span data-ttu-id="37b1c-212">实际应用配置的 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="37b1c-212">A MOF file that actually applies the configuration.</span></span> <span data-ttu-id="37b1c-213">Start-DscConfiguration 应用配置。</span><span class="sxs-lookup"><span data-stu-id="37b1c-213">Start-DscConfiguration applies the configuration.</span></span>

<span data-ttu-id="37b1c-214">这些命令将完成这些步骤：</span><span class="sxs-lookup"><span data-stu-id="37b1c-214">These commands will accomplish those steps:</span></span>

```powershell
Write-Host "Generate DSC Configuration..."
CredentialEncryptionExample -ConfigurationData $ConfigData -OutputPath .\CredentialEncryptionExample

Write-Host "Setting up LCM to decrypt credentials..."
Set-DscLocalConfigurationManager .\CredentialEncryptionExample -Verbose

Write-Host "Starting Configuration..."
Start-DscConfiguration .\CredentialEncryptionExample -wait -Verbose
```

<span data-ttu-id="37b1c-215">此示例将 DSC 配置推送到目标节点。</span><span class="sxs-lookup"><span data-stu-id="37b1c-215">This example would push the DSC configuration to the target node.</span></span> <span data-ttu-id="37b1c-216">还可以使用 DSC 请求服务器（如果可用）来应用 DSC 配置。</span><span class="sxs-lookup"><span data-stu-id="37b1c-216">The DSC configuration can also be applied using a DSC Pull Server if one is available.</span></span>

<span data-ttu-id="37b1c-217">有关使用 DSC 请求服务器应用 DSC 配置的详细信息，请参阅[设置 DSC 请求客户端](pullClient.md)。</span><span class="sxs-lookup"><span data-stu-id="37b1c-217">See [Setting up a DSC pull client](pullClient.md) for more information on applying DSC configurations using a DSC Pull Server.</span></span>

## <a name="credential-encryption-module-example"></a><span data-ttu-id="37b1c-218">凭据加密模块示例</span><span class="sxs-lookup"><span data-stu-id="37b1c-218">Credential Encryption Module Example</span></span>

<span data-ttu-id="37b1c-219">以下是包含所有步骤的完整示例，以及用于导出和复制公钥的帮助程序 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="37b1c-219">Here is a full example that incorporates all of these steps, plus a helper cmdlet that exports and copies the public keys:</span></span>

```powershell
# A simple example of using credentials
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
    )

    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\server\share\file.txt"
            DestinationPath = "C:\Users\user"
            Credential = $credential
        }

        LocalConfigurationManager
        {
            CertificateId = $node.Thumbprint
        }
    }
}

# A Helper to invoke the configuration, with the correct public key
# To encrypt the configuration credentials
function Start-CredentialEncryptionExample
{
    [CmdletBinding()]
    param ($computerName)

    [string] $thumbprint = Get-EncryptionCertificate -computerName $computerName -Verbose
    Write-Verbose "using cert: $thumbprint"

    $certificatePath = join-path -Path "$env:SystemDrive\$script:publicKeyFolder" -childPath "$computername.EncryptionCertificate.cer"

    $ConfigData=    @{
        AllNodes = @(
                        @{
                            # The name of the node we are describing
                            NodeName = "$computerName"

                            # The path to the .cer file containing the
                            # public key of the Encryption Certificate
                            CertificateFile = "$certificatePath"

                            # The thumbprint of the Encryption Certificate
                            # used to decrypt the credentials
                            Thumbprint = $thumbprint
                        };
                    );
    }

    Write-Verbose "Generate DSC Configuration..."
    CredentialEncryptionExample -ConfigurationData $ConfigData -OutputPath .\CredentialEncryptionExample `
        -credential (Get-Credential -UserName "$env:USERDOMAIN\$env:USERNAME" -Message "Enter credentials for configuration")

    Write-Verbose "Setting up LCM to decrypt credentials..."
    Set-DscLocalConfigurationManager .\CredentialEncryptionExample -Verbose

    Write-Verbose "Starting Configuration..."
    Start-DscConfiguration .\CredentialEncryptionExample -wait -Verbose
}

#region HelperFunctions

# The folder name for the exported public keys
$script:publicKeyFolder = "publicKeys"

# Get the certificate that works for encryptions
function Get-EncryptionCertificate
{
    [CmdletBinding()]
    param ($computerName)

    $returnValue= Invoke-Command -ComputerName $computerName -ScriptBlock {
        $certificates = dir Cert:\LocalMachine\my

        $certificates | %{
                    # Verify the certificate is for Encryption and valid
            if ($_.PrivateKey.KeyExchangeAlgorithm -and $_.Verify())
            {
                # Create the folder to hold the exported public key
                $folder= Join-Path -Path $env:SystemDrive\ -ChildPath $using:publicKeyFolder
                if (! (Test-Path $folder))
                {
                    md $folder | Out-Null
                }

                # Export the public key to a well known location
                $certPath = Export-Certificate -Cert $_ -FilePath (Join-Path -path $folder -childPath "EncryptionCertificate.cer")

                # Return the thumbprint, and exported certificate path
                return @($_.Thumbprint,$certPath);
            }
        }
    }

    Write-Verbose "Identified and exported cert..."
    # Copy the exported certificate locally
    $destinationPath = join-path -Path "$env:SystemDrive\$script:publicKeyFolder" -childPath "$computername.EncryptionCertificate.cer"
    Copy-Item -Path (join-path -path \\$computername -childPath $returnValue[1].FullName.Replace(":","$"))  $destinationPath | Out-Null

    # Return the thumbprint
    return $returnValue[0]
}

Start-CredentialEncryptionExample
```
