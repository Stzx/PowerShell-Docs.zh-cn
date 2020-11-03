---
description: 描述如何解释和格式化远程命令的输出。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 4d298b945a9b6d45b26a76b3788d2a49b7d2a107
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200370"
---
# <a name="about-remote-output"></a><span data-ttu-id="e782b-104">关于远程输出</span><span class="sxs-lookup"><span data-stu-id="e782b-104">About Remote Output</span></span>

## <a name="short-description"></a><span data-ttu-id="e782b-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="e782b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e782b-106">描述如何解释和格式化远程命令的输出。</span><span class="sxs-lookup"><span data-stu-id="e782b-106">Describes how to interpret and format the output of remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="e782b-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="e782b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e782b-108">在远程计算机上运行的命令的输出可能类似于在本地计算机上运行的同一个命令的输出，但存在一些重要的差异。</span><span class="sxs-lookup"><span data-stu-id="e782b-108">The output of a command that was run on a remote computer might look like output of the same command run on a local computer, but there are some significant differences.</span></span>

<span data-ttu-id="e782b-109">本主题说明如何解释、格式化和显示在远程计算机上运行的命令的输出。</span><span class="sxs-lookup"><span data-stu-id="e782b-109">This topic explains how to interpret, format, and display the output of commands that are run on remote computers.</span></span>

## <a name="displaying-the-computer-name"></a><span data-ttu-id="e782b-110">显示计算机名称</span><span class="sxs-lookup"><span data-stu-id="e782b-110">DISPLAYING THE COMPUTER NAME</span></span>

<span data-ttu-id="e782b-111">使用 Invoke-Command cmdlet 在远程计算机上运行命令时，该命令将返回一个对象，该对象包含生成数据的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e782b-111">When you use the Invoke-Command cmdlet to run a command on a remote computer, the command returns an object that includes the name of the computer that generated the data.</span></span> <span data-ttu-id="e782b-112">远程计算机名称存储在 PSComputerName 属性中。</span><span class="sxs-lookup"><span data-stu-id="e782b-112">The remote computer name is stored in the PSComputerName property.</span></span>

<span data-ttu-id="e782b-113">对于许多命令，默认情况下会显示 PSComputerName。</span><span class="sxs-lookup"><span data-stu-id="e782b-113">For many commands, the PSComputerName is displayed by default.</span></span> <span data-ttu-id="e782b-114">例如，以下命令在两台远程计算机 Server01 和 Server02 上运行 Get-Culture 命令。</span><span class="sxs-lookup"><span data-stu-id="e782b-114">For example, the following command runs a Get-Culture command on two remote computers, Server01 and Server02.</span></span> <span data-ttu-id="e782b-115">输出如下所示，其中包含运行命令的远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e782b-115">The output, which appears below, includes the names of the remote computers on which the command ran.</span></span>

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

<span data-ttu-id="e782b-116">您可以使用 Invoke-Command 的 HideComputerName 参数来隐藏 PSComputerName 属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-116">You can use the HideComputerName parameter of Invoke-Command to hide the PSComputerName property.</span></span> <span data-ttu-id="e782b-117">此参数专为从一台远程计算机收集数据的命令而设计。</span><span class="sxs-lookup"><span data-stu-id="e782b-117">This parameter is designed for commands that collect data from only one remote computer.</span></span>

<span data-ttu-id="e782b-118">以下命令在 Server01 远程计算机上运行 Get-Culture 命令。</span><span class="sxs-lookup"><span data-stu-id="e782b-118">The following command runs a Get-Culture command on the Server01 remote computer.</span></span> <span data-ttu-id="e782b-119">它使用 HideComputerName 参数来隐藏 PSComputerName 属性和相关属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-119">It uses the HideComputerName parameter to hide the PSComputerName property and related properties.</span></span>

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="e782b-120">如果默认情况下不显示 PSComputerName 属性，还可以显示该属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-120">You can also display the PSComputerName property if it is not displayed by default.</span></span>

<span data-ttu-id="e782b-121">例如，以下命令使用 Format-Table cmdlet 将 PSComputerName 属性添加到远程 Get-Date 命令的输出中。</span><span class="sxs-lookup"><span data-stu-id="e782b-121">For example, the following commands use the Format-Table cmdlet to add the PSComputerName property to the output of a remote Get-Date command.</span></span>

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a><span data-ttu-id="e782b-122">显示 MACHINENAME 属性</span><span class="sxs-lookup"><span data-stu-id="e782b-122">DISPLAYING THE MACHINENAME PROPERTY</span></span>

