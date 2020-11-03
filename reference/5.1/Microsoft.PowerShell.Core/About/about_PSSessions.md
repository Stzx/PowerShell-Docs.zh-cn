---
description: 介绍 (Pssession) 的 Windows PowerShell 会话，并说明如何建立与远程计算机的持续连接。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: 0bf3e24ca11108b5ab4739abd9be530243c50f11
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200279"
---
# <a name="about-pssessions"></a><span data-ttu-id="567b1-104">关于 Pssession</span><span class="sxs-lookup"><span data-stu-id="567b1-104">About PSSessions</span></span>

## <a name="short-description"></a><span data-ttu-id="567b1-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="567b1-105">Short Description</span></span>

<span data-ttu-id="567b1-106">介绍 (Pssession) 的 Windows PowerShell 会话，并说明如何建立与远程计算机的持续连接。</span><span class="sxs-lookup"><span data-stu-id="567b1-106">Describes Windows PowerShell sessions (PSSessions) and explains how to establish a persistent connection to a remote computer.</span></span>

## <a name="long-description"></a><span data-ttu-id="567b1-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="567b1-107">Long Description</span></span>

<span data-ttu-id="567b1-108">若要在远程计算机上运行 Windows PowerShell 命令，可以使用 cmdlet 的 **ComputerName** 参数，也可以 (pssession) 创建 Windows powershell 会话，并在 pssession 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-108">To run Windows PowerShell commands on a remote computer, you can use the **ComputerName** parameter of a cmdlet, or you can create a Windows PowerShell session (PSSession) and run commands in the PSSession.</span></span>

<span data-ttu-id="567b1-109">当你创建 PSSession 时，Windows PowerShell 将建立与远程计算机的持续性连接。</span><span class="sxs-lookup"><span data-stu-id="567b1-109">When you create a PSSession, Windows PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="567b1-110">使用 PSSession 在远程计算机上运行一系列相关命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-110">Use a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="567b1-111">在同一 PSSession 中运行的命令可以共享数据，例如变量、别名和函数的值。</span><span class="sxs-lookup"><span data-stu-id="567b1-111">Commands that run in the same PSSession can share data, such as the values of variables, aliases, and functions.</span></span>

<span data-ttu-id="567b1-112">你还可以在本地计算机上创建 PSSession，并在其中运行命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-112">You can also create a PSSession on the local computer and run commands in it.</span></span>
<span data-ttu-id="567b1-113">本地 PSSession 使用 Windows PowerShell 远程处理基础结构来创建和维护 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-113">A local PSSession uses the Windows PowerShell remoting infrastructure to create and maintain the PSSession.</span></span>

<span data-ttu-id="567b1-114">从 Windows PowerShell 3.0 开始，Pssession 独立于在其中创建它们的会话。</span><span class="sxs-lookup"><span data-stu-id="567b1-114">Beginning in Windows PowerShell 3.0, PSSessions are independent of the sessions in which they are created.</span></span> <span data-ttu-id="567b1-115">活动的 Pssession 在远程计算机 (或远程端的计算机或连接) 的 "服务器端" 进行维护。</span><span class="sxs-lookup"><span data-stu-id="567b1-115">Active PSSessions are maintained on the remote computer (or the computer at the remote end or "server-side" of the connection).</span></span> <span data-ttu-id="567b1-116">因此，你可以断开与 PSSession 的连接，并在以后从同一台计算机或另一台计算机重新连接到它。</span><span class="sxs-lookup"><span data-stu-id="567b1-116">As a result, you can disconnect from the PSSession and reconnect to it at a later time from the same computer or from a different computer.</span></span>

<span data-ttu-id="567b1-117">本主题介绍如何创建、使用、获取和删除 Pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-117">This topic explains how to create, use, get, and delete PSSessions.</span></span> <span data-ttu-id="567b1-118">有关更高级的信息，请参阅 [about_PSSession_Details](about_PSSession_Details.md)。</span><span class="sxs-lookup"><span data-stu-id="567b1-118">For more advanced information, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

