---
description: 说明 windows PowerShell 4.0 在 Windows RT 8.1 上的限制。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200039"
---
# <a name="about-windows-rt"></a><span data-ttu-id="c93ae-104">关于 Windows RT</span><span class="sxs-lookup"><span data-stu-id="c93ae-104">About Windows RT</span></span>

## <a name="short-description"></a><span data-ttu-id="c93ae-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="c93ae-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="c93ae-106">说明 windows PowerShell 4.0 在 Windows RT 8.1 上的限制。</span><span class="sxs-lookup"><span data-stu-id="c93ae-106">Explains limitations of  Windows PowerShell 4.0 on Windows RT 8.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="c93ae-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="c93ae-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c93ae-108">Windows RT 8.1 操作系统安装在 (（如 Microsoft Surface 2）上的计算机和设备上，在这种情况下，它是随计算机一起提供的操作系统) 使用高级 RISC 计算机 (ARM) 处理器。</span><span class="sxs-lookup"><span data-stu-id="c93ae-108">The Windows RT 8.1 operating system is installed on computers and devices (such as Microsoft Surface 2, on which it is the operating system that ships with the computer) that use Advanced RISC Machine (ARM) processors.</span></span>

<span data-ttu-id="c93ae-109">Windows PowerShell 4.0 包含在 Windows RT 8.1 中。</span><span class="sxs-lookup"><span data-stu-id="c93ae-109">Windows PowerShell 4.0 is included in Windows RT 8.1.</span></span> <span data-ttu-id="c93ae-110">所有适用于 Windows PowerShell 2.0 和更高版本的 cmdlet、提供程序、模块和大多数脚本都在 Windows RT 8.1 上运行，无需更改。</span><span class="sxs-lookup"><span data-stu-id="c93ae-110">All cmdlets, providers, and modules, and most scripts designed for Windows PowerShell 2.0 and later releases run on Windows RT 8.1 without changes.</span></span>

<span data-ttu-id="c93ae-111">因为 Windows RT 8.1 不包含所有 Windows 功能，所以，某些 Windows PowerShell 功能的工作方式不同或在基于 Windows RT 的设备上不起作用。</span><span class="sxs-lookup"><span data-stu-id="c93ae-111">Because Windows RT 8.1 does not include all Windows features, some Windows PowerShell features work differently or do not work on Windows RT-based devices.</span></span> <span data-ttu-id="c93ae-112">下表说明了这些差异。</span><span class="sxs-lookup"><span data-stu-id="c93ae-112">The following list explains the differences.</span></span>

- <span data-ttu-id="c93ae-113">Windows PowerShell ISE 不包含在中，并且无法在 Windows RT 8.1 上运行。</span><span class="sxs-lookup"><span data-stu-id="c93ae-113">Windows PowerShell ISE is not included in and cannot run on Windows RT 8.1.</span></span>
  <span data-ttu-id="c93ae-114">Windows PowerShell ISE 需要 Windows Presentation Foundation，但不包括在 Windows RT 8.1 中。</span><span class="sxs-lookup"><span data-stu-id="c93ae-114">Windows PowerShell ISE requires Windows Presentation Foundation, which is not included in Windows RT 8.1.</span></span>

- <span data-ttu-id="c93ae-115">默认情况下，Windows PowerShell 远程处理和 WinRM 服务处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="c93ae-115">Windows PowerShell remoting and the WinRM service are disabled by default.</span></span>
  <span data-ttu-id="c93ae-116">若要启用远程处理，请运行 Enable-PSRemoting cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c93ae-116">To enable remoting, run the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="c93ae-117">同时，运行 Set-Service cmdlet 将 WinRM 服务的启动类型设置为 "自动" 或 "自动 (延迟启动) "。</span><span class="sxs-lookup"><span data-stu-id="c93ae-117">Also, run the Set-Service cmdlet to set the startup type of the WinRM service to Automatic, or Automatic (Delayed Start).</span></span>

  <span data-ttu-id="c93ae-118">当远程处理处于禁用状态时，你可以使用 Windows PowerShell 远程处理在其他计算机上运行命令，但其他计算机无法在 Windows RT 设备上运行命令。</span><span class="sxs-lookup"><span data-stu-id="c93ae-118">While remoting is disabled, you can use Windows PowerShell remoting to run commands on other computers, but other computers cannot run commands on the Windows RT device.</span></span> <span data-ttu-id="c93ae-119">此外，隐式远程处理-即，内置到 cmdlet 或脚本中的远程处理，并且未使用添加的参数显式请求</span><span class="sxs-lookup"><span data-stu-id="c93ae-119">Also, implicit remoting - that is, remoting that is built in to a cmdlet or script, and not explicitly requested with added parameters</span></span>
  - <span data-ttu-id="c93ae-120">不适用于在 Windows RT 8.1 上运行的 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c93ae-120">does not work in Windows PowerShell running on Windows RT 8.1.</span></span>

