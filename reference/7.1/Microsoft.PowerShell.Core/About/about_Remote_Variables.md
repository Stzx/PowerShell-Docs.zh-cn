---
description: 说明如何在远程命令中使用本地和远程变量。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: f4477b76dd6ef16ca1c4dea6259c2591f1f0b40d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200418"
---
# <a name="about-remote-variables"></a><span data-ttu-id="53f50-104">关于远程变量</span><span class="sxs-lookup"><span data-stu-id="53f50-104">About Remote Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="53f50-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="53f50-105">Short description</span></span>

<span data-ttu-id="53f50-106">说明如何在远程命令中使用本地和远程变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-106">Explains how to use local and remote variables in remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="53f50-107">长说明</span><span class="sxs-lookup"><span data-stu-id="53f50-107">Long description</span></span>

<span data-ttu-id="53f50-108">你可以使用在远程计算机上运行的命令中的变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-108">You can use variables in commands that you run on remote computers.</span></span> <span data-ttu-id="53f50-109">为变量赋值，然后使用变量代替值。</span><span class="sxs-lookup"><span data-stu-id="53f50-109">Assign a value to the variable and then use the variable in place of the value.</span></span>

<span data-ttu-id="53f50-110">默认情况下，远程命令中的变量假定为在运行该命令的会话中定义。</span><span class="sxs-lookup"><span data-stu-id="53f50-110">By default, the variables in remote commands are assumed to be defined in the session that runs the command.</span></span> <span data-ttu-id="53f50-111">在本地会话中定义的变量必须在命令中标识为局部变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-111">Variables that are defined in a local session, must be identified as local variables in the command.</span></span>

## <a name="using-remote-variables"></a><span data-ttu-id="53f50-112">使用远程变量</span><span class="sxs-lookup"><span data-stu-id="53f50-112">Using remote variables</span></span>

<span data-ttu-id="53f50-113">PowerShell 假设在运行该命令的会话中定义了远程命令中使用的变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-113">PowerShell assumes that the variables used in remote commands are defined in the session in which the command runs.</span></span>

<span data-ttu-id="53f50-114">在此示例中， `$ps` 变量在运行该命令的临时会话中定义 `Get-WinEvent` 。</span><span class="sxs-lookup"><span data-stu-id="53f50-114">In this example, the `$ps` variable is defined in the temporary session in which the `Get-WinEvent` command runs.</span></span>

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

<span data-ttu-id="53f50-115">当命令在持久会话（ **PSSession** ）中运行时，必须在该会话中定义远程变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-115">When the command runs in a persistent session, **PSSession** , the remote variable must be defined in that session.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a><span data-ttu-id="53f50-116">使用局部变量</span><span class="sxs-lookup"><span data-stu-id="53f50-116">Using local variables</span></span>

<span data-ttu-id="53f50-117">可以使用远程命令中的局部变量，但必须在本地会话中定义此变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-117">You can use local variables in remote commands, but the variable must be defined in the local session.</span></span>

<span data-ttu-id="53f50-118">从 PowerShell 3.0 开始，可以使用 `Using` 作用域修饰符来标识远程命令中的局部变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-118">Beginning in PowerShell 3.0, you can use the `Using` scope modifier to identify a local variable in a remote command.</span></span>

<span data-ttu-id="53f50-119">的语法如下所示 `Using` ：</span><span class="sxs-lookup"><span data-stu-id="53f50-119">The syntax of `Using` is as follows:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="53f50-120">在下面的示例中， `$ps` 变量是在本地会话中创建的，但在运行该命令的会话中使用。</span><span class="sxs-lookup"><span data-stu-id="53f50-120">In the following example, the `$ps` variable is created in the local session, but is used in the session in which the command runs.</span></span> <span data-ttu-id="53f50-121">`Using`作用域修饰符将 `$ps` 标识为局部变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-121">The `Using` scope modifier identifies `$ps` as a local variable.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

<span data-ttu-id="53f50-122">`Using`作用域修饰符可用于 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="53f50-122">The `Using` scope modifier can be used in a **PSSession** .</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