<span data-ttu-id="567b1-119">注意： Pssession 使用 Windows PowerShell 远程处理基础结构。</span><span class="sxs-lookup"><span data-stu-id="567b1-119">Note: PSSessions use the Windows PowerShell remoting infrastructure.</span></span> <span data-ttu-id="567b1-120">若要使用 Pssession，必须为本地和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="567b1-120">To use PSSessions, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="567b1-121">有关详细信息，请参阅 [about_Remote_Requirements](about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="567b1-121">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

<span data-ttu-id="567b1-122">在 Windows Vista 和更高版本的 Windows 中，若要在本地计算机上创建 PSSession，你必须使用 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="567b1-122">In Windows Vista and later versions of Windows, to create a PSSession on a local computer, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

## <a name="what-is-a-session"></a><span data-ttu-id="567b1-123">什么是会话？</span><span class="sxs-lookup"><span data-stu-id="567b1-123">What Is a Session?</span></span>

<span data-ttu-id="567b1-124">会话是 Windows PowerShell 在其中运行的环境。</span><span class="sxs-lookup"><span data-stu-id="567b1-124">A session is an environment in which Windows PowerShell runs.</span></span>

<span data-ttu-id="567b1-125">每次启动 Windows PowerShell 时，将为你创建一个会话，你可以在该会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-125">Each time you start Windows PowerShell, a session is created for you, and you can run commands in the session.</span></span> <span data-ttu-id="567b1-126">您还可以将项添加到您的会话中，如模块和管理单元，并且可以创建变量、函数和别名等项。</span><span class="sxs-lookup"><span data-stu-id="567b1-126">You can also add items to your session, such as modules and snap-ins, and you can create items, such as variables, functions, and aliases.</span></span> <span data-ttu-id="567b1-127">这些项仅存在于会话中，并在会话结束时被删除。</span><span class="sxs-lookup"><span data-stu-id="567b1-127">These items exist only in the session and are deleted when the session ends.</span></span>

<span data-ttu-id="567b1-128">你还可以在本地计算机或远程计算机上创建用户管理的会话，称为 "Windows PowerShell 会话" 或 "Pssession"。</span><span class="sxs-lookup"><span data-stu-id="567b1-128">You can also create user-managed sessions, known as " Windows PowerShell sessions" or "PSSessions," on the local computer or on a remote computer.</span></span> <span data-ttu-id="567b1-129">与默认会话一样，你可以在 PSSession 中运行命令并添加和创建项。</span><span class="sxs-lookup"><span data-stu-id="567b1-129">Like the default session, you can run commands in a PSSession and add and create items.</span></span> <span data-ttu-id="567b1-130">但是，与自动启动的会话不同，你可以控制创建的 Pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-130">However, unlike the session that starts automatically, you can control the PSSessions that you create.</span></span> <span data-ttu-id="567b1-131">您可以获取、创建、配置和删除它们、断开连接并重新连接到它们，还可以在同一 PSSession 中运行多个命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-131">You can get, create, configure, and remove them, disconnect and reconnect to them, and run multiple commands in the same PSSession.</span></span> <span data-ttu-id="567b1-132">在删除 PSSession 之前，该 PSSession 将保持可用状态。</span><span class="sxs-lookup"><span data-stu-id="567b1-132">The PSSession remains available until you delete it or it times out.</span></span>

<span data-ttu-id="567b1-133">通常，你可以创建 PSSession 以在远程计算机上运行一系列相关命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-133">Typically, you create a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="567b1-134">在远程计算机上创建 PSSession 时，Windows PowerShell 会建立与远程计算机的持久连接，以支持会话。</span><span class="sxs-lookup"><span data-stu-id="567b1-134">When you create a PSSession on a remote computer, Windows PowerShell establishes a persistent connection to the remote computer to support the session.</span></span>

<span data-ttu-id="567b1-135">如果使用或 cmdlet 的 **ComputerName** 参数 `Invoke-Command` `Enter-PSSession` 运行远程命令或启动交互式会话，Windows PowerShell 将在远程计算机上创建一个临时会话，并在该命令完成或交互式会话结束后立即关闭会话。</span><span class="sxs-lookup"><span data-stu-id="567b1-135">If you use the **ComputerName** parameter of the `Invoke-Command` or `Enter-PSSession` cmdlet to run a remote command or to start an interactive session, Windows PowerShell creates a temporary session on the remote computer and closes the session as soon as the command is complete or as soon as the interactive session ends.</span></span> <span data-ttu-id="567b1-136">你无法控制这些临时会话，并且你无法将其用于多个命令或单个交互式会话。</span><span class="sxs-lookup"><span data-stu-id="567b1-136">You cannot control these temporary sessions, and you cannot use them for more than a single command or a single interactive session.</span></span>

<span data-ttu-id="567b1-137">在 Windows PowerShell 中，"当前会话" 是您正在使用的会话。</span><span class="sxs-lookup"><span data-stu-id="567b1-137">In Windows PowerShell, the "current session" is the session that you are working in.</span></span> <span data-ttu-id="567b1-138">"当前会话" 可以引用任何会话，包括临时会话或 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-138">The "current session" can refer to any session, including a temporary session or a PSSession.</span></span>

## <a name="why-use-a-pssession"></a><span data-ttu-id="567b1-139">为什么使用 PSSession？</span><span class="sxs-lookup"><span data-stu-id="567b1-139">Why Use a PSSession?</span></span>

<span data-ttu-id="567b1-140">需要与远程计算机建立持久连接时，请使用 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-140">Use a PSSession when you need a persistent connection to a remote computer.</span></span>
<span data-ttu-id="567b1-141">使用 PSSession，你可以运行共享数据的一系列命令，如变量的值、函数的内容或别名的定义。</span><span class="sxs-lookup"><span data-stu-id="567b1-141">With a PSSession, you can run a series of commands that share data, such as the value of variables, the contents of a function, or the definition of an alias.</span></span>

<span data-ttu-id="567b1-142">无需创建 PSSession 即可运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-142">You can run remote commands without creating a PSSession.</span></span> <span data-ttu-id="567b1-143">使用启用远程的 cmdlet 的 **ComputerName** 参数在一台或多台计算机上运行单个命令或一系列不相关的命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-143">Use the **ComputerName** parameter of remote-enabled cmdlets to run a single command or a series of unrelated commands on one or many computers.</span></span>

<span data-ttu-id="567b1-144">当你使用或的 **ComputerName** 参数 `Invoke-Command` 时 `Enter-PSSession` ，Windows PowerShell 将建立与远程计算机的临时连接，然后在该命令完成后立即关闭连接。</span><span class="sxs-lookup"><span data-stu-id="567b1-144">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, Windows PowerShell establishes a temporary connection to the remote computer and then closes the connection as soon as the command is complete.</span></span> <span data-ttu-id="567b1-145">连接关闭时，所创建的任何数据元素都将丢失。</span><span class="sxs-lookup"><span data-stu-id="567b1-145">Any data elements that you create are lost when the connection is closed.</span></span>

<span data-ttu-id="567b1-146">具有 **ComputerName** 参数的其他 cmdlet （例如 `Get-Eventlog` 和 `Get-WmiObject` ）使用不同的远程处理技术来收集数据。</span><span class="sxs-lookup"><span data-stu-id="567b1-146">Other cmdlets that have a **ComputerName** parameter, such as `Get-Eventlog` and `Get-WmiObject`, use different remoting technologies to gather data.</span></span> <span data-ttu-id="567b1-147">无创建一个持久连接，如 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-147">None create a persistent connection like a PSSession.</span></span>

## <a name="how-to-create-a-pssession"></a><span data-ttu-id="567b1-148">如何创建 PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-148">How to Create a PSSession</span></span>

<span data-ttu-id="567b1-149">若要创建 PSSession，请使用 `New-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="567b1-149">To create a PSSession, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="567b1-150">若要在远程计算机上创建 PSSession，请使用该 cmdlet 的 **ComputerName** 参数 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="567b1-150">To create the PSSession on a remote computer, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="567b1-151">例如，以下命令在 Server01 计算机上创建一个新的 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-151">For example, the following command creates a new PSSession on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

<span data-ttu-id="567b1-152">提交该命令时，将 `New-PSSession` 创建 PSSession 并返回表示 PSSession 的对象。</span><span class="sxs-lookup"><span data-stu-id="567b1-152">When you submit the command, `New-PSSession` creates the PSSession and returns an object that represents the PSSession.</span></span> <span data-ttu-id="567b1-153">您可以在创建 PSSession 时将对象保存在变量中，也可以使用 `Get-PSSession` 命令在以后获取 pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-153">You can save the object in a variable when you create the PSSession, or you can use a `Get-PSSession` command to get the PSSession at a later time.</span></span>

<span data-ttu-id="567b1-154">例如，以下命令在 Server01 计算机上创建一个新的 PSSession，并将生成的对象保存在 $ps 的变量中。</span><span class="sxs-lookup"><span data-stu-id="567b1-154">For example, the following command creates a new PSSession on the Server01 computer and saves the resulting object in the $ps variable.</span></span>

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a><span data-ttu-id="567b1-155">如何在多台计算机上创建 Pssession</span><span class="sxs-lookup"><span data-stu-id="567b1-155">How to Create PSSessions on Multiple Computers</span></span>

<span data-ttu-id="567b1-156">若要在多台计算机上创建 Pssession，请使用该 cmdlet 的 **ComputerName** 参数 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="567b1-156">To create PSSessions on multiple computers, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="567b1-157">在以逗号分隔的列表中键入远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="567b1-157">Type the names of the remote computers in a comma-separated list.</span></span>

<span data-ttu-id="567b1-158">例如，若要在 Server01、Server02 和 Server03 计算机上创建 Pssession，请键入：</span><span class="sxs-lookup"><span data-stu-id="567b1-158">For example, to create PSSessions on the Server01, Server02, and Server03 computers, type:</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="567b1-159">`New-PSSession` 在每台远程计算机上创建一个 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-159">`New-PSSession` creates one PSSession on each of the remote computers.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="567b1-160">如何获取 Pssession</span><span class="sxs-lookup"><span data-stu-id="567b1-160">How to Get PSSessions</span></span>

<span data-ttu-id="567b1-161">若要获取在当前会话中创建的 Pssession，请使用 `Get-PSSession` 不带 **ComputerName** 参数的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="567b1-161">To get the PSSessions that were created in your current session, use the `Get-PSSession` cmdlet without the **ComputerName** parameter.</span></span> <span data-ttu-id="567b1-162">`Get-PSSession` 返回返回的相同类型的对象 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="567b1-162">`Get-PSSession` returns the same type of object that `New-PSSession` returns.</span></span>

<span data-ttu-id="567b1-163">以下命令将获取在当前会话中创建的所有 Pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-163">The following command gets all the PSSessions that were created in the current session.</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="567b1-164">Pssession 的默认显示显示其 ID 和默认显示名称。</span><span class="sxs-lookup"><span data-stu-id="567b1-164">The default display of the PSSessions shows their ID and a default display name.</span></span> <span data-ttu-id="567b1-165">您可以在创建会话时分配备用显示名称。</span><span class="sxs-lookup"><span data-stu-id="567b1-165">You can assign an alternate display name when you create the session.</span></span>

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

<span data-ttu-id="567b1-166">你还可以在变量中保存 Pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-166">You can also save the PSSessions in a variable.</span></span> <span data-ttu-id="567b1-167">以下命令将获取 Pssession 并将其保存在 \$ ps123 变量中。</span><span class="sxs-lookup"><span data-stu-id="567b1-167">The following command gets the PSSessions and saves them in the \$ps123 variable.</span></span>

```powershell
$ps123 = Get-PSSession
```

<span data-ttu-id="567b1-168">使用 PSSession cmdlet 时，可以按其 ID、其名称或 (GUID) 的实例 ID 来引用 PSSession。</span><span class="sxs-lookup"><span data-stu-id="567b1-168">When using the PSSession cmdlets, you can refer to a PSSession by its ID, by its name, or by its instance ID (a GUID).</span></span> <span data-ttu-id="567b1-169">下面的命令通过其 ID 获取 PSSession，并将其保存在 \$ ps01 变量中。</span><span class="sxs-lookup"><span data-stu-id="567b1-169">The following command gets a PSSession by its ID and saves it in the \$ps01 variable.</span></span>

```powershell
$ps01 = Get-PSSession -Id 1
```

<span data-ttu-id="567b1-170">从 Windows PowerShell 3.0 开始，Pssession 在远程计算机上维护。</span><span class="sxs-lookup"><span data-stu-id="567b1-170">Beginning in Windows PowerShell 3.0, PSSessions are maintained on the remote computer.</span></span> <span data-ttu-id="567b1-171">若要获取在特定远程计算机上创建的 Pssession，请使用该 cmdlet 的 **ComputerName** 参数 `Get-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="567b1-171">To get PSSessions that you created on particular remote computers, use the **ComputerName** parameter of the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="567b1-172">以下命令将获取在 Server01 远程计算机上创建的 Pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-172">The following command gets the PSSessions that you created on the Server01 remote computer.</span></span> <span data-ttu-id="567b1-173">这包括在当前会话和本地计算机或其他计算机上的其他会话中创建的 Pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-173">This includes PSSessions created in the current session and in other sessions on the local computer or other computers.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

<span data-ttu-id="567b1-174">在 Windows PowerShell 2.0 中， `Get-PSSession` 仅获取在当前会话中创建的 pssession。</span><span class="sxs-lookup"><span data-stu-id="567b1-174">In Windows PowerShell 2.0, `Get-PSSession` gets only the PSSessions that were created in the current session.</span></span> <span data-ttu-id="567b1-175">它不会获取在其他会话或其他计算机上创建的 Pssession，即使会话连接到并且正在本地计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-175">It does not get PSSessions that were created in other sessions or on other computers, even if the sessions are connected to and are running commands on the local computer.</span></span>

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="567b1-176">如何在 PSSession 中运行命令</span><span class="sxs-lookup"><span data-stu-id="567b1-176">How to Run Commands in a PSSession</span></span>

<span data-ttu-id="567b1-177">若要在一个或多个 Pssession 中运行命令，请使用 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="567b1-177">To run a command in one or more PSSessions, use the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="567b1-178">使用 Session 参数指定 Pssession，并使用 **ScriptBlock** 参数来指定命令。</span><span class="sxs-lookup"><span data-stu-id="567b1-178">Use the Session parameter to specify the PSSessions and the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="567b1-179">例如，若要 `Get-ChildItem` 在 123 $ps 变量中保存的三个 pssession 中的每一个中运行 ( "dir" ) 命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="567b1-179">For example, to run a `Get-ChildItem` ("dir") command in each of the three PSSessions saved in the $ps123 variable, type:</span></span>

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a><span data-ttu-id="567b1-180">如何删除 Pssession</span><span class="sxs-lookup"><span data-stu-id="567b1-180">How to Delete PSSessions</span></span>

<span data-ttu-id="567b1-181">使用完 PSSession 后，请使用 `Remove-PSSession` cmdlet 删除 pssession，并释放所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="567b1-181">When you are finished with the PSSession, use the `Remove-PSSession` cmdlet to delete the PSSession and to release the resources that it was using.</span></span>

```powershell
Remove-PSSession -Session $ps
```

<span data-ttu-id="567b1-182">或</span><span class="sxs-lookup"><span data-stu-id="567b1-182">or</span></span>

```powershell
Remove-PSSession -Id 1
```

<span data-ttu-id="567b1-183">若要从远程计算机中删除 PSSession，请使用该 cmdlet 的 **ComputerName** 参数 `Remove-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="567b1-183">To remove a PSSession from a remote computer, use the **ComputerName** parameter of the `Remove-PSSession` cmdlet.</span></span>

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

<span data-ttu-id="567b1-184">如果不删除 PSSession，则 PSSession 在超时之前仍可供使用。</span><span class="sxs-lookup"><span data-stu-id="567b1-184">If you do not delete the PSSession, the PSSession remains available for use until it times out.</span></span>

<span data-ttu-id="567b1-185">你还可以使用 cmdlet 的 **IdleTimeout** 参数 `New-PSSessionOption` 设置空闲 PSSession 的过期时间。</span><span class="sxs-lookup"><span data-stu-id="567b1-185">You can also use the **IdleTimeout** parameter of the `New-PSSessionOption` cmdlet to set an expiration time for an idle PSSession.</span></span> <span data-ttu-id="567b1-186">有关详细信息，请参阅 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。</span><span class="sxs-lookup"><span data-stu-id="567b1-186">For more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="the-pssession-cmdlets"></a><span data-ttu-id="567b1-187">PSSession Cmdlet</span><span class="sxs-lookup"><span data-stu-id="567b1-187">The PSSession Cmdlets</span></span>

<span data-ttu-id="567b1-188">若要获取 PSSession cmdlet 列表，请键入：</span><span class="sxs-lookup"><span data-stu-id="567b1-188">For a list of PSSession cmdlets, type:</span></span>

```powershell
Get-Help *-PSSession
```

- <span data-ttu-id="567b1-189">Connect-PSSession：将 PSSession 连接到当前会话</span><span class="sxs-lookup"><span data-stu-id="567b1-189">Connect-PSSession: Connects a PSSession to the current session</span></span>
- <span data-ttu-id="567b1-190">Disconnect-PSSession：断开与当前会话的 PSSession 的连接</span><span class="sxs-lookup"><span data-stu-id="567b1-190">Disconnect-PSSession: Disconnects a PSSession from the current session</span></span>
- <span data-ttu-id="567b1-191">Enter-PSSession：启动交互式会话</span><span class="sxs-lookup"><span data-stu-id="567b1-191">Enter-PSSession: Starts an interactive session</span></span>
- <span data-ttu-id="567b1-192">Exit-PSSession：结束交互式会话</span><span class="sxs-lookup"><span data-stu-id="567b1-192">Exit-PSSession: Ends an interactive session</span></span>
- <span data-ttu-id="567b1-193">Get-help：获取当前会话中的 Pssession</span><span class="sxs-lookup"><span data-stu-id="567b1-193">Get-PSSession: Gets the PSSessions in the current session</span></span>
- <span data-ttu-id="567b1-194">New-PSSession：在本地或远程计算机上创建新的 PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-194">New-PSSession: Creates a new PSSession on a local or remote computer</span></span>
- <span data-ttu-id="567b1-195">Receive-PSSession：获取在断开连接的会话中运行的命令的结果</span><span class="sxs-lookup"><span data-stu-id="567b1-195">Receive-PSSession: Gets the results of commands that ran in a disconnected session</span></span>
- <span data-ttu-id="567b1-196">Remove-PSSession：删除当前会话中的 Pssession</span><span class="sxs-lookup"><span data-stu-id="567b1-196">Remove-PSSession: Deletes the PSSessions in the current session</span></span>

## <a name="for-more-information"></a><span data-ttu-id="567b1-197">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="567b1-197">For More Information</span></span>

<span data-ttu-id="567b1-198">有关 Pssession 的详细信息，请参阅 [about_PSSession_Details](about_PSSession_Details.md)。</span><span class="sxs-lookup"><span data-stu-id="567b1-198">For more information about PSSessions, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="567b1-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="567b1-199">See Also</span></span>

[<span data-ttu-id="567b1-200">about_Remote</span><span class="sxs-lookup"><span data-stu-id="567b1-200">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="567b1-201">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="567b1-201">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="567b1-202">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="567b1-202">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="567b1-203">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-203">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="567b1-204">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-204">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="567b1-205">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-205">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="567b1-206">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-206">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[<span data-ttu-id="567b1-207">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-207">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="567b1-208">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="567b1-208">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="567b1-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-209">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="567b1-210">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="567b1-210">Remove-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSession)