<span data-ttu-id="e782b-123">多个 cmdlet （包括获取进程、获取服务和获取事件日志）都具有一个用于获取远程计算机上的对象的 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="e782b-123">Several cmdlets, including Get-Process, Get-Service, and Get-EventLog, have a ComputerName parameter that gets the objects on a remote computer.</span></span>
<span data-ttu-id="e782b-124">这些 cmdlet 不使用 PowerShell 远程处理，因此即使在未配置为在 Windows PowerShell 中进行远程处理的计算机上，也可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="e782b-124">These cmdlets do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="e782b-125">这些 cmdlet 返回的对象在 MachineName 属性中存储远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e782b-125">The objects that these cmdlets return store the name of the remote computer in the MachineName property.</span></span> <span data-ttu-id="e782b-126"> (这些对象没有 PSComputerName 属性。 ) </span><span class="sxs-lookup"><span data-stu-id="e782b-126">(These objects do not have a PSComputerName property.)</span></span>

<span data-ttu-id="e782b-127">例如，此命令将获取 Server01 和 Server02 远程计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="e782b-127">For example, this command gets the PowerShell process on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="e782b-128">默认显示不包括 MachineName 属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-128">The default display does not include the MachineName property.</span></span>

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

<span data-ttu-id="e782b-129">可以使用 Format-Table cmdlet 显示进程对象的 MachineName 属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-129">You can use the Format-Table cmdlet to display the MachineName property of the process objects.</span></span>

<span data-ttu-id="e782b-130">例如，以下命令将进程保存在 $p 变量中，然后使用管道运算符 (|) 将 $p 中的进程发送到 Format-Table 命令。</span><span class="sxs-lookup"><span data-stu-id="e782b-130">For example, the following command saves the processes in the $p variable and then uses a pipeline operator (|) to send the processes in $p to the Format-Table command.</span></span> <span data-ttu-id="e782b-131">该命令使用 Format-Table 的属性参数在显示中包括 MachineName 属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-131">The command uses the Property parameter of Format-Table to include the MachineName property in the display.</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

<span data-ttu-id="e782b-132">下面更复杂的命令将 MachineName 属性添加到默认进程显示。</span><span class="sxs-lookup"><span data-stu-id="e782b-132">The following more complex command adds the MachineName property to the default process display.</span></span> <span data-ttu-id="e782b-133">它使用哈希表来指定计算属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-133">It uses hash tables to specify calculated properties.</span></span> <span data-ttu-id="e782b-134">幸运的是，您不必理解它来使用它。</span><span class="sxs-lookup"><span data-stu-id="e782b-134">Fortunately, you do not have to understand it to use it.</span></span>

