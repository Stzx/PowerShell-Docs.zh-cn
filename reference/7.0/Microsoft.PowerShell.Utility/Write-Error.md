---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: 883990ace87c947ad9f0e10100d4d1dc7f1b8cbe
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200524"
---
# <span data-ttu-id="0dc1f-103">Write-Error</span><span class="sxs-lookup"><span data-stu-id="0dc1f-103">Write-Error</span></span>

## <span data-ttu-id="0dc1f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0dc1f-104">SYNOPSIS</span></span>
<span data-ttu-id="0dc1f-105">将对象写入错误流。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-105">Writes an object to the error stream.</span></span>

## <span data-ttu-id="0dc1f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0dc1f-106">SYNTAX</span></span>

### <span data-ttu-id="0dc1f-107">NoException（默认值）</span><span class="sxs-lookup"><span data-stu-id="0dc1f-107">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="0dc1f-108">WithException</span><span class="sxs-lookup"><span data-stu-id="0dc1f-108">WithException</span></span>

```
Write-Error -Exception <Exception> [-Message <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="0dc1f-109">ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="0dc1f-109">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="0dc1f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0dc1f-110">DESCRIPTION</span></span>

<span data-ttu-id="0dc1f-111">`Write-Error`Cmdlet 声明非终止错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-111">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="0dc1f-112">默认情况下，将错误随输出一起在错误流中发送到主机程序来显示。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-112">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="0dc1f-113">若要编写非终止错误，请输入错误消息字符串、 **ErrorRecord** 对象，或 **Exception** 对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-113">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="0dc1f-114">使用的其他参数 `Write-Error` 填充错误记录。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-114">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="0dc1f-115">非终止错误将错误写入错误流，但它们不会停止命令处理。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-115">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="0dc1f-116">如果在输入项的集合中的一个项上声明非终止错误，则该命令会继续处理集合中的其他项。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-116">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="0dc1f-117">若要声明终止错误，请使用 `Throw` 关键字。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-117">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="0dc1f-118">有关详细信息，请参阅 [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-118">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="0dc1f-119">示例</span><span class="sxs-lookup"><span data-stu-id="0dc1f-119">EXAMPLES</span></span>

### <span data-ttu-id="0dc1f-120">示例1：为 RegistryKey 对象写入错误</span><span class="sxs-lookup"><span data-stu-id="0dc1f-120">Example 1: Write an error for RegistryKey object</span></span>

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

<span data-ttu-id="0dc1f-121">当 `Get-ChildItem` cmdlet 返回 `Microsoft.Win32.RegistryKey` 对象（例如 `HKLM:` `HKCU:` PowerShell 注册表提供程序的或驱动器中的对象）时，此命令声明一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-121">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="0dc1f-122">示例2：将错误消息写入控制台</span><span class="sxs-lookup"><span data-stu-id="0dc1f-122">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="0dc1f-123">此命令声明一个非终止错误，并写入“拒绝访问”错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-123">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="0dc1f-124">此命令使用 **Message** 参数来指定消息，但省略可选的 **Message** 参数名称。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-124">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="0dc1f-125">示例3：将错误写入控制台并指定类别</span><span class="sxs-lookup"><span data-stu-id="0dc1f-125">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="0dc1f-126">此命令声明一个非终止错误，并指定错误类别。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-126">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="0dc1f-127">示例4：使用 Exception 对象编写错误</span><span class="sxs-lookup"><span data-stu-id="0dc1f-127">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="0dc1f-128">此命令使用 **Exception** 对象来声明一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-128">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="0dc1f-129">第一个命令使用哈希表来创建 **System.Exception** 对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-129">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="0dc1f-130">它将异常对象保存在 `$E` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-130">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="0dc1f-131">可以使用哈希表来创建具有空构造函数的类型的任何对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-131">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="0dc1f-132">第二个命令使用 `Write-Error` cmdlet 声明非终止错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-132">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="0dc1f-133">**Exception** 参数的值是变量中的 **异常** 对象 `$E` 。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-133">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="0dc1f-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0dc1f-134">PARAMETERS</span></span>

### <span data-ttu-id="0dc1f-135">-Category</span><span class="sxs-lookup"><span data-stu-id="0dc1f-135">-Category</span></span>

<span data-ttu-id="0dc1f-136">指定的错误类别。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-136">Specifies the category of the error.</span></span> <span data-ttu-id="0dc1f-137">默认值为 **NotSpecified** 。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-137">The default value is **NotSpecified** .</span></span> <span data-ttu-id="0dc1f-138">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="0dc1f-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0dc1f-139">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="0dc1f-139">NotSpecified</span></span>
- <span data-ttu-id="0dc1f-140">OpenError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-140">OpenError</span></span>
- <span data-ttu-id="0dc1f-141">CloseError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-141">CloseError</span></span>
- <span data-ttu-id="0dc1f-142">DeviceError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-142">DeviceError</span></span>
- <span data-ttu-id="0dc1f-143">DeadlockDetected</span><span class="sxs-lookup"><span data-stu-id="0dc1f-143">DeadlockDetected</span></span>
- <span data-ttu-id="0dc1f-144">InvalidArgument</span><span class="sxs-lookup"><span data-stu-id="0dc1f-144">InvalidArgument</span></span>
- <span data-ttu-id="0dc1f-145">InvalidData</span><span class="sxs-lookup"><span data-stu-id="0dc1f-145">InvalidData</span></span>
- <span data-ttu-id="0dc1f-146">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="0dc1f-146">InvalidOperation</span></span>
- <span data-ttu-id="0dc1f-147">InvalidResult</span><span class="sxs-lookup"><span data-stu-id="0dc1f-147">InvalidResult</span></span>
- <span data-ttu-id="0dc1f-148">InvalidType</span><span class="sxs-lookup"><span data-stu-id="0dc1f-148">InvalidType</span></span>
- <span data-ttu-id="0dc1f-149">MetadataError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-149">MetadataError</span></span>
- <span data-ttu-id="0dc1f-150">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="0dc1f-150">NotImplemented</span></span>
- <span data-ttu-id="0dc1f-151">NotInstalled</span><span class="sxs-lookup"><span data-stu-id="0dc1f-151">NotInstalled</span></span>
- <span data-ttu-id="0dc1f-152">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="0dc1f-152">ObjectNotFound</span></span>
- <span data-ttu-id="0dc1f-153">OperationStopped</span><span class="sxs-lookup"><span data-stu-id="0dc1f-153">OperationStopped</span></span>
- <span data-ttu-id="0dc1f-154">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="0dc1f-154">OperationTimeout</span></span>
- <span data-ttu-id="0dc1f-155">SyntaxError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-155">SyntaxError</span></span>
- <span data-ttu-id="0dc1f-156">ParserError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-156">ParserError</span></span>
- <span data-ttu-id="0dc1f-157">PermissionDenied</span><span class="sxs-lookup"><span data-stu-id="0dc1f-157">PermissionDenied</span></span>
- <span data-ttu-id="0dc1f-158">ResourceBusy</span><span class="sxs-lookup"><span data-stu-id="0dc1f-158">ResourceBusy</span></span>
- <span data-ttu-id="0dc1f-159">ResourceExists</span><span class="sxs-lookup"><span data-stu-id="0dc1f-159">ResourceExists</span></span>
- <span data-ttu-id="0dc1f-160">ResourceUnavailable</span><span class="sxs-lookup"><span data-stu-id="0dc1f-160">ResourceUnavailable</span></span>
- <span data-ttu-id="0dc1f-161">ReadError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-161">ReadError</span></span>
- <span data-ttu-id="0dc1f-162">WriteError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-162">WriteError</span></span>
- <span data-ttu-id="0dc1f-163">FromStdErr</span><span class="sxs-lookup"><span data-stu-id="0dc1f-163">FromStdErr</span></span>
- <span data-ttu-id="0dc1f-164">SecurityError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-164">SecurityError</span></span>
- <span data-ttu-id="0dc1f-165">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-165">ProtocolError</span></span>
- <span data-ttu-id="0dc1f-166">ConnectionError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-166">ConnectionError</span></span>
- <span data-ttu-id="0dc1f-167">AuthenticationError</span><span class="sxs-lookup"><span data-stu-id="0dc1f-167">AuthenticationError</span></span>
- <span data-ttu-id="0dc1f-168">LimitsExceeded</span><span class="sxs-lookup"><span data-stu-id="0dc1f-168">LimitsExceeded</span></span>
- <span data-ttu-id="0dc1f-169">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="0dc1f-169">QuotaExceeded</span></span>
- <span data-ttu-id="0dc1f-170">NotEnabled</span><span class="sxs-lookup"><span data-stu-id="0dc1f-170">NotEnabled</span></span>

<span data-ttu-id="0dc1f-171">有关错误类别的信息，请参阅 [ErrorCategory 枚举](https://go.microsoft.com/fwlink/?LinkId=143600)。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-171">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-172">-CategoryActivity</span><span class="sxs-lookup"><span data-stu-id="0dc1f-172">-CategoryActivity</span></span>

<span data-ttu-id="0dc1f-173">指定导致错误的操作。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-173">Specifies the action that caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-174">-CategoryReason</span><span class="sxs-lookup"><span data-stu-id="0dc1f-174">-CategoryReason</span></span>

<span data-ttu-id="0dc1f-175">指定活动导致错误的方式或原因。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-175">Specifies how or why the activity caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-176">-CategoryTargetName</span><span class="sxs-lookup"><span data-stu-id="0dc1f-176">-CategoryTargetName</span></span>

<span data-ttu-id="0dc1f-177">指定当发生错误时被处理的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-177">Specifies the name of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-178">-CategoryTargetType</span><span class="sxs-lookup"><span data-stu-id="0dc1f-178">-CategoryTargetType</span></span>

<span data-ttu-id="0dc1f-179">指定当发生错误时被处理的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-179">Specifies the type of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-180">-ErrorId</span><span class="sxs-lookup"><span data-stu-id="0dc1f-180">-ErrorId</span></span>

<span data-ttu-id="0dc1f-181">指定 ID 字符串以标识错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-181">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="0dc1f-182">字符串应该是唯一的错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-182">The string should be unique to the error.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-183">-ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="0dc1f-183">-ErrorRecord</span></span>

<span data-ttu-id="0dc1f-184">指定一个表示错误的错误记录对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-184">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="0dc1f-185">使用对象的属性来描述错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-185">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="0dc1f-186">若要创建错误记录对象，请使用 `New-Object` cmdlet 或从自动变量中的数组获取错误记录对象 `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-186">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-187">-Exception</span><span class="sxs-lookup"><span data-stu-id="0dc1f-187">-Exception</span></span>

