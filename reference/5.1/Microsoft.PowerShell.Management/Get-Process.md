---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: 6b22e8d4f843d0611083c253027222f4d4cd7282
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198282"
---
# <span data-ttu-id="b77ce-103">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-103">Get-Process</span></span>

## <span data-ttu-id="b77ce-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b77ce-104">SYNOPSIS</span></span>
<span data-ttu-id="b77ce-105">获取在本地计算机或远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-105">Gets the processes that are running on the local computer or a remote computer.</span></span>

## <span data-ttu-id="b77ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b77ce-106">SYNTAX</span></span>

### <span data-ttu-id="b77ce-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="b77ce-107">Name (Default)</span></span>

```
Get-Process [[-Name] <String[]>] [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="b77ce-108">NameWithUserName</span><span class="sxs-lookup"><span data-stu-id="b77ce-108">NameWithUserName</span></span>

```
Get-Process [[-Name] <String[]>] [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="b77ce-109">IdWithUserName</span><span class="sxs-lookup"><span data-stu-id="b77ce-109">IdWithUserName</span></span>

```
Get-Process -Id <Int32[]> [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="b77ce-110">ID</span><span class="sxs-lookup"><span data-stu-id="b77ce-110">Id</span></span>

```
Get-Process -Id <Int32[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="b77ce-111">InputObjectWithUserName</span><span class="sxs-lookup"><span data-stu-id="b77ce-111">InputObjectWithUserName</span></span>

```
Get-Process -InputObject <Process[]> [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="b77ce-112">InputObject</span><span class="sxs-lookup"><span data-stu-id="b77ce-112">InputObject</span></span>

```
Get-Process -InputObject <Process[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

## <span data-ttu-id="b77ce-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b77ce-113">DESCRIPTION</span></span>

<span data-ttu-id="b77ce-114">`Get-Process`Cmdlet 将获取本地或远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-114">The `Get-Process` cmdlet gets the processes on a local or remote computer.</span></span>

<span data-ttu-id="b77ce-115">如果没有参数，此 cmdlet 将获取本地计算机上的所有进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-115">Without parameters, this cmdlet gets all of the processes on the local computer.</span></span>
<span data-ttu-id="b77ce-116">还可以通过进程名称或进程 ID (PID) 指定特定进程，或将进程对象通过管道传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b77ce-116">You can also specify a particular process by process name or process ID (PID) or pass a process object through the pipeline to this cmdlet.</span></span>

<span data-ttu-id="b77ce-117">默认情况下，此 cmdlet 将返回一个进程对象，该对象包含有关进程的详细信息，并支持使你能够启动和停止进程的方法。</span><span class="sxs-lookup"><span data-stu-id="b77ce-117">By default, this cmdlet returns a process object that has detailed information about the process and supports methods that let you start and stop the process.</span></span>
<span data-ttu-id="b77ce-118">你还可以使用 cmdlet 的参数 `Get-Process` 来获取进程中运行的程序的文件版本信息，并获取进程加载的模块。</span><span class="sxs-lookup"><span data-stu-id="b77ce-118">You can also use the parameters of the `Get-Process` cmdlet to get file version information for the program that runs in the process and to get the modules that the process loaded.</span></span>

## <span data-ttu-id="b77ce-119">示例</span><span class="sxs-lookup"><span data-stu-id="b77ce-119">EXAMPLES</span></span>

### <span data-ttu-id="b77ce-120">示例1：获取本地计算机上所有活动进程的列表</span><span class="sxs-lookup"><span data-stu-id="b77ce-120">Example 1: Get a list of all active processes on the local computer</span></span>

```powershell
Get-Process
```

<span data-ttu-id="b77ce-121">此命令将获取在本地计算机上运行的所有活动进程的列表。</span><span class="sxs-lookup"><span data-stu-id="b77ce-121">This command gets a list of all active processes running on the local computer.</span></span>
<span data-ttu-id="b77ce-122">有关每列的定义，请参阅 [注释](#notes) 部分。</span><span class="sxs-lookup"><span data-stu-id="b77ce-122">For a definition of each column, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="b77ce-123">示例2：获取有关一个或多个进程的所有可用数据</span><span class="sxs-lookup"><span data-stu-id="b77ce-123">Example 2: Get all available data about one or more processes</span></span>

```powershell
Get-Process winword, explorer | Format-List *
```

<span data-ttu-id="b77ce-124">此命令获取计算机上的有关 Winword 和 Explorer 进程的所有可用的数据。</span><span class="sxs-lookup"><span data-stu-id="b77ce-124">This command gets all available data about the Winword and Explorer processes on the computer.</span></span>
<span data-ttu-id="b77ce-125">它使用 **Name** 参数来指定进程，但它省略了可选的参数名称。</span><span class="sxs-lookup"><span data-stu-id="b77ce-125">It uses the **Name** parameter to specify the processes, but it omits the optional parameter name.</span></span>
<span data-ttu-id="b77ce-126">管道运算符将 `|` 数据传递给 `Format-List` cmdlet，后者显示 `*` Winword 和资源管理器进程对象的所有可用属性。</span><span class="sxs-lookup"><span data-stu-id="b77ce-126">The pipeline operator `|` passes the data to the `Format-List` cmdlet, which displays all available properties `*` of the Winword and Explorer process objects.</span></span>

<span data-ttu-id="b77ce-127">也可通过其进程 ID 来标识这些进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-127">You can also identify the processes by their process IDs.</span></span>
<span data-ttu-id="b77ce-128">例如：`Get-Process -Id 664, 2060`。</span><span class="sxs-lookup"><span data-stu-id="b77ce-128">For instance, `Get-Process -Id 664, 2060`.</span></span>

### <span data-ttu-id="b77ce-129">示例3：获取工作集大于指定大小的所有进程</span><span class="sxs-lookup"><span data-stu-id="b77ce-129">Example 3: Get all processes with a working set greater than a specified size</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

<span data-ttu-id="b77ce-130">此命令获取所有工作集大于 20 MB 的进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-130">This command gets all processes that have a working set greater than 20 MB.</span></span>
<span data-ttu-id="b77ce-131">它使用 `Get-Process`  cmdlet 来获取所有正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-131">It uses the `Get-Process`  cmdlet to get all running processes.</span></span>
<span data-ttu-id="b77ce-132">管道运算符将 `|` 进程对象传递给 `Where-Object` cmdlet，该 cmdlet 只选择其值大于20000000字节的工作集属性的对象。 **WorkingSet**</span><span class="sxs-lookup"><span data-stu-id="b77ce-132">The pipeline operator `|` passes the process objects to the `Where-Object` cmdlet, which selects only the object with a value greater than 20,000,000 bytes for the **WorkingSet** property.</span></span>

<span data-ttu-id="b77ce-133">集 **是进程** 对象的许多属性之一。</span><span class="sxs-lookup"><span data-stu-id="b77ce-133">**WorkingSet** is one of many properties of process objects.</span></span>
<span data-ttu-id="b77ce-134">若要查看所有属性，请键入 `Get-Process | Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-134">To see all of the properties, type `Get-Process | Get-Member`.</span></span>
<span data-ttu-id="b77ce-135">默认情况下，所有数量属性的值以字节为单位，尽管默认显示以千字节和兆字节为单位列出这些值。</span><span class="sxs-lookup"><span data-stu-id="b77ce-135">By default, the values of all amount properties are in bytes, even though the default display lists them in kilobytes and megabytes.</span></span>

### <span data-ttu-id="b77ce-136">示例4：根据优先级列出计算机上的进程</span><span class="sxs-lookup"><span data-stu-id="b77ce-136">Example 4: List processes on the computer in groups based on priority</span></span>

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

<span data-ttu-id="b77ce-137">这些命令基于其优先级类在计算机上列出进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-137">These commands list the processes on the computer in groups based on their priority class.</span></span>
<span data-ttu-id="b77ce-138">第一个命令获取计算机上的所有进程，然后将其存储在 `$A` 变量中。</span><span class="sxs-lookup"><span data-stu-id="b77ce-138">The first command gets all the processes on the computer and then stores them in the `$A` variable.</span></span>

<span data-ttu-id="b77ce-139">第二个命令将存储在变量中的 **进程** 对象通过管道传递 `$A` 给 `Get-Process` cmdlet，然后传递给 `Format-Table` cmdlet，后者使用 **优先级** 视图设置进程的格式。</span><span class="sxs-lookup"><span data-stu-id="b77ce-139">The second command pipes the **Process** object stored in the `$A` variable to the `Get-Process` cmdlet, then to the `Format-Table` cmdlet, which formats the processes by using the **Priority** view.</span></span>

<span data-ttu-id="b77ce-140">**优先级** 视图和其他视图在 PowerShell home directory () 中的 types.ps1xml 格式文件中定义 `$pshome` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-140">The **Priority** view, and other views, are defined in the PS1XML format files in the PowerShell home directory (`$pshome`).</span></span>

### <span data-ttu-id="b77ce-141">示例5：向标准 Get-Process 输出显示添加属性</span><span class="sxs-lookup"><span data-stu-id="b77ce-141">Example 5: Add a property to the standard Get-Process output display</span></span>

```powershell
Get-Process powershell -ComputerName S1, localhost | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 S1          powershell
     6 23500 31348   142 2.75   4016 S1          powershell
    27 54572 54520   576 5.52   4428 localhost   powershell
```

<span data-ttu-id="b77ce-142">此示例从本地计算机和远程计算机 (S1) 中检索进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-142">This example retrieves processes from the local computer and a remote computer (S1).</span></span>
<span data-ttu-id="b77ce-143">检索到的进程将通过管道传递给 `Format-Table` 将 **MachineName** 属性添加到标准 `Get-Process` 输出显示的命令。</span><span class="sxs-lookup"><span data-stu-id="b77ce-143">The retrieved processes are piped to the `Format-Table` command that adds the **MachineName** property to the standard `Get-Process` output display.</span></span>

### <span data-ttu-id="b77ce-144">示例6：获取进程的版本信息</span><span class="sxs-lookup"><span data-stu-id="b77ce-144">Example 6: Get version information for a process</span></span>

```
Get-Process powershell -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.6713.1       6.1.6713.1 (f... C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe
```

<span data-ttu-id="b77ce-145">此命令使用 **FileVersionInfo** 参数获取 powershell.exe 文件的版本信息，该文件是 PowerShell 进程的主模块。</span><span class="sxs-lookup"><span data-stu-id="b77ce-145">This command uses the **FileVersionInfo** parameter to get the version information for the powershell.exe file that is the main module for the PowerShell process.</span></span>

<span data-ttu-id="b77ce-146">若要在 Windows Vista 和更高版本的 Windows 上运行此命令，你必须以 "以管理员身份运行" 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b77ce-146">To run this command with processes that you do not own on Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="b77ce-147">示例7：获取用指定进程加载的模块</span><span class="sxs-lookup"><span data-stu-id="b77ce-147">Example 7: Get modules loaded with the specified process</span></span>

```powershell
Get-Process SQL* -Module
```

<span data-ttu-id="b77ce-148">此命令使用 **Module** 参数来获取已由进程加载的模块。</span><span class="sxs-lookup"><span data-stu-id="b77ce-148">This command uses the **Module** parameter to get the modules that have been loaded by the process.</span></span>
<span data-ttu-id="b77ce-149">此命令获取名称以 SQL 开头的进程的模块。</span><span class="sxs-lookup"><span data-stu-id="b77ce-149">This command gets the modules for the processes that have names that begin with SQL.</span></span>

<span data-ttu-id="b77ce-150">若要在 Windows Vista 和更高版本的 Windows 上对你不拥有的进程运行此命令，必须通过 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b77ce-150">To run this command on Windows Vista and later versions of Windows with processes that you do not own, you must start PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="b77ce-151">示例8：查找进程的所有者</span><span class="sxs-lookup"><span data-stu-id="b77ce-151">Example 8: Find the owner of a process</span></span>

```powershell
PS C:\> Get-Process powershell -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     powershell
```

```powershell
$p = Get-WmiObject Win32_Process -Filter "name='powershell.exe'"
$p.GetOwner()
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 3
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Domain           : DOMAIN01
ReturnValue      : 0
User             : user01
```

<span data-ttu-id="b77ce-152">第一个命令演示如何查找进程的所有者。</span><span class="sxs-lookup"><span data-stu-id="b77ce-152">The first command shows how to find the owner of a process.</span></span>
<span data-ttu-id="b77ce-153">**: Includeusername** 参数需要提升的用户权限 (以管理员身份运行) 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-153">The **IncludeUserName** parameter requires elevated user rights (Run as Administrator).</span></span>
<span data-ttu-id="b77ce-154">输出显示所有者为 Domain01\user01。</span><span class="sxs-lookup"><span data-stu-id="b77ce-154">The output reveals that the owner is Domain01\user01.</span></span>

<span data-ttu-id="b77ce-155">第二个和第三个命令是查找进程的所有者的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="b77ce-155">The second and third command are another way to find the owner of a process.</span></span>

<span data-ttu-id="b77ce-156">第二个命令使用 `Get-WmiObject` 来获取 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-156">The second command uses `Get-WmiObject` to get the PowerShell process.</span></span>
<span data-ttu-id="b77ce-157">此命令将其保存在 $p 变量中。</span><span class="sxs-lookup"><span data-stu-id="b77ce-157">It saves it in the $p variable.</span></span>

<span data-ttu-id="b77ce-158">第三个命令使用 GetOwner 方法来获取 $p 中的进程的所有者。</span><span class="sxs-lookup"><span data-stu-id="b77ce-158">The third command uses the GetOwner method to get the owner of the process in $p.</span></span>
<span data-ttu-id="b77ce-159">输出显示所有者为 Domain01\user01。</span><span class="sxs-lookup"><span data-stu-id="b77ce-159">The output reveals that the owner is Domain01\user01.</span></span>

### <span data-ttu-id="b77ce-160">示例9：使用自动变量标识托管当前会话的进程</span><span class="sxs-lookup"><span data-stu-id="b77ce-160">Example 9: Use an automatic variable to identify the process hosting the current session</span></span>

```powershell
Get-Process powershell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
308      26        52308      61780   567     3.18   5632 powershell
377      26        62676      63384   575     3.88   5888 powershell
```

```powershell
Get-Process -Id $PID
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
396      26        56488      57236   575     3.90   5888 powershell
```

<span data-ttu-id="b77ce-161">这些命令演示如何使用 `$PID` 自动变量来标识承载当前 PowerShell 会话的进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-161">These commands show how to use the `$PID` automatic variable to identify the process that is hosting the current PowerShell session.</span></span>
<span data-ttu-id="b77ce-162">可以使用此方法将宿主进程与可能要停止或关闭的其他 PowerShell 进程区分开来。</span><span class="sxs-lookup"><span data-stu-id="b77ce-162">You can use this method to distinguish the host process from other PowerShell processes that you might want to stop or close.</span></span>

<span data-ttu-id="b77ce-163">第一个命令获取当前会话中的所有 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-163">The first command gets all of the PowerShell processes in the current session.</span></span>

<span data-ttu-id="b77ce-164">第二个命令获取托管当前会话的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-164">The second command gets the PowerShell process that is hosting the current session.</span></span>

### <span data-ttu-id="b77ce-165">示例10：获取具有主窗口标题的所有进程，并在表中显示这些进程</span><span class="sxs-lookup"><span data-stu-id="b77ce-165">Example 10: Get all processes that have a main window title and display them in a table</span></span>

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

<span data-ttu-id="b77ce-166">此命令获取具有主窗口标题的所有进程，并在表中显示这些进程及其进程 ID 和进程名称。</span><span class="sxs-lookup"><span data-stu-id="b77ce-166">This command gets all the processes that have a main window title, and it displays them in a table with the process ID and the process name.</span></span>

<span data-ttu-id="b77ce-167">**MainWindowTitle** 属性只是返回的 **进程** 对象的许多有用属性之一 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-167">The **mainWindowTitle** property is just one of many useful properties of the **Process** object that `Get-Process` returns.</span></span>
<span data-ttu-id="b77ce-168">若要查看所有属性，请通过管道将命令结果传递 `Get-Process` 给 `Get-Member` cmdlet `Get-Process | Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-168">To view all of the properties, pipe the results of a `Get-Process` command to the `Get-Member` cmdlet `Get-Process | Get-Member`.</span></span>

## <span data-ttu-id="b77ce-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b77ce-169">PARAMETERS</span></span>

### <span data-ttu-id="b77ce-170">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b77ce-170">-ComputerName</span></span>

<span data-ttu-id="b77ce-171">指定此 cmdlet 为其获取活动进程的计算机。</span><span class="sxs-lookup"><span data-stu-id="b77ce-171">Specifies the computers for which this cmdlet gets active processes.</span></span>
<span data-ttu-id="b77ce-172">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="b77ce-172">The default is the local computer.</span></span>

<span data-ttu-id="b77ce-173">键入一台或多台计算机 (FQDN) 的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="b77ce-173">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one or more computers.</span></span>
<span data-ttu-id="b77ce-174">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="b77ce-174">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="b77ce-175">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="b77ce-175">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="b77ce-176">即使你的计算机未配置为运行远程命令，你也可以使用此 cmdlet 的 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="b77ce-176">You can use the **ComputerName** parameter of this cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, Id, InputObject
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77ce-177">-FileVersionInfo</span><span class="sxs-lookup"><span data-stu-id="b77ce-177">-FileVersionInfo</span></span>

<span data-ttu-id="b77ce-178">指示此 cmdlet 获取进程中运行的程序的文件版本信息。</span><span class="sxs-lookup"><span data-stu-id="b77ce-178">Indicates that this cmdlet gets the file version information for the program that runs in the process.</span></span>

<span data-ttu-id="b77ce-179">在 Windows Vista 和更高版本的 Windows 上，必须使用 "以管理员身份运行" 选项打开 PowerShell，才能对你不具有所有权的进程使用此参数。</span><span class="sxs-lookup"><span data-stu-id="b77ce-179">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="b77ce-180">不能在同一命令中使用 cmdlet 的 **FileVersionInfo** 和 **ComputerName** 参数 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-180">You cannot use the **FileVersionInfo** and **ComputerName** parameters of the `Get-Process` cmdlet in the same command.</span></span>

<span data-ttu-id="b77ce-181">若要获取远程计算机上某个进程的文件版本信息，请使用 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b77ce-181">To get file version information for a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="b77ce-182">使用此参数等效于获取每个进程对象的 **Mainmodule.fileversioninfo FileVersionInfo** 属性。</span><span class="sxs-lookup"><span data-stu-id="b77ce-182">Using this parameter is equivalent to getting the **MainModule.FileVersionInfo** property of each process object.</span></span>
<span data-ttu-id="b77ce-183">使用此参数时，将 `Get-Process` 返回 **FileVersionInfo** 对象 **FileVersionInfo** ，而不是进程对象。</span><span class="sxs-lookup"><span data-stu-id="b77ce-183">When you use this parameter, `Get-Process` returns a **FileVersionInfo** object **System.Diagnostics.FileVersionInfo** , not a process object.</span></span>
<span data-ttu-id="b77ce-184">因此，不能通过管道将命令输出传递到需要进程对象的 cmdlet，例如 `Stop-Process` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-184">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b77ce-185">-Id</span><span class="sxs-lookup"><span data-stu-id="b77ce-185">-Id</span></span>

<span data-ttu-id="b77ce-186">通过进程 ID (PID) 指定一个或多个进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-186">Specifies one or more processes by process ID (PID).</span></span>
<span data-ttu-id="b77ce-187">若要指定多个 ID，请使用逗号分隔 ID。</span><span class="sxs-lookup"><span data-stu-id="b77ce-187">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="b77ce-188">若要查找进程的 PID，请键入 `Get-Process`。</span><span class="sxs-lookup"><span data-stu-id="b77ce-188">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdWithUserName, Id
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b77ce-189">-: Includeusername</span><span class="sxs-lookup"><span data-stu-id="b77ce-189">-IncludeUserName</span></span>

<span data-ttu-id="b77ce-190">指示随命令的结果一起返回 **进程** 对象的用户名值。</span><span class="sxs-lookup"><span data-stu-id="b77ce-190">Indicates that the UserName value of the **Process** object is returned with results of the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b77ce-191">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b77ce-191">-InputObject</span></span>

<span data-ttu-id="b77ce-192">指定一个或多个进程对象。</span><span class="sxs-lookup"><span data-stu-id="b77ce-192">Specifies one or more process objects.</span></span>
<span data-ttu-id="b77ce-193">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="b77ce-193">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObjectWithUserName, InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b77ce-194">-Module</span><span class="sxs-lookup"><span data-stu-id="b77ce-194">-Module</span></span>

<span data-ttu-id="b77ce-195">指示此 cmdlet 获取由进程加载的模块。</span><span class="sxs-lookup"><span data-stu-id="b77ce-195">Indicates that this cmdlet gets the modules that have been loaded by the processes.</span></span>

<span data-ttu-id="b77ce-196">在 Windows Vista 和更高版本的 Windows 上，必须使用 "以管理员身份运行" 选项打开 PowerShell，才能对你不具有所有权的进程使用此参数。</span><span class="sxs-lookup"><span data-stu-id="b77ce-196">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="b77ce-197">若要获取远程计算机上由进程加载的模块，请使用 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b77ce-197">To get the modules that have been loaded by a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="b77ce-198">此参数等效于获取每个进程对象的 **模块** 属性。</span><span class="sxs-lookup"><span data-stu-id="b77ce-198">This parameter is equivalent to getting the **Modules** property of each process object.</span></span>
<span data-ttu-id="b77ce-199">使用此参数时，此 cmdlet 将返回 **system.diagnostics.processmodule** 对象 **system.diagnostics.processmodule** ，而不是进程对象。</span><span class="sxs-lookup"><span data-stu-id="b77ce-199">When you use this parameter, this cmdlet returns a **ProcessModule** object **System.Diagnostics.ProcessModule** , not a process object.</span></span>
<span data-ttu-id="b77ce-200">因此，不能通过管道将命令输出传递到需要进程对象的 cmdlet，例如 `Stop-Process` 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-200">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

<span data-ttu-id="b77ce-201">在同一命令中同时使用 *Module* 和 **FileVersionInfo** 参数时，此 Cmdlet 将返回一个 **FileVersionInfo** 对象，其中包含有关所有模块的文件版本的信息。</span><span class="sxs-lookup"><span data-stu-id="b77ce-201">When you use both the *Module* and **FileVersionInfo** parameters in the same command, this cmdlet returns a **FileVersionInfo** object with information about the file version of all modules.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b77ce-202">-Name</span><span class="sxs-lookup"><span data-stu-id="b77ce-202">-Name</span></span>

<span data-ttu-id="b77ce-203">通过进程名称指定一个或多个进程。</span><span class="sxs-lookup"><span data-stu-id="b77ce-203">Specifies one or more processes by process name.</span></span>
<span data-ttu-id="b77ce-204">可以键入多个进程名称（以逗号分隔），并可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b77ce-204">You can type multiple process names (separated by commas) and use wildcard characters.</span></span>
<span data-ttu-id="b77ce-205">参数名（“Name”）为可选项。</span><span class="sxs-lookup"><span data-stu-id="b77ce-205">The parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b77ce-206">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b77ce-206">CommonParameters</span></span>

<span data-ttu-id="b77ce-207">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b77ce-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b77ce-208">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b77ce-208">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b77ce-209">输入</span><span class="sxs-lookup"><span data-stu-id="b77ce-209">INPUTS</span></span>

### <span data-ttu-id="b77ce-210">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-210">System.Diagnostics.Process</span></span>

<span data-ttu-id="b77ce-211">可以将进程对象通过管道传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b77ce-211">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="b77ce-212">输出</span><span class="sxs-lookup"><span data-stu-id="b77ce-212">OUTPUTS</span></span>

### <span data-ttu-id="b77ce-213">"FileVersionInfo"、"System.diagnostics.processmodule" 和 "</span><span class="sxs-lookup"><span data-stu-id="b77ce-213">System.Diagnostics.Process, System.Diagnostics.FileVersionInfo, System.Diagnostics.ProcessModule</span></span>

<span data-ttu-id="b77ce-214">默认情况下，此 cmdlet 将返回一个 **system.object** 对象。</span><span class="sxs-lookup"><span data-stu-id="b77ce-214">By default, this cmdlet returns a **System.Diagnostics.Process** object.</span></span>
<span data-ttu-id="b77ce-215">如果使用 **FileVersionInfo** 参数，它将返回 **FileVersionInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="b77ce-215">If you use the **FileVersionInfo** parameter, it returns a **System.Diagnostics.FileVersionInfo** object.</span></span>
<span data-ttu-id="b77ce-216">如果使用 **Module** 参数（不带 **FileVersionInfo** 参数），则它将返回 **system.diagnostics.processmodule** 对象。</span><span class="sxs-lookup"><span data-stu-id="b77ce-216">If you use the **Module** parameter, without the **FileVersionInfo** parameter, it returns a **System.Diagnostics.ProcessModule** object.</span></span>

## <span data-ttu-id="b77ce-217">注释</span><span class="sxs-lookup"><span data-stu-id="b77ce-217">NOTES</span></span>

- <span data-ttu-id="b77ce-218">还可以通过其内置别名、ps 和 gps 来引用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b77ce-218">You can also refer to this cmdlet by its built-in aliases, ps and gps.</span></span> <span data-ttu-id="b77ce-219">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="b77ce-219">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="b77ce-220">在运行64位版本的 Windows 的计算机上，64位版本的 PowerShell 仅获取64位进程模块，而版本的 PowerShell 32 的版本仅适用于32位进程模块。</span><span class="sxs-lookup"><span data-stu-id="b77ce-220">On computers that are running a 64-bit version of Windows, the 64-bit version of PowerShell gets only 64-bit process modules and the 32-bit version of PowerShell gets only 32-bit process modules.</span></span>
- <span data-ttu-id="b77ce-221">可以在 PowerShell 中使用 Windows Management Instrumentation (WMI) Win32_Process 对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="b77ce-221">You can use the properties and methods of the Windows Management Instrumentation (WMI) Win32_Process object in PowerShell.</span></span> <span data-ttu-id="b77ce-222">有关信息，请参阅 `Get-WmiObject` 和 WMI SDK。</span><span class="sxs-lookup"><span data-stu-id="b77ce-222">For information, see `Get-WmiObject` and the WMI SDK.</span></span>
- <span data-ttu-id="b77ce-223">进程的默认显示为包括以下列的表。</span><span class="sxs-lookup"><span data-stu-id="b77ce-223">The default display of a process is a table that includes the following columns.</span></span> <span data-ttu-id="b77ce-224">有关进程对象的所有属性的说明，请参阅 MSDN library 中的 [进程属性](/dotnet/api/system.diagnostics.process) 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-224">For a description of all of the properties of process objects, see [Process Properties](/dotnet/api/system.diagnostics.process) in the MSDN library.</span></span>
  - <span data-ttu-id="b77ce-225">Handles：进程打开的句柄数。</span><span class="sxs-lookup"><span data-stu-id="b77ce-225">Handles: The number of handles that the process has opened.</span></span>
  - <span data-ttu-id="b77ce-226">NPM (K) ：进程正在使用的非分页内存量（kb）。</span><span class="sxs-lookup"><span data-stu-id="b77ce-226">NPM(K): The amount of non-paged memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="b77ce-227">PM (K) ：进程正在使用的可分页内存量（kb）。</span><span class="sxs-lookup"><span data-stu-id="b77ce-227">PM(K): The amount of pageable memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="b77ce-228">WS (K) ：进程工作集的大小（以 kb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="b77ce-228">WS(K): The size of the working set of the process, in kilobytes.</span></span>
    <span data-ttu-id="b77ce-229">工作集包括进程最近引用的内存的页面。</span><span class="sxs-lookup"><span data-stu-id="b77ce-229">The working set consists of the pages of memory that were recently referenced by the process.</span></span>
  - <span data-ttu-id="b77ce-230">VM (M) ：进程正在使用的虚拟内存量（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="b77ce-230">VM(M): The amount of virtual memory that the process is using, in megabytes.</span></span>
    <span data-ttu-id="b77ce-231">虚拟内存包括磁盘上分页文件中的存储。</span><span class="sxs-lookup"><span data-stu-id="b77ce-231">Virtual memory includes storage in the paging files on disk.</span></span>
  - <span data-ttu-id="b77ce-232">CPU () ：进程使用的处理器时间，以秒为单位。</span><span class="sxs-lookup"><span data-stu-id="b77ce-232">CPU(s): The amount of processor time that the process has used on all processors, in seconds.</span></span>
  - <span data-ttu-id="b77ce-233">ID：进程的进程 ID (PID) 。</span><span class="sxs-lookup"><span data-stu-id="b77ce-233">ID: The process ID (PID) of the process.</span></span>
  - <span data-ttu-id="b77ce-234">ProcessName：进程的名称。</span><span class="sxs-lookup"><span data-stu-id="b77ce-234">ProcessName: The name of the process.</span></span>
    <span data-ttu-id="b77ce-235">有关与进程相关的概念的解释，请参阅帮助和支持中心中的词汇表以及任务管理器帮助。</span><span class="sxs-lookup"><span data-stu-id="b77ce-235">For explanations of the concepts related to processes, see the Glossary in Help and Support Center and the Help for Task Manager.</span></span>
- <span data-ttu-id="b77ce-236">你还可以使用中提供的进程的内置替代视图 `Format-Table` ，例如 **StartTime** 和 **Priority** ，还可以设计你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="b77ce-236">You can also use the built-in alternate views of the processes available with `Format-Table`, such as **StartTime** and **Priority** , and you can design your own views.</span></span>

## <span data-ttu-id="b77ce-237">相关链接</span><span class="sxs-lookup"><span data-stu-id="b77ce-237">RELATED LINKS</span></span>

[<span data-ttu-id="b77ce-238">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-238">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="b77ce-239">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-239">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="b77ce-240">Start-Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-240">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="b77ce-241">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-241">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="b77ce-242">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="b77ce-242">Wait-Process</span></span>](Wait-Process.md)
