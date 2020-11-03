---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198052"
---
# <span data-ttu-id="2623a-103">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="2623a-103">Reset-ComputerMachinePassword</span></span>

## <span data-ttu-id="2623a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2623a-104">SYNOPSIS</span></span>
<span data-ttu-id="2623a-105">重置计算机的计算机帐户密码。</span><span class="sxs-lookup"><span data-stu-id="2623a-105">Resets the machine account password for the computer.</span></span>

## <span data-ttu-id="2623a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2623a-106">SYNTAX</span></span>

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2623a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2623a-107">DESCRIPTION</span></span>
<span data-ttu-id="2623a-108">**Reset-computermachinepassword** cmdlet 将更改计算机用于向域中的域控制器进行身份验证的计算机帐户密码。</span><span class="sxs-lookup"><span data-stu-id="2623a-108">The **Reset-ComputerMachinePassword** cmdlet changes the computer account password that the computers use to authenticate to the domain controllers in the domain.</span></span>
<span data-ttu-id="2623a-109">你可以使用它重置本地计算机的密码。</span><span class="sxs-lookup"><span data-stu-id="2623a-109">You can use it to reset the password of the local computer.</span></span>

## <span data-ttu-id="2623a-110">示例</span><span class="sxs-lookup"><span data-stu-id="2623a-110">EXAMPLES</span></span>

### <span data-ttu-id="2623a-111">示例1：重置本地计算机的密码</span><span class="sxs-lookup"><span data-stu-id="2623a-111">Example 1: Reset the password for the local computer</span></span>

```
PS C:\> Reset-ComputerMachinePassword
```

<span data-ttu-id="2623a-112">此命令重置本地计算机的计算机密码。</span><span class="sxs-lookup"><span data-stu-id="2623a-112">This command resets the computer password for the local computer.</span></span>
<span data-ttu-id="2623a-113">该命令使用当前用户的凭据运行。</span><span class="sxs-lookup"><span data-stu-id="2623a-113">The command runs with the credentials of the current user.</span></span>

### <span data-ttu-id="2623a-114">示例2：使用指定的域控制器重置本地计算机的密码</span><span class="sxs-lookup"><span data-stu-id="2623a-114">Example 2: Reset the password for the local computer by using a specified domain controller</span></span>

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

<span data-ttu-id="2623a-115">此命令使用 DC01 域控制器重置本地计算机的计算机密码。</span><span class="sxs-lookup"><span data-stu-id="2623a-115">This command resets the computer password of the local computer by using the DC01 domain controller.</span></span>
<span data-ttu-id="2623a-116">它使用 *Credential* 参数指定有权在域中重置计算机密码的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2623a-116">It uses the *Credential* parameter to specify a user account that has permission to reset a computer password in the domain.</span></span>

### <span data-ttu-id="2623a-117">示例3：重置远程计算机上的密码</span><span class="sxs-lookup"><span data-stu-id="2623a-117">Example 3: Reset the password on a remote computer</span></span>

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

<span data-ttu-id="2623a-118">此命令使用 Invoke-Command cmdlet 在 Server01 远程计算机上运行 **reset-computermachinepassword** 命令。</span><span class="sxs-lookup"><span data-stu-id="2623a-118">This command uses the Invoke-Command cmdlet to run a **Reset-ComputerMachinePassword** command on the Server01 remote computer.</span></span>

<span data-ttu-id="2623a-119">有关 Windows PowerShell 中远程命令的详细信息，请参阅 about_Remote 和 **调用-命令** 。</span><span class="sxs-lookup"><span data-stu-id="2623a-119">For more information about remote commands in Windows PowerShell, see about_Remote and **Invoke-Command** .</span></span>

## <span data-ttu-id="2623a-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2623a-120">PARAMETERS</span></span>

### <span data-ttu-id="2623a-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="2623a-121">-Credential</span></span>
<span data-ttu-id="2623a-122">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2623a-122">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="2623a-123">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="2623a-123">The default is the current user.</span></span>

<span data-ttu-id="2623a-124">键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如 Get-Credential cmdlet 生成的一个 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="2623a-124">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="2623a-125">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="2623a-125">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="2623a-126">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="2623a-126">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2623a-127">-Server</span><span class="sxs-lookup"><span data-stu-id="2623a-127">-Server</span></span>
<span data-ttu-id="2623a-128">指定此 cmdlet 设置计算机帐户密码时使用的域控制器的名称。</span><span class="sxs-lookup"><span data-stu-id="2623a-128">Specifies the name of a domain controller to use when this cmdlet sets the computer account password.</span></span>

<span data-ttu-id="2623a-129">此参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="2623a-129">This parameter is optional.</span></span>
<span data-ttu-id="2623a-130">如果省略此参数，则将选择域控制器来处理该命令。</span><span class="sxs-lookup"><span data-stu-id="2623a-130">If you omit this parameter, a domain controller is chosen to service the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2623a-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2623a-131">-Confirm</span></span>
<span data-ttu-id="2623a-132">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="2623a-132">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2623a-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2623a-133">-WhatIf</span></span>
<span data-ttu-id="2623a-134">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="2623a-134">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2623a-135">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2623a-135">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2623a-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2623a-136">CommonParameters</span></span>
<span data-ttu-id="2623a-137">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2623a-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2623a-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2623a-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2623a-139">输入</span><span class="sxs-lookup"><span data-stu-id="2623a-139">INPUTS</span></span>

### <span data-ttu-id="2623a-140">无</span><span class="sxs-lookup"><span data-stu-id="2623a-140">None</span></span>
<span data-ttu-id="2623a-141">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2623a-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2623a-142">输出</span><span class="sxs-lookup"><span data-stu-id="2623a-142">OUTPUTS</span></span>

### <span data-ttu-id="2623a-143">无</span><span class="sxs-lookup"><span data-stu-id="2623a-143">None</span></span>
<span data-ttu-id="2623a-144">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="2623a-144">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2623a-145">注释</span><span class="sxs-lookup"><span data-stu-id="2623a-145">NOTES</span></span>

## <span data-ttu-id="2623a-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="2623a-146">RELATED LINKS</span></span>

## <span data-ttu-id="2623a-147">相关链接</span><span class="sxs-lookup"><span data-stu-id="2623a-147">RELATED LINKS</span></span>