<span data-ttu-id="53f50-123">变量引用，如 `$using:var` `$var` 从调用方的上下文扩展为变量的值。</span><span class="sxs-lookup"><span data-stu-id="53f50-123">A variable reference such as `$using:var` expands to the value of variable `$var` from the caller's context.</span></span> <span data-ttu-id="53f50-124">您无法访问调用方的变量对象。</span><span class="sxs-lookup"><span data-stu-id="53f50-124">You do not get access to the caller's variable object.</span></span>
<span data-ttu-id="53f50-125">`Using`作用域修饰符不能用于修改 **PSSession** 内的局部变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-125">The `Using` scope modifier cannot be used to modify a local variable within the **PSSession** .</span></span> <span data-ttu-id="53f50-126">例如，下面的代码不起作用：</span><span class="sxs-lookup"><span data-stu-id="53f50-126">For example, the following code does not work:</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

<span data-ttu-id="53f50-127">有关的详细信息 `Using` ，请参阅 [about_Scopes](./about_Scopes.md)</span><span class="sxs-lookup"><span data-stu-id="53f50-127">For more information about `Using`, see [about_Scopes](./about_Scopes.md)</span></span>

### <a name="using-splatting"></a><span data-ttu-id="53f50-128">使用展开</span><span class="sxs-lookup"><span data-stu-id="53f50-128">Using splatting</span></span>