<span data-ttu-id="0dc1f-188">指定一个表示错误的异常对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-188">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="0dc1f-189">使用对象的属性来描述错误。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-189">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="0dc1f-190">若要创建异常对象，请使用哈希表或使用 `New-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-190">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-191">-Message</span><span class="sxs-lookup"><span data-stu-id="0dc1f-191">-Message</span></span>

<span data-ttu-id="0dc1f-192">指定错误的消息文本。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-192">Specifies the message text of the error.</span></span> <span data-ttu-id="0dc1f-193">如果文本包含空格或特殊字符，则将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-193">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="0dc1f-194">还可以通过管道将消息字符串传递给 `Write-Error` 。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-194">You can also pipe a message string to `Write-Error`.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-195">-RecommendedAction</span><span class="sxs-lookup"><span data-stu-id="0dc1f-195">-RecommendedAction</span></span>

<span data-ttu-id="0dc1f-196">指定用户在解决或阻止错误时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-196">Specifies the action that the user should take to resolve or prevent the error.</span></span>

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

### <span data-ttu-id="0dc1f-197">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="0dc1f-197">-TargetObject</span></span>

<span data-ttu-id="0dc1f-198">指定当发生错误时被处理的对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-198">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="0dc1f-199">输入对象、包含对象的变量或获取对象的命令。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-199">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0dc1f-200">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0dc1f-200">CommonParameters</span></span>

<span data-ttu-id="0dc1f-201">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0dc1f-202">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0dc1f-203">输入</span><span class="sxs-lookup"><span data-stu-id="0dc1f-203">INPUTS</span></span>

### <span data-ttu-id="0dc1f-204">System.String</span><span class="sxs-lookup"><span data-stu-id="0dc1f-204">System.String</span></span>

<span data-ttu-id="0dc1f-205">可以通过管道将包含错误消息的字符串传递给 `Write-Error` 。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-205">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="0dc1f-206">输出</span><span class="sxs-lookup"><span data-stu-id="0dc1f-206">OUTPUTS</span></span>

### <span data-ttu-id="0dc1f-207">错误对象</span><span class="sxs-lookup"><span data-stu-id="0dc1f-207">Error object</span></span>

<span data-ttu-id="0dc1f-208">`Write-Error` 仅写入错误流。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-208">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="0dc1f-209">它不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-209">It does not return any objects.</span></span>

## <span data-ttu-id="0dc1f-210">注释</span><span class="sxs-lookup"><span data-stu-id="0dc1f-210">NOTES</span></span>

<span data-ttu-id="0dc1f-211">`Write-Error` 不会更改自动变量的值 `$?` ，因此它不会指示终止错误情况。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-211">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="0dc1f-212">若要通知终止错误，请使用 [$PSCmdlet ( # B1 ](/dotnet/api/system.management.automation.cmdlet.writeerror) 方法。</span><span class="sxs-lookup"><span data-stu-id="0dc1f-212">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="0dc1f-213">相关链接</span><span class="sxs-lookup"><span data-stu-id="0dc1f-213">RELATED LINKS</span></span>

[<span data-ttu-id="0dc1f-214">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="0dc1f-214">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="0dc1f-215">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="0dc1f-215">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="0dc1f-216">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="0dc1f-216">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="0dc1f-217">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="0dc1f-217">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="0dc1f-218">Write-Host</span><span class="sxs-lookup"><span data-stu-id="0dc1f-218">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="0dc1f-219">Write-Output</span><span class="sxs-lookup"><span data-stu-id="0dc1f-219">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="0dc1f-220">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="0dc1f-220">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="0dc1f-221">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="0dc1f-221">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="0dc1f-222">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="0dc1f-222">Write-Warning</span></span>](Write-Warning.md)