<span data-ttu-id="e782b-135"> (请注意，反撇号 ['] 是继续符。 ) </span><span class="sxs-lookup"><span data-stu-id="e782b-135">(Note that the backtick [\`] is the continuation character.)</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a><span data-ttu-id="e782b-136">反序列化对象</span><span class="sxs-lookup"><span data-stu-id="e782b-136">DESERIALIZED OBJECTS</span></span>

<span data-ttu-id="e782b-137">当运行生成输出的远程命令时，命令输出会通过网络传输回本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e782b-137">When you run remote commands that generate output, the command output is transmitted across the network back to the local computer.</span></span>

<span data-ttu-id="e782b-138">由于大多数实时 Microsoft .NET 框架对象 (例如 PowerShell cmdlet 返回) 的对象无法通过网络进行传输，因此活动对象将 "序列化"。</span><span class="sxs-lookup"><span data-stu-id="e782b-138">Because most live Microsoft .NET Framework objects (such as the objects that PowerShell cmdlets return) cannot be transmitted over the network, the live objects are "serialized".</span></span> <span data-ttu-id="e782b-139">换句话说，活动对象将转换为对象及其属性的 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="e782b-139">In other words, the live objects are converted into XML representations of the object and its properties.</span></span> <span data-ttu-id="e782b-140">然后，基于 XML 的序列化对象通过网络传输。</span><span class="sxs-lookup"><span data-stu-id="e782b-140">Then, the XML-based serialized object is transmitted across the network.</span></span>

<span data-ttu-id="e782b-141">在本地计算机上，PowerShell 接收基于 XML 的序列化对象，并通过将基于 XML 的对象转换为标准 .NET Framework 对象来进行 "反序列化"。</span><span class="sxs-lookup"><span data-stu-id="e782b-141">On the local computer, PowerShell receives the XML-based serialized object and "deserializes" it by converting the XML-based object into a standard .NET Framework object.</span></span>

<span data-ttu-id="e782b-142">但是，反序列化的对象不是活动对象。</span><span class="sxs-lookup"><span data-stu-id="e782b-142">However, the deserialized object is not a live object.</span></span> <span data-ttu-id="e782b-143">它是对象在序列化时的快照，它包含属性，但没有方法。</span><span class="sxs-lookup"><span data-stu-id="e782b-143">It is a snapshot of the object at the time that it was serialized, and it includes properties but no methods.</span></span> <span data-ttu-id="e782b-144">可以在 PowerShell 中使用和管理这些对象，这些对象包括在管道中传递它们、显示所选属性以及设置它们的格式。</span><span class="sxs-lookup"><span data-stu-id="e782b-144">You can use and manage these objects in PowerShell, including passing them in pipelines, displaying selected properties, and formatting them.</span></span>

<span data-ttu-id="e782b-145">大多数反序列化对象会自动设置格式，以供 Types.ps1xml 或 Format.ps1xml 文件中的项显示。</span><span class="sxs-lookup"><span data-stu-id="e782b-145">Most deserialized objects are automatically formatted for display by entries in the Types.ps1xml or Format.ps1xml files.</span></span> <span data-ttu-id="e782b-146">但是，本地计算机可能没有对远程计算机上生成的所有反序列化对象的格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="e782b-146">However, the local computer might not have formatting files for all of the deserialized objects that were generated on a remote computer.</span></span> <span data-ttu-id="e782b-147">如果未设置对象的格式，则每个对象的所有属性都将显示在控制台中的流列表中。</span><span class="sxs-lookup"><span data-stu-id="e782b-147">When objects are not formatted, all of the properties of each object appear in the console in a streaming list.</span></span>

<span data-ttu-id="e782b-148">如果未自动设置对象的格式，则可以使用格式设置 cmdlet （如 Format-Table 或格式列表）来设置所选属性的格式并显示这些属性。</span><span class="sxs-lookup"><span data-stu-id="e782b-148">When objects are not formatted automatically, you can use the formatting cmdlets, such as Format-Table or Format-List, to format and display selected properties.</span></span> <span data-ttu-id="e782b-149">或者，可以使用 Out-GridView cmdlet 显示表中的对象。</span><span class="sxs-lookup"><span data-stu-id="e782b-149">Or, you can use the Out-GridView cmdlet to display the objects in a table.</span></span>

<span data-ttu-id="e782b-150">此外，如果你在远程计算机上运行的命令所使用的 cmdlet 不在本地计算机上，则该命令返回的对象的格式可能不正确，因为你的计算机上没有这些对象的格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="e782b-150">Also, if you run a command on a remote computer that uses cmdlets that you do not have on your local computer, the objects that the command returns might not be formatted properly because you do not have the formatting files for those objects on your computer.</span></span> <span data-ttu-id="e782b-151">若要从另一台计算机获取格式设置数据，请使用 Get-FormatData 和 Export-FormatData cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e782b-151">To get formatting data from another computer, use the Get-FormatData and Export-FormatData cmdlets.</span></span>

<span data-ttu-id="e782b-152">某些对象类型（如 DirectoryInfo 对象和 Guid）在收到时转换回活动对象。</span><span class="sxs-lookup"><span data-stu-id="e782b-152">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="e782b-153">这些对象不需要任何特殊的处理或格式。</span><span class="sxs-lookup"><span data-stu-id="e782b-153">These objects do not need any special handling or formatting.</span></span>

## <a name="ordering-the-results"></a><span data-ttu-id="e782b-154">对结果进行排序</span><span class="sxs-lookup"><span data-stu-id="e782b-154">ORDERING THE RESULTS</span></span>

<span data-ttu-id="e782b-155">Cmdlet 的 ComputerName 参数中计算机名称的顺序决定了 PowerShell 连接到远程计算机的顺序。</span><span class="sxs-lookup"><span data-stu-id="e782b-155">The order of the computer names in the ComputerName parameter of cmdlets determines the order in which PowerShell connects to the remote computers.</span></span> <span data-ttu-id="e782b-156">但是，结果以本地计算机接收它们的顺序显示，这可能是不同的顺序。</span><span class="sxs-lookup"><span data-stu-id="e782b-156">However, the results appear in the order in which the local computer receives them, which might be a different order.</span></span>

<span data-ttu-id="e782b-157">若要更改结果的顺序，请使用 Sort-Object cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e782b-157">To change the order of the results, use the Sort-Object cmdlet.</span></span> <span data-ttu-id="e782b-158">可以按 PSComputerName 或 MachineName 属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="e782b-158">You can sort on the PSComputerName or MachineName property.</span></span> <span data-ttu-id="e782b-159">您还可以对对象的另一个属性进行排序，以使不同计算机的结果交错。</span><span class="sxs-lookup"><span data-stu-id="e782b-159">You can also sort on another property of the object so that the results from different computers are interspersed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e782b-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e782b-160">SEE ALSO</span></span>

[<span data-ttu-id="e782b-161">about_Remote</span><span class="sxs-lookup"><span data-stu-id="e782b-161">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="e782b-162">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="e782b-162">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="e782b-163">Format-Table</span><span class="sxs-lookup"><span data-stu-id="e782b-163">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="e782b-164">Get-Process</span><span class="sxs-lookup"><span data-stu-id="e782b-164">Get-Process</span></span>](xref:Microsoft.PowerShell.Management.Get-Process)

[<span data-ttu-id="e782b-165">Get-Service</span><span class="sxs-lookup"><span data-stu-id="e782b-165">Get-Service</span></span>](xref:Microsoft.PowerShell.Management.Get-Service)

[<span data-ttu-id="e782b-166">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e782b-166">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="e782b-167">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e782b-167">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)
