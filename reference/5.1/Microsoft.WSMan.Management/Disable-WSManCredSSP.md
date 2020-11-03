---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: c34de849d664fe0c0a02b695f0fc72f54cf1ae3d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200637"
---
# <span data-ttu-id="1a0be-103">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1a0be-103">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="1a0be-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1a0be-104">SYNOPSIS</span></span>
<span data-ttu-id="1a0be-105">在计算机上禁用 CredSSP 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1a0be-105">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="1a0be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a0be-106">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="1a0be-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a0be-107">DESCRIPTION</span></span>
<span data-ttu-id="1a0be-108">**Disable-WSManCredSSP** cmdlet 在客户端或服务器计算机上禁用凭据安全支持提供程序 (CredSSP) 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1a0be-108">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="1a0be-109">当使用 CredSSP 身份验证时，用户凭据将传递给要进行身份验证的远程计算机。</span><span class="sxs-lookup"><span data-stu-id="1a0be-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="1a0be-110">此 cmdlet 通过在 Role  参数中指定 Client 来禁用客户端上的 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-110">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="1a0be-111">该 cmdlet 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a0be-111">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="1a0be-112">禁用客户端上的 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-112">Disables CredSSP on the client.</span></span> <span data-ttu-id="1a0be-113">此 cmdlet 将 WS-Management 设置 **\<localhost|computername\> \Client\Auth\CredSSP** 设置为 false。</span><span class="sxs-lookup"><span data-stu-id="1a0be-113">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="1a0be-114">从客户端上的 Windows CredSSP 策略 **AllowFreshCredentials** 中删除任何 WSMan/\* 设置。</span><span class="sxs-lookup"><span data-stu-id="1a0be-114">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="1a0be-115">通过在 Role  中指定 Server 使用该 cmdlet 禁用服务器上的 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-115">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role* .</span></span>
<span data-ttu-id="1a0be-116">该 cmdlet 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a0be-116">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="1a0be-117">禁用服务器上的 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-117">Disables CredSSP on the server.</span></span> <span data-ttu-id="1a0be-118">此 cmdlet 将 WS-Management 设置 **\<localhost|computername\> \Service\Auth\CredSSP** 设置为 false。</span><span class="sxs-lookup"><span data-stu-id="1a0be-118">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="1a0be-119">注意：CredSSP 身份验证将用户凭据从本地计算机委派给远程计算机。</span><span class="sxs-lookup"><span data-stu-id="1a0be-119">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="1a0be-120">此做法增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="1a0be-120">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="1a0be-121">如果远程计算机的安全受到威胁，则在向该计算机传递凭据时，可使用这些凭据来控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="1a0be-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="1a0be-122">示例</span><span class="sxs-lookup"><span data-stu-id="1a0be-122">EXAMPLES</span></span>

### <span data-ttu-id="1a0be-123">示例 1：禁用客户端上的 CredSSP</span><span class="sxs-lookup"><span data-stu-id="1a0be-123">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="1a0be-124">此命令禁用客户端上的 CredSSP，这会阻止到服务器的委派。</span><span class="sxs-lookup"><span data-stu-id="1a0be-124">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="1a0be-125">示例 2：禁用服务器上的 CredSSP</span><span class="sxs-lookup"><span data-stu-id="1a0be-125">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="1a0be-126">此命令禁用服务器上的 CredSSP，这会阻止从客户端委派。</span><span class="sxs-lookup"><span data-stu-id="1a0be-126">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="1a0be-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a0be-127">PARAMETERS</span></span>

### <span data-ttu-id="1a0be-128">-Role</span><span class="sxs-lookup"><span data-stu-id="1a0be-128">-Role</span></span>
<span data-ttu-id="1a0be-129">指定以客户端还是服务器的形式禁用 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-129">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="1a0be-130">此参数的可接受的值是：Client 和 Server。</span><span class="sxs-lookup"><span data-stu-id="1a0be-130">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="1a0be-131">如果指定 Client，该 cmdlet 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a0be-131">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="1a0be-132">禁用客户端上的 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-132">Disables CredSSP on the client.</span></span> <span data-ttu-id="1a0be-133">此 cmdlet 将 WS-Management 设置 **\<localhost|computername\> \Client\Auth\CredSSP** 设置为 false。</span><span class="sxs-lookup"><span data-stu-id="1a0be-133">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="1a0be-134">从客户端上的 Windows CredSSP 策略 **AllowFreshCredentials** 中删除任何 WSMan/\* 设置。</span><span class="sxs-lookup"><span data-stu-id="1a0be-134">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="1a0be-135">如果指定 Server，则该 cmdlet 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a0be-135">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="1a0be-136">禁用服务器上的 CredSSP。</span><span class="sxs-lookup"><span data-stu-id="1a0be-136">Disables CredSSP on the server.</span></span> <span data-ttu-id="1a0be-137">此 cmdlet 将 WS-Management 设置 **\<localhost|computername\> \Service\Auth\CredSSP** 设置为 false。</span><span class="sxs-lookup"><span data-stu-id="1a0be-137">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a0be-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1a0be-138">CommonParameters</span></span>
<span data-ttu-id="1a0be-139">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="1a0be-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a0be-140">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="1a0be-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a0be-141">输入</span><span class="sxs-lookup"><span data-stu-id="1a0be-141">INPUTS</span></span>

### <span data-ttu-id="1a0be-142">无</span><span class="sxs-lookup"><span data-stu-id="1a0be-142">None</span></span>
<span data-ttu-id="1a0be-143">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="1a0be-143">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="1a0be-144">输出</span><span class="sxs-lookup"><span data-stu-id="1a0be-144">OUTPUTS</span></span>

### <span data-ttu-id="1a0be-145">无</span><span class="sxs-lookup"><span data-stu-id="1a0be-145">None</span></span>
<span data-ttu-id="1a0be-146">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="1a0be-146">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1a0be-147">注释</span><span class="sxs-lookup"><span data-stu-id="1a0be-147">NOTES</span></span>

* <span data-ttu-id="1a0be-148">若要启用 CredSSP 身份验证，请使用 Enable-WSManCredSSP cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a0be-148">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="1a0be-149">相关链接</span><span class="sxs-lookup"><span data-stu-id="1a0be-149">RELATED LINKS</span></span>

[<span data-ttu-id="1a0be-150">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1a0be-150">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="1a0be-151">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1a0be-151">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="1a0be-152">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1a0be-152">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="1a0be-153">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1a0be-153">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="1a0be-154">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1a0be-154">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="1a0be-155">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="1a0be-155">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="1a0be-156">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1a0be-156">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="1a0be-157">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="1a0be-157">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="1a0be-158">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1a0be-158">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="1a0be-159">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1a0be-159">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="1a0be-160">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="1a0be-160">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="1a0be-161">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="1a0be-161">Test-WSMan</span></span>](Test-WSMan.md)
