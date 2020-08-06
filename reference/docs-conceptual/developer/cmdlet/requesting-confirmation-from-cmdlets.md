---
title: 正在从 Cmdlet 请求确认 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.openlocfilehash: bcc4c766d0012e7173550e3b6cb3ef058baa06bb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781794"
---
# <a name="requesting-confirmation-from-cmdlets"></a><span data-ttu-id="b36bb-102">请求 Cmdlet 确认</span><span class="sxs-lookup"><span data-stu-id="b36bb-102">Requesting Confirmation from Cmdlets</span></span>

<span data-ttu-id="b36bb-103">当 cmdlet 要对 Windows PowerShell 环境之外的系统进行更改时，应请求确认。</span><span class="sxs-lookup"><span data-stu-id="b36bb-103">Cmdlets should request confirmation when they are about to make a change to the system that is outside of the Windows PowerShell environment.</span></span> <span data-ttu-id="b36bb-104">例如，如果某个 cmdlet 要添加用户帐户或停止进程，则该 cmdlet 会在继续操作之前要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="b36bb-104">For example, if a cmdlet is about to add a user account or stop a process, the cmdlet should require confirmation from the user before it proceeds.</span></span> <span data-ttu-id="b36bb-105">相反，如果 cmdlet 要更改 Windows PowerShell 变量，则 cmdlet 不需要确认。</span><span class="sxs-lookup"><span data-stu-id="b36bb-105">In contrast, if a cmdlet is about to change a Windows PowerShell variable, the cmdlet does not need to require confirmation.</span></span>

<span data-ttu-id="b36bb-106">为了发出确认请求，该 cmdlet 必须指示它支持确认请求，并且它必须调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)和[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (可选的) 方法来显示确认请求消息，然后才能发出确认请求消息。</span><span class="sxs-lookup"><span data-stu-id="b36bb-106">In order to make a confirmation request, the cmdlet must indicate that it supports confirmation requests, and it must call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (optional) methods to display a confirmation request message.</span></span>

## <a name="supporting-confirmation-requests"></a><span data-ttu-id="b36bb-107">支持确认请求</span><span class="sxs-lookup"><span data-stu-id="b36bb-107">Supporting Confirmation Requests</span></span>

<span data-ttu-id="b36bb-108">为了支持确认请求，cmdlet 必须将 `SupportsShouldProcess` cmdlet 特性的参数设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b36bb-108">To support confirmation requests, the cmdlet must set the `SupportsShouldProcess` parameter of the Cmdlet attribute to `true`.</span></span> <span data-ttu-id="b36bb-109">这将启用 `Confirm` `WhatIf` Windows PowerShell 提供的和 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="b36bb-109">This enables the `Confirm` and `WhatIf` cmdlet parameters that are provided by Windows PowerShell.</span></span> <span data-ttu-id="b36bb-110">`Confirm`参数允许用户控制是否显示确认请求。</span><span class="sxs-lookup"><span data-stu-id="b36bb-110">The `Confirm` parameter allows the user to control whether the confirmation request is displayed.</span></span> <span data-ttu-id="b36bb-111">此 `WhatIf` 参数允许用户确定该 cmdlet 是否应显示消息或执行其操作。</span><span class="sxs-lookup"><span data-stu-id="b36bb-111">The `WhatIf` parameter allows the user to determine whether the cmdlet should display a message or perform its action.</span></span> <span data-ttu-id="b36bb-112">不要将 `Confirm` 和参数手动添加 `WhatIf` 到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b36bb-112">Do not manually add the `Confirm` and `WhatIf` parameters to a cmdlet.</span></span>

<span data-ttu-id="b36bb-113">下面的示例演示支持确认请求的 Cmdlet 特性声明。</span><span class="sxs-lookup"><span data-stu-id="b36bb-113">The following example shows a Cmdlet attribute declaration that supports confirmation requests.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a><span data-ttu-id="b36bb-114">调用确认请求方法</span><span class="sxs-lookup"><span data-stu-id="b36bb-114">Calling the Confirmation request methods</span></span>

<span data-ttu-id="b36bb-115">在 cmdlet 代码中，先调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法，然后再执行更改系统的操作。</span><span class="sxs-lookup"><span data-stu-id="b36bb-115">In the cmdlet code, call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method before the operation that changes the system is performed.</span></span> <span data-ttu-id="b36bb-116">设计 cmdlet，以便在调用返回的值 `false` 时，不会执行操作，并且该 cmdlet 将处理下一个操作。</span><span class="sxs-lookup"><span data-stu-id="b36bb-116">Design the cmdlet so that if the call returns a value of `false`, the operation is not performed, and the cmdlet processes the next operation.</span></span>

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="b36bb-117">调用 ShouldContinue 方法</span><span class="sxs-lookup"><span data-stu-id="b36bb-117">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="b36bb-118">大多数 cmdlet 只请求使用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法进行确认。</span><span class="sxs-lookup"><span data-stu-id="b36bb-118">Most cmdlets request confirmation using only the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="b36bb-119">但某些情况下，可能需要额外的确认。</span><span class="sxs-lookup"><span data-stu-id="b36bb-119">However, some cases might require additional confirmation.</span></span> <span data-ttu-id="b36bb-120">对于这些情况，请使用对[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的调用对[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)调用进行补充，从而对其进行补充。</span><span class="sxs-lookup"><span data-stu-id="b36bb-120">For these cases, supplement the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call with a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method.</span></span> <span data-ttu-id="b36bb-121">这使 cmdlet 或提供程序可以更好地控制对确认提示的所有响应的 **"是"** 的范围。</span><span class="sxs-lookup"><span data-stu-id="b36bb-121">This allows the cmdlet or provider to more finely control the scope of the **Yes to all** response to the confirmation prompt.</span></span>

<span data-ttu-id="b36bb-122">如果某个 cmdlet 调用[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法，则该 cmdlet 还必须提供一个 `Force` 开关参数。</span><span class="sxs-lookup"><span data-stu-id="b36bb-122">If a cmdlet calls the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method, the cmdlet must also provide a `Force` switch parameter.</span></span> <span data-ttu-id="b36bb-123">如果用户在 `Force` 用户调用 cmdlet 时指定了，则该 cmdlet 仍应调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)，但它应绕过对[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)的调用，但不会调用。</span><span class="sxs-lookup"><span data-stu-id="b36bb-123">If the user specifies `Force` when the user invokes the cmdlet, the cmdlet should still call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), but it should bypass the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

<span data-ttu-id="b36bb-124">当从非交互式环境中调用[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)时，将引发异常，而不会提示用户。</span><span class="sxs-lookup"><span data-stu-id="b36bb-124">[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) will throw an exception when it is called from a non-interactive environment where the user cannot be prompted.</span></span> <span data-ttu-id="b36bb-125">添加 `Force` 参数可确保在非交互式环境中调用命令时仍可执行该命令。</span><span class="sxs-lookup"><span data-stu-id="b36bb-125">Adding a `Force` parameter ensures that the command can still be performed when it is invoked in a non-interactive environment.</span></span>

<span data-ttu-id="b36bb-126">下面的示例演示了如何调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)和[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)的情况下出现的情况下。</span><span class="sxs-lookup"><span data-stu-id="b36bb-126">The following example shows how to call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