<span data-ttu-id="53f50-129">PowerShell 展开将参数名称和值的集合传递给命令。</span><span class="sxs-lookup"><span data-stu-id="53f50-129">PowerShell splatting passes a collection of parameter names and values to a command.</span></span> <span data-ttu-id="53f50-130">有关详细信息，请参阅 [about_Splatting](about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="53f50-130">For more information, see [about_Splatting](about_Splatting.md).</span></span>

<span data-ttu-id="53f50-131">在此示例中，展开变量 `$Splat` 是在本地计算机上设置的哈希表。</span><span class="sxs-lookup"><span data-stu-id="53f50-131">In this example, the splatting variable, `$Splat` is a hash table that is set up on the local computer.</span></span> <span data-ttu-id="53f50-132">`Invoke-Command`连接到远程计算机会话。</span><span class="sxs-lookup"><span data-stu-id="53f50-132">The `Invoke-Command` connects to a remote computer session.</span></span> <span data-ttu-id="53f50-133">**ScriptBlock** 将 `Using` 作用域修饰符与位于 () 符号一起使用， `@` 以表示 splatted 变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-133">The **ScriptBlock** uses the `Using` scope modifier with the At (`@`) symbol to represent the splatted variable.</span></span>

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a><span data-ttu-id="53f50-134">需要 "Using" 作用域修饰符的其他情况</span><span class="sxs-lookup"><span data-stu-id="53f50-134">Other situations where the 'Using' scope modifier is needed</span></span>

<span data-ttu-id="53f50-135">对于任何执行进程外的脚本或命令，都需要 `Using` 范围修饰符来嵌入调用会话范围内的变量值，以便使会话代码不能访问它们。</span><span class="sxs-lookup"><span data-stu-id="53f50-135">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="53f50-136">`Using`以下上下文支持作用域修饰符：</span><span class="sxs-lookup"><span data-stu-id="53f50-136">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="53f50-137">远程执行的命令，已开始 `Invoke-Command` 使用 **ComputerName** 、 **HostName** 、 **SSHConnection** 或 **Session** 参数 (远程会话) </span><span class="sxs-lookup"><span data-stu-id="53f50-137">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="53f50-138">后台作业， `Start-Job` (进程外会话开始) </span><span class="sxs-lookup"><span data-stu-id="53f50-138">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="53f50-139">通过 `Start-ThreadJob` 或 `ForEach-Object -Parallel` (单独的线程会话启动的线程作业) </span><span class="sxs-lookup"><span data-stu-id="53f50-139">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="53f50-140">根据上下文，嵌入变量值是调用方的作用域中的数据的独立副本或对其的引用。</span><span class="sxs-lookup"><span data-stu-id="53f50-140">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="53f50-141">在远程和进程外会话中，它们始终是独立的副本。</span><span class="sxs-lookup"><span data-stu-id="53f50-141">In remote and out-of-process sessions, they are always independent copies.</span></span> <span data-ttu-id="53f50-142">在线程会话中，它们是通过引用传递的。</span><span class="sxs-lookup"><span data-stu-id="53f50-142">In thread sessions, they are passed by reference.</span></span>

## <a name="serialization-of-variable-values"></a><span data-ttu-id="53f50-143">变量值的序列化</span><span class="sxs-lookup"><span data-stu-id="53f50-143">Serialization of variable values</span></span>

<span data-ttu-id="53f50-144">远程执行的命令和后台作业在进程外运行。</span><span class="sxs-lookup"><span data-stu-id="53f50-144">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="53f50-145">进程外会话使用基于 XML 的序列化和反序列化来使变量的值可在进程边界内使用。</span><span class="sxs-lookup"><span data-stu-id="53f50-145">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="53f50-146">序列化进程将对象转换为包含原始对象属性但不包含其方法的 **PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="53f50-146">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="53f50-147">对于有限类型的类型，请将解除冻结对象反序列化为原始类型。</span><span class="sxs-lookup"><span data-stu-id="53f50-147">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="53f50-148">解除冻结对象是原始对象实例的副本。</span><span class="sxs-lookup"><span data-stu-id="53f50-148">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="53f50-149">它具有类型属性和方法。</span><span class="sxs-lookup"><span data-stu-id="53f50-149">It has the type properties and methods.</span></span> <span data-ttu-id="53f50-150">对于简单的类型（如 **system.object** ），副本是精确的。</span><span class="sxs-lookup"><span data-stu-id="53f50-150">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="53f50-151">对于复杂类型，复制为完善。</span><span class="sxs-lookup"><span data-stu-id="53f50-151">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="53f50-152">例如，解除冻结证书对象不包含私钥。</span><span class="sxs-lookup"><span data-stu-id="53f50-152">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="53f50-153">所有其他类型的实例都是 **PSObject** 实例。</span><span class="sxs-lookup"><span data-stu-id="53f50-153">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="53f50-154">**PSTypeNames** 属性包含以 **反序列化** 的原始类型名称，例如 **Deserialized.System。Data DataTable**</span><span class="sxs-lookup"><span data-stu-id="53f50-154">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

## <a name="using-local-variables-with-argumentlist-parameter"></a><span data-ttu-id="53f50-155">使用带有 **ArgumentList** 参数的局部变量</span><span class="sxs-lookup"><span data-stu-id="53f50-155">Using local variables with **ArgumentList** parameter</span></span>

<span data-ttu-id="53f50-156">可以通过为远程命令定义参数并使用 cmdlet 的 **ArgumentList** 参数 `Invoke-Command` 将局部变量指定为参数值，来在远程命令中使用局部变量。</span><span class="sxs-lookup"><span data-stu-id="53f50-156">You can use local variables in a remote command by defining parameters for the remote command and using the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

- <span data-ttu-id="53f50-157">使用 `param` 关键字为远程命令定义参数。</span><span class="sxs-lookup"><span data-stu-id="53f50-157">Use the `param` keyword to define parameters for the remote command.</span></span> <span data-ttu-id="53f50-158">参数名称是不需要与本地变量名称匹配的占位符。</span><span class="sxs-lookup"><span data-stu-id="53f50-158">The parameter names are placeholders that don't need to match the local variable's name.</span></span>

- <span data-ttu-id="53f50-159">使用命令中由关键字定义的参数 `param` 。</span><span class="sxs-lookup"><span data-stu-id="53f50-159">Use the parameters defined by the `param` keyword in the command.</span></span>

- <span data-ttu-id="53f50-160">使用 cmdlet 的 **ArgumentList** 参数 `Invoke-Command` 将本地变量指定为参数值。</span><span class="sxs-lookup"><span data-stu-id="53f50-160">Use the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

<span data-ttu-id="53f50-161">例如，以下命令在 `$ps` 本地会话中定义该变量，然后在远程命令中使用它。</span><span class="sxs-lookup"><span data-stu-id="53f50-161">For example, the following commands define the `$ps` variable in the local session and then use it in a remote command.</span></span> <span data-ttu-id="53f50-162">该命令使用 `$log` 作为参数名称，使用局部变量 `$ps` 作为其值。</span><span class="sxs-lookup"><span data-stu-id="53f50-162">The command uses `$log` as the parameter name and the local variable, `$ps`, as its value.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a><span data-ttu-id="53f50-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53f50-163">See also</span></span>

[<span data-ttu-id="53f50-164">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="53f50-164">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="53f50-165">about_Remote</span><span class="sxs-lookup"><span data-stu-id="53f50-165">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="53f50-166">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="53f50-166">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="53f50-167">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="53f50-167">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="53f50-168">about_Variables</span><span class="sxs-lookup"><span data-stu-id="53f50-168">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="53f50-169">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="53f50-169">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="53f50-170">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="53f50-170">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="53f50-171">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="53f50-171">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="53f50-172">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="53f50-172">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)

@Microsoft.PowerShell.Core.ForEach-Object

