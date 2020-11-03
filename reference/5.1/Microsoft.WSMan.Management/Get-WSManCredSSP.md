---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: ce2046a9df5d4d02d718d6408c7a196a753c9914
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200639"
---
# <span data-ttu-id="0d541-103">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0d541-103">Get-WSManCredSSP</span></span>

## <span data-ttu-id="0d541-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0d541-104">SYNOPSIS</span></span>
<span data-ttu-id="0d541-105">获取客户端与凭据安全支持提供程序相关的配置。</span><span class="sxs-lookup"><span data-stu-id="0d541-105">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="0d541-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d541-106">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="0d541-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d541-107">DESCRIPTION</span></span>
<span data-ttu-id="0d541-108">**Enable-wsmancredssp** cmdlet 将获取客户端和服务器的与凭据安全支持提供程序相关的配置。</span><span class="sxs-lookup"><span data-stu-id="0d541-108">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="0d541-109">输出将指示凭据安全支持提供程序 (CredSSP) 身份验证已启用还是已禁用。</span><span class="sxs-lookup"><span data-stu-id="0d541-109">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="0d541-110">此 cmdlet 还显示 CredSSP 的 **AllowFreshCredentials** 策略的配置信息。</span><span class="sxs-lookup"><span data-stu-id="0d541-110">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="0d541-111">使用 CredSSP 身份验证时，用户凭据将传递给要进行身份验证的远程计算机。</span><span class="sxs-lookup"><span data-stu-id="0d541-111">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="0d541-112">此类型的身份验证旨在用于从一个远程会话创建另一个远程会话的命令。</span><span class="sxs-lookup"><span data-stu-id="0d541-112">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="0d541-113">例如，若要在远程计算机上运行后台作业，可以使用此类型的身份验证。</span><span class="sxs-lookup"><span data-stu-id="0d541-113">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="0d541-114">该 cmdlet 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0d541-114">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="0d541-115">获取客户端 ( **\<localhost|computername\> \Client\Auth\CredSSP** ) 上的 WS-Management CredSSP 设置。</span><span class="sxs-lookup"><span data-stu-id="0d541-115">Gets the WS-Management CredSSP setting on the client ( **\<localhost|computername\>\Client\Auth\CredSSP** ).</span></span>
- <span data-ttu-id="0d541-116">获取 Windows CredSSP 策略设置 **AllowFreshCredentials** 。</span><span class="sxs-lookup"><span data-stu-id="0d541-116">Gets the Windows CredSSP policy setting **AllowFreshCredentials** .</span></span>
- <span data-ttu-id="0d541-117">获取服务器上的 WS-Management CredSSP 设置 ( **\<localhost|computername\> \Service\Auth\CredSSP** ) 。</span><span class="sxs-lookup"><span data-stu-id="0d541-117">Gets the WS-Management CredSSP setting on the server ( **\<localhost|computername\>\Service\Auth\CredSSP** ).</span></span>

<span data-ttu-id="0d541-118">注意：CredSSP 身份验证将用户凭据从本地计算机委派给远程计算机。</span><span class="sxs-lookup"><span data-stu-id="0d541-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="0d541-119">此做法增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="0d541-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="0d541-120">如果远程计算机的安全受到威胁，则在向该计算机传递凭据时，可使用这些凭据来控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="0d541-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="0d541-121">示例</span><span class="sxs-lookup"><span data-stu-id="0d541-121">EXAMPLES</span></span>

### <span data-ttu-id="0d541-122">示例1：显示 CredSSP 配置</span><span class="sxs-lookup"><span data-stu-id="0d541-122">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="0d541-123">此命令将显示客户端和服务器的 CredSSP 配置信息。</span><span class="sxs-lookup"><span data-stu-id="0d541-123">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="0d541-124">输出将标识此计算机是否针对 CredSSP 进行了配置。</span><span class="sxs-lookup"><span data-stu-id="0d541-124">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="0d541-125">如果计算机针对 CredSSP 进行了配置，则输出如下：</span><span class="sxs-lookup"><span data-stu-id="0d541-125">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="0d541-126">如果计算机未针对 CredSSP 进行配置，则输出如下：</span><span class="sxs-lookup"><span data-stu-id="0d541-126">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="0d541-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d541-127">PARAMETERS</span></span>

### <span data-ttu-id="0d541-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0d541-128">CommonParameters</span></span>
<span data-ttu-id="0d541-129">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0d541-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d541-130">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0d541-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d541-131">输入</span><span class="sxs-lookup"><span data-stu-id="0d541-131">INPUTS</span></span>

### <span data-ttu-id="0d541-132">无</span><span class="sxs-lookup"><span data-stu-id="0d541-132">None</span></span>
<span data-ttu-id="0d541-133">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="0d541-133">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="0d541-134">输出</span><span class="sxs-lookup"><span data-stu-id="0d541-134">OUTPUTS</span></span>

### <span data-ttu-id="0d541-135">无</span><span class="sxs-lookup"><span data-stu-id="0d541-135">None</span></span>
<span data-ttu-id="0d541-136">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="0d541-136">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0d541-137">注释</span><span class="sxs-lookup"><span data-stu-id="0d541-137">NOTES</span></span>

* <span data-ttu-id="0d541-138">若要禁用 CredSSP 身份验证，请使用 Disable-WSManCredSSP cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d541-138">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="0d541-139">若要启用 CredSSP 身份验证，请使用 Enable-WSManCredSSP cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d541-139">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="0d541-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="0d541-140">RELATED LINKS</span></span>

[<span data-ttu-id="0d541-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0d541-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="0d541-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0d541-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="0d541-143">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0d541-143">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="0d541-144">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0d541-144">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="0d541-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0d541-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="0d541-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0d541-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="0d541-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0d541-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="0d541-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="0d541-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="0d541-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0d541-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="0d541-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0d541-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="0d541-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="0d541-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="0d541-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="0d541-152">Test-WSMan</span></span>](Test-WSMan.md)