<span data-ttu-id="b36bb-127">[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)调用的行为可能会有所不同，具体取决于调用该 Cmdlet 时使用的环境。</span><span class="sxs-lookup"><span data-stu-id="b36bb-127">The behavior of a [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call can vary depending on the environment in which the cmdlet is invoked.</span></span> <span data-ttu-id="b36bb-128">使用前面的准则有助于确保 cmdlet 与其他 cmdlet 的行为一致，而不考虑主机环境。</span><span class="sxs-lookup"><span data-stu-id="b36bb-128">Using the previous guidelines will help ensure that the cmdlet behaves consistently with other cmdlets, regardless of the host environment.</span></span>

<span data-ttu-id="b36bb-129">有关如何调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法的示例，请参阅[如何请求确认](./how-to-request-confirmations.md)。</span><span class="sxs-lookup"><span data-stu-id="b36bb-129">For an example of calling the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specify-the-impact-level"></a><span data-ttu-id="b36bb-130">指定影响级别</span><span class="sxs-lookup"><span data-stu-id="b36bb-130">Specify the Impact Level</span></span>

<span data-ttu-id="b36bb-131">创建 cmdlet 时，指定影响级别 (更改的严重性) 。</span><span class="sxs-lookup"><span data-stu-id="b36bb-131">When you create the cmdlet, specify the impact level (the severity) of the change.</span></span> <span data-ttu-id="b36bb-132">为此，请将 `ConfirmImpact` Cmdlet 属性的参数值设置为 "高"、"中" 或 "低"。</span><span class="sxs-lookup"><span data-stu-id="b36bb-132">To do this, set the value of the `ConfirmImpact` parameter of the Cmdlet attribute to High, Medium, or Low.</span></span> <span data-ttu-id="b36bb-133">`ConfirmImpact`仅当同时指定 cmdlet 的参数时，才可以指定的值 `SupportsShouldProcess` 。</span><span class="sxs-lookup"><span data-stu-id="b36bb-133">You can specify a value for `ConfirmImpact` only when you also specify the `SupportsShouldProcess` parameter for the cmdlet.</span></span>

<span data-ttu-id="b36bb-134">对于大多数 cmdlet，无需显式指定 `ConfirmImpact` 。</span><span class="sxs-lookup"><span data-stu-id="b36bb-134">For most cmdlets, you do not have to explicitly specify `ConfirmImpact`.</span></span>  <span data-ttu-id="b36bb-135">请改用参数的默认设置，即 "中"。</span><span class="sxs-lookup"><span data-stu-id="b36bb-135">Instead, use the default setting of the parameter, which is Medium.</span></span> <span data-ttu-id="b36bb-136">如果将设置 `ConfirmImpact` 为 "高"，则默认情况下将确认操作。</span><span class="sxs-lookup"><span data-stu-id="b36bb-136">If you set `ConfirmImpact` to High, the operation will be confirmed by default.</span></span> <span data-ttu-id="b36bb-137">为高度中断操作（如重新格式化硬盘卷）保留此设置。</span><span class="sxs-lookup"><span data-stu-id="b36bb-137">Reserve this setting for highly disruptive actions, such as reformatting a hard-disk volume.</span></span>

## <a name="calling-non-confirmation-methods"></a><span data-ttu-id="b36bb-138">调用非确认方法</span><span class="sxs-lookup"><span data-stu-id="b36bb-138">Calling Non-Confirmation Methods</span></span>

<span data-ttu-id="b36bb-139">如果 cmdlet 或提供程序必须发送消息但未请求确认，则它可以调用以下三种方法。</span><span class="sxs-lookup"><span data-stu-id="b36bb-139">If the cmdlet or provider must send a message but not request confirmation, it can call the following three methods.</span></span> <span data-ttu-id="b36bb-140">避免使用[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)方法发送这些类型的消息，因为[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)输出与 Cmdlet 或提供程序的正常输出混在一起，这会使脚本编写变得很困难。</span><span class="sxs-lookup"><span data-stu-id="b36bb-140">Avoid using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method to send messages of these types because [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) output is intermingled with the normal output of your cmdlet or provider, which makes script writing difficult.</span></span>

- <span data-ttu-id="b36bb-141">若要警告用户并继续操作，cmdlet 或提供程序可以调用[WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)方法来调用。</span><span class="sxs-lookup"><span data-stu-id="b36bb-141">To caution the user and continue with the operation, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

- <span data-ttu-id="b36bb-142">若要提供用户可以使用参数检索的其他信息 `Verbose` ，cmdlet 或提供程序可以调用[WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)方法。</span><span class="sxs-lookup"><span data-stu-id="b36bb-142">To provide additional information that the user can retrieve using the `Verbose` parameter, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span>

- <span data-ttu-id="b36bb-143">若要为其他开发人员或产品支持提供调试级别的详细信息，cmdlet 或提供程序可以调用[WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)方法。</span><span class="sxs-lookup"><span data-stu-id="b36bb-143">To provide debugging-level detail for other developers or for product support, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span> <span data-ttu-id="b36bb-144">用户可以使用参数检索此信息 `Debug` 。</span><span class="sxs-lookup"><span data-stu-id="b36bb-144">The user can retrieve this information using the `Debug` parameter.</span></span>

<span data-ttu-id="b36bb-145">Cmdlet 和提供程序在尝试执行更改 Windows PowerShell 之外的系统的操作之前，先调用以下方法来请求确认：</span><span class="sxs-lookup"><span data-stu-id="b36bb-145">Cmdlets and providers first call the following methods to request confirmation before they attempt to perform an operation that changes a system outside of Windows PowerShell:</span></span>

- [<span data-ttu-id="b36bb-146">"Shouldprocess"。</span><span class="sxs-lookup"><span data-stu-id="b36bb-146">System.Management.Automation.Cmdlet.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [<span data-ttu-id="b36bb-147">Cmdletprovider. "Shouldprocess"</span><span class="sxs-lookup"><span data-stu-id="b36bb-147">System.Management.Automation.Provider.Cmdletprovider.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

<span data-ttu-id="b36bb-148">它们通过调用[Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法来执行此操作，这会提示用户根据用户调用命令的方式确认操作。</span><span class="sxs-lookup"><span data-stu-id="b36bb-148">They do so by calling the [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, which prompts the user to confirm the operation based on how the user invoked the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="b36bb-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b36bb-149">See Also</span></span>

[<span data-ttu-id="b36bb-150">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b36bb-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