- <span data-ttu-id="c93ae-121">Windows RT 8.1 不支持已加入域的计算和 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c93ae-121">Domain-joined computing and Kerberos authentication are not supported on Windows RT 8.1.</span></span> <span data-ttu-id="c93ae-122">不能使用 Windows PowerShell 添加或管理这些功能。</span><span class="sxs-lookup"><span data-stu-id="c93ae-122">You cannot use Windows PowerShell to add or manage these features.</span></span>

- <span data-ttu-id="c93ae-123">Windows rt 8.1 8.1 上的 Windows PowerShell 中也不支持 Windows RT 不支持 Microsoft .NET 框架类。</span><span class="sxs-lookup"><span data-stu-id="c93ae-123">Microsoft .NET Framework classes that are not supported on Windows RT 8.1 are also not supported by Windows PowerShell on Windows RT 8.1.</span></span>

- <span data-ttu-id="c93ae-124">在 Windows RT 8.1 上不启用事务。</span><span class="sxs-lookup"><span data-stu-id="c93ae-124">Transactions are not enabled on Windows RT 8.1.</span></span> <span data-ttu-id="c93ae-125">事务 cmdlet （如 Start Transaction 和 transaction 参数，如 UseTransaction）不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c93ae-125">Transaction cmdlets, such as Start-Transaction, and transaction parameters, such as UseTransaction, do not work properly.</span></span>

- <span data-ttu-id="c93ae-126">Windows RT 8.1 设备上的所有 Windows PowerShell 会话都使用 ConstrainedLanguage 语言模式。</span><span class="sxs-lookup"><span data-stu-id="c93ae-126">All Windows PowerShell sessions on Windows RT 8.1 devices use the ConstrainedLanguage language mode.</span></span> <span data-ttu-id="c93ae-127">ConstrainedLanguage 语言模式是用户模式代码完整性的伴随 (UMCI) 。</span><span class="sxs-lookup"><span data-stu-id="c93ae-127">ConstrainedLanguage language mode is a companion to User Mode Code Integrity (UMCI).</span></span> <span data-ttu-id="c93ae-128">它允许所有 Windows cmdlet 和 Windows PowerShell 语言元素，但会限制类型，以确保用户无法使用 Windows PowerShell 来绕过或违反 UMCI 保护。</span><span class="sxs-lookup"><span data-stu-id="c93ae-128">It permits all Windows cmdlets and Windows PowerShell language elements, but restricts types to ensure that users cannot use Windows PowerShell to circumvent or violate the UMCI protections.</span></span>

<span data-ttu-id="c93ae-129">有关 ConstrainedLanguage 语言模式的详细信息，请参阅 [about_Language_Modes](about_Language_Modes.md)。</span><span class="sxs-lookup"><span data-stu-id="c93ae-129">For more information about ConstrainedLanguage language mode, see [about_Language_Modes](about_Language_Modes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c93ae-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c93ae-130">SEE ALSO</span></span>

[<span data-ttu-id="c93ae-131">about_Language_Modes</span><span class="sxs-lookup"><span data-stu-id="c93ae-131">about_Language_Modes</span></span>](about_Language_Modes.md)

[<span data-ttu-id="c93ae-132">about_Remote</span><span class="sxs-lookup"><span data-stu-id="c93ae-132">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="c93ae-133">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="c93ae-133">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)
