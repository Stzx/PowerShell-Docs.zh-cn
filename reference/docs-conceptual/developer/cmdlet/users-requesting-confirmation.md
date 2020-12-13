---
ms.date: 09/13/2016
ms.topic: reference
title: 请求确认的用户
description: 请求确认的用户
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646298"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="80120-103">请求确认的用户</span><span class="sxs-lookup"><span data-stu-id="80120-103">Users Requesting Confirmation</span></span>

<span data-ttu-id="80120-104">`true`为 `SupportsShouldProcess` Cmdlet 特性声明的参数指定值时，用户可以 `Confirm` 在命令提示符处指定参数。</span><span class="sxs-lookup"><span data-stu-id="80120-104">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="80120-105">在默认的环境中，用户可以指定 `Confirm` 参数，或在 `"-Confirm:$true` 调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法时请求进行确认。</span><span class="sxs-lookup"><span data-stu-id="80120-105">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="80120-106">这会绕过 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 确认请求，即使对于影响很大的操作也是如此。</span><span class="sxs-lookup"><span data-stu-id="80120-106">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="80120-107">如果 `Confirm` 未指定，则当[](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `$ConfirmPreference` 首选项变量等于或大于 `ConfirmImpact` Cmdlet 或提供程序的设置时，ShouldProcess 调用请求确认。</span><span class="sxs-lookup"><span data-stu-id="80120-107">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="80120-108">的默认设置 `$ConfirmPreference` 为 "高"。</span><span class="sxs-lookup"><span data-stu-id="80120-108">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="80120-109">因此，在默认环境中，只有指定了影响很大的操作请求确认的 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="80120-109">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="80120-110">如果 `Confirm` 为 false 或 `"-Confirm:$false` 指定了，则 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 调用请求从用户处进行确认，并且 `$ConfirmPreference` 忽略 shell 变量。</span><span class="sxs-lookup"><span data-stu-id="80120-110">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="80120-111">备注</span><span class="sxs-lookup"><span data-stu-id="80120-111">Remarks</span></span>

- <span data-ttu-id="80120-112">对于指定但不指定（但不会）的 cmdlet 和提供程序， `SupportsShouldProcess` `ConfirmImpact` 这些操作将作为 "中影响" 操作处理，默认情况下不会提示。</span><span class="sxs-lookup"><span data-stu-id="80120-112">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="80120-113">其影响级别小于 `$ConfirmPreference` 首选项变量的默认设置。</span><span class="sxs-lookup"><span data-stu-id="80120-113">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="80120-114">如果用户指定了 `Verbose` 参数，则这些参数会得到通知，即使未提示进行确认。</span><span class="sxs-lookup"><span data-stu-id="80120-114">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="80120-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80120-115">See Also</span></span>

[<span data-ttu-id="80120-116">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="80120-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
