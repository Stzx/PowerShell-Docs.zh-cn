---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 49838449bd2ffe949c4b2f1310c3f68c40867908
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198999"
---
# <span data-ttu-id="ef642-103">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="ef642-103">Get-CimInstance</span></span>

## <span data-ttu-id="ef642-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ef642-104">SYNOPSIS</span></span>
<span data-ttu-id="ef642-105">从 CIM 服务器获取类的 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-105">Gets the CIM instances of a class from a CIM server.</span></span>

## <span data-ttu-id="ef642-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef642-106">SYNTAX</span></span>

### <span data-ttu-id="ef642-107">ClassNameComputerSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="ef642-107">ClassNameComputerSet (Default)</span></span>

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ef642-108">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="ef642-108">ResourceUriSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ef642-109">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="ef642-109">QuerySessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### <span data-ttu-id="ef642-110">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="ef642-110">ClassNameSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ef642-111">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="ef642-111">CimInstanceSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="ef642-112">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="ef642-112">CimInstanceComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="ef642-113">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="ef642-113">ResourceUriComputerSet</span></span>

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ef642-114">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="ef642-114">QueryComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## <span data-ttu-id="ef642-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef642-115">DESCRIPTION</span></span>

<span data-ttu-id="ef642-116">`Get-CimInstance`Cmdlet 从 cim 服务器获取类的 cim 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-116">The `Get-CimInstance` cmdlet gets the CIM instances of a class from a CIM server.</span></span> <span data-ttu-id="ef642-117">可以为此 cmdlet 指定类名或查询。</span><span class="sxs-lookup"><span data-stu-id="ef642-117">You can specify either the class name or a query for this cmdlet.</span></span> <span data-ttu-id="ef642-118">此 cmdlet 将返回一个或多个 CIM 实例对象，这些对象表示 CIM 服务器上存在的 CIM 实例的快照。</span><span class="sxs-lookup"><span data-stu-id="ef642-118">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances present on the CIM server.</span></span>

<span data-ttu-id="ef642-119">如果未指定 **InputObject** 参数，该 cmdlet 将采用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="ef642-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="ef642-120">如果 **ComputerName** 参数和 **CimSession** 参数均未指定，则此 cmdlet 将在本地 Windows Management Instrumentation (WMI) 使用组件对象模型 (COM) 会话。</span><span class="sxs-lookup"><span data-stu-id="ef642-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="ef642-121">如果指定 **computername** 参数或 **CimSession** 参数，则此 cmdlet 适用于 **ComputerName** 参数或 **CimSession** 参数指定的 CIM 服务器。</span><span class="sxs-lookup"><span data-stu-id="ef642-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="ef642-122">如果指定了 **InputObject** 参数，该 cmdlet 将采用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="ef642-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="ef642-123">如果 **ComputerName** 参数和 **CimSession** 参数均未指定，则此 cmdlet 将使用输入对象中的 CIM 会话或计算机名称。</span><span class="sxs-lookup"><span data-stu-id="ef642-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="ef642-124">如果指定了 **ComputerName** 参数或 **CimSession** 参数，则此 cmdlet 将使用 CimSession 参数值或 **ComputerName** 参数值。</span><span class="sxs-lookup"><span data-stu-id="ef642-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the CimSession parameter value or **ComputerName** parameter value.</span></span>

## <span data-ttu-id="ef642-125">示例</span><span class="sxs-lookup"><span data-stu-id="ef642-125">EXAMPLES</span></span>

### <span data-ttu-id="ef642-126">示例1：获取指定类的 CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-126">Example 1: Get the CIM instances of a specified class</span></span>

<span data-ttu-id="ef642-127">此示例将检索名为 **Win32_Process** 的类的 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-127">This example retrieves the CIM instances of a class named **Win32_Process** .</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process
```

### <span data-ttu-id="ef642-128">示例2：从 WMI 服务器获取命名空间列表</span><span class="sxs-lookup"><span data-stu-id="ef642-128">Example 2: Get a list of namespaces from a WMI server</span></span>

<span data-ttu-id="ef642-129">此示例在 WMI 服务器上的 **根** 命名空间下检索命名空间的列表。</span><span class="sxs-lookup"><span data-stu-id="ef642-129">This example retrieves a list of namespaces under the **Root** namespace on a WMI server.</span></span>

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### <span data-ttu-id="ef642-130">示例3：获取使用查询筛选的类的实例</span><span class="sxs-lookup"><span data-stu-id="ef642-130">Example 3: Get instances of a class filtered by using a query</span></span>

<span data-ttu-id="ef642-131">此示例使用 **查询** 参数指定的查询，检索以名为 **Win32_Process** 的类的字母 **P** 开头的所有 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-131">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the query specified by a **Query** parameter.</span></span>

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### <span data-ttu-id="ef642-132">示例4：获取通过使用类名称和筛选器表达式筛选的类的实例</span><span class="sxs-lookup"><span data-stu-id="ef642-132">Example 4: Get instances of a class filtered by using a class name and a filter expression</span></span>

<span data-ttu-id="ef642-133">此示例使用 Filter 参数检索以名为 **Win32_Process** 的类的字母 **P** 开头的所有 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-133">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the Filter parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### <span data-ttu-id="ef642-134">示例5：获取仅填充了密钥属性的 CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-134">Example 5: Get the CIM instances with only key properties filled in</span></span>

<span data-ttu-id="ef642-135">此示例在内存中为名为 **Win32_Process** 的类创建一个名为的新 CIM 实例，该实例具有键属性 `@{ "Handle"=0 }` ，并将其存储在名为的变量中 `$x` 。</span><span class="sxs-lookup"><span data-stu-id="ef642-135">This example creates a new CIM instance in memory for a class named **Win32_Process** with the key property `@{ "Handle"=0 }` and stores it in a variable named `$x`.</span></span> <span data-ttu-id="ef642-136">变量作为 CIM 实例传递到 `Get-CimInstance` cmdlet 以获取特定的实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-136">The variable is passed as a CIM instance to the `Get-CimInstance` cmdlet to get a particular instance.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### <span data-ttu-id="ef642-137">示例6：检索并重复使用 CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-137">Example 6: Retrieve CIM instances and reuse them</span></span>

<span data-ttu-id="ef642-138">此示例将获取名为 **Win32_Process** 的类的 CIM 实例，并将其存储在变量 `$x` 和中 `$y` 。</span><span class="sxs-lookup"><span data-stu-id="ef642-138">This example gets the CIM instances of a class named **Win32_Process** and stores them in the variables `$x` and `$y`.</span></span> <span data-ttu-id="ef642-139">然后，将变量设置为 `$x` 仅包含 **Name** 和 **KernelModeTime** 属性的表，并将该表设置为 "自动 **调整大小** "。</span><span class="sxs-lookup"><span data-stu-id="ef642-139">The variable `$x` is then formatted in a table containing only the **Name** and **KernelModeTime** properties, the table set to **AutoSize** .</span></span>

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### <span data-ttu-id="ef642-140">示例7：从远程计算机获取 CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-140">Example 7: Get CIM instances from remote computer</span></span>

<span data-ttu-id="ef642-141">此示例从名为 **Server01** 和 **Server02** 的远程计算机中检索名为 **Win32_ComputerSystem** 的类的 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-141">This example retrieves the CIM instances of a class named **Win32_ComputerSystem** from the remote computers named **Server01** and **Server02** .</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### <span data-ttu-id="ef642-142">示例8：仅获取密钥属性，而不是所有属性</span><span class="sxs-lookup"><span data-stu-id="ef642-142">Example 8: Getting only the key properties, instead of all properties</span></span>

<span data-ttu-id="ef642-143">此示例仅检索密钥属性，这会减少对象和网络流量的大小。</span><span class="sxs-lookup"><span data-stu-id="ef642-143">This example retrieves only the key properties, which reduces the size of the object and network traffic.</span></span>

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### <span data-ttu-id="ef642-144">示例9：仅获取属性的子集，而不是所有属性</span><span class="sxs-lookup"><span data-stu-id="ef642-144">Example 9: Getting only a subset of properties, instead of all properties</span></span>

<span data-ttu-id="ef642-145">此示例仅检索部分属性，这会减少对象和网络流量的大小。</span><span class="sxs-lookup"><span data-stu-id="ef642-145">This example retrieves only a subset of properties, which reduces the size of the object and network traffic.</span></span>

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

<span data-ttu-id="ef642-146">使用 **属性** 参数检索到的实例可用于执行其他 CIM 操作，例如 `Set-CimInstance` 或 `Invoke-CimMethod` 。</span><span class="sxs-lookup"><span data-stu-id="ef642-146">The instance retrieved with the **Property** parameter can be used to perform other CIM operations, for example `Set-CimInstance` or `Invoke-CimMethod`.</span></span>

### <span data-ttu-id="ef642-147">示例10：使用 CIM 会话获取 CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-147">Example 10: Get the CIM instance using CIM session</span></span>

<span data-ttu-id="ef642-148">此示例使用 cmdlet 在名为 **Server01** 和 **Server02** 的计算机上创建 CIM 会话 `New-CimSession` ，并将会话信息存储在名为的变量中 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="ef642-148">This example creates a CIM session on the computers named **Server01** and **Server02** using the `New-CimSession` cmdlet and stores the session information in a variable named `$s`.</span></span> <span data-ttu-id="ef642-149">然后，使用 CimSession 参数将变量的内容传递到 `Get-CimInstance` ， **CimSession** 以获取名为 **WIN32_COMPUTERSYSTEM** 的类的 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-149">The contents of the variable are then passed to `Get-CimInstance` by using the **CimSession** parameter, to get the CIM instances of the class named **Win32_ComputerSystem** .</span></span>

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## <span data-ttu-id="ef642-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef642-150">PARAMETERS</span></span>

### <span data-ttu-id="ef642-151">-CimSession</span><span class="sxs-lookup"><span data-stu-id="ef642-151">-CimSession</span></span>

<span data-ttu-id="ef642-152">指定要用于此 cmdlet 的 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="ef642-152">Specifies the CIM session to use for this cmdlet.</span></span> <span data-ttu-id="ef642-153">输入包含 CIM 会话的变量，或输入创建或获取 CIM 会话的命令（如 `New-CimSession` 或 `Get-CimSession` cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="ef642-153">Enter a variable that contains the CIM session or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="ef642-154">有关详细信息，请参阅 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)。</span><span class="sxs-lookup"><span data-stu-id="ef642-154">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-155">-ClassName</span><span class="sxs-lookup"><span data-stu-id="ef642-155">-ClassName</span></span>

<span data-ttu-id="ef642-156">指定要为其检索 CIM 实例的 CIM 类的名称。</span><span class="sxs-lookup"><span data-stu-id="ef642-156">Specifies the name of the CIM class for which to retrieve the CIM instances.</span></span> <span data-ttu-id="ef642-157">您可以使用 tab 自动补全来浏览类列表，因为 PowerShell 从本地 WMI 服务器获取类的列表以提供类名的列表。</span><span class="sxs-lookup"><span data-stu-id="ef642-157">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-158">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ef642-158">-ComputerName</span></span>

<span data-ttu-id="ef642-159">指定要在其上运行 CIM 操作的计算机。</span><span class="sxs-lookup"><span data-stu-id="ef642-159">Specifies computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="ef642-160">可以指定完全限定的域名 (FQDN) 、NetBIOS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ef642-160">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="ef642-161">如果未指定此参数，则该 cmdlet 将使用组件对象模型 (COM) 在本地计算机上执行操作。</span><span class="sxs-lookup"><span data-stu-id="ef642-161">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="ef642-162">如果指定此参数，则该 cmdlet 将使用 WsMan 协议创建到指定计算机的临时会话。</span><span class="sxs-lookup"><span data-stu-id="ef642-162">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="ef642-163">如果在同一台计算机上执行多个操作，请使用 CIM 会话进行连接以获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="ef642-163">If multiple operations are being performed on the same computer, connect using a CIM session for better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="ef642-164">-Filter</span></span>

<span data-ttu-id="ef642-165">指定要用作筛选器的 where 子句。</span><span class="sxs-lookup"><span data-stu-id="ef642-165">Specifies a where clause to use as a filter.</span></span> <span data-ttu-id="ef642-166">指定 **WQL** 或 **CQL** 查询语言中的子句。</span><span class="sxs-lookup"><span data-stu-id="ef642-166">Specify the clause in either the **WQL** or the **CQL** query language.</span></span> <span data-ttu-id="ef642-167">不要 `WHERE` 在参数的值中包含关键字。</span><span class="sxs-lookup"><span data-stu-id="ef642-167">Do not include the `WHERE` keyword in the value of the parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ef642-168">-InputObject</span></span>

<span data-ttu-id="ef642-169">指定要用作输入的 CIM 实例对象。</span><span class="sxs-lookup"><span data-stu-id="ef642-169">Specifies a CIM instance object to use as input.</span></span>

<span data-ttu-id="ef642-170">如果已在使用 CIM 实例对象，则可以使用此参数传递 CIM 实例对象，以便从 CIM 服务器获取最新的快照。</span><span class="sxs-lookup"><span data-stu-id="ef642-170">If you are already working with a CIM instance object, you can use this parameter to pass the CIM instance object in order to get the latest snapshot from the CIM server.</span></span> <span data-ttu-id="ef642-171">将 CIM 实例对象作为输入传递时，将 `Get-CimInstance` 从服务器使用 GET CIM 操作（而不是枚举或查询操作）返回对象。</span><span class="sxs-lookup"><span data-stu-id="ef642-171">When you pass a CIM instance object as an input, `Get-CimInstance` returns the object from server using a get CIM operation, instead of an enumerate or query operation.</span></span> <span data-ttu-id="ef642-172">使用 get CIM 操作比检索所有实例并筛选它们更有效。</span><span class="sxs-lookup"><span data-stu-id="ef642-172">Using a get CIM operation is more efficient than retrieving all instances and then filtering them.</span></span>

<span data-ttu-id="ef642-173">如果 CIM 类未实现 get 操作，则指定 **InputObject** 参数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="ef642-173">If the CIM class does not implement the get operation, then specifying the **InputObject** parameter returns an error.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-174">-KeyOnly</span><span class="sxs-lookup"><span data-stu-id="ef642-174">-KeyOnly</span></span>

<span data-ttu-id="ef642-175">指示只返回填充了键属性的对象。</span><span class="sxs-lookup"><span data-stu-id="ef642-175">Indicates that only objects with key properties populated are returned.</span></span> <span data-ttu-id="ef642-176">指定 **KeyOnly** 参数将减少通过网络传输的数据量。</span><span class="sxs-lookup"><span data-stu-id="ef642-176">Specifying the **KeyOnly** parameter reduces the amount of data transferred over the network.</span></span>

<span data-ttu-id="ef642-177">使用 **KeyOnly** 参数可仅返回对象的一小部分，该对象可用于其他操作，例如 `Set-CimInstance` 或 `Get-CimAssociatedInstance` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef642-177">Use the **KeyOnly** parameter to return only a small portion of the object, which can be used for other operations, such as the `Set-CimInstance` or `Get-CimAssociatedInstance` cmdlets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-178">-Namespace</span><span class="sxs-lookup"><span data-stu-id="ef642-178">-Namespace</span></span>

<span data-ttu-id="ef642-179">指定 CIM 类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ef642-179">Specifies the namespace of CIM class.</span></span>

<span data-ttu-id="ef642-180">默认命名空间为 **root/cimv2** 。</span><span class="sxs-lookup"><span data-stu-id="ef642-180">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="ef642-181">您可以使用 tab 自动补全来浏览命名空间列表，因为 PowerShell 从本地 WMI 服务器获取命名空间列表以提供命名空间列表。</span><span class="sxs-lookup"><span data-stu-id="ef642-181">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-182">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="ef642-182">-OperationTimeoutSec</span></span>

<span data-ttu-id="ef642-183">指定 cmdlet 等待计算机响应的时间量。</span><span class="sxs-lookup"><span data-stu-id="ef642-183">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="ef642-184">默认情况下，此参数的值为0，表示该 cmdlet 使用服务器的默认超时值。</span><span class="sxs-lookup"><span data-stu-id="ef642-184">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="ef642-185">如果 **OperationTimeoutSec** 参数设置为小于3分钟的稳定连接重试超时值，则不能恢复最后超过 **OperationTimeoutSec** 参数值的网络故障，因为在客户端重新连接之前，服务器上的操作将超时。</span><span class="sxs-lookup"><span data-stu-id="ef642-185">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-186">-Property</span><span class="sxs-lookup"><span data-stu-id="ef642-186">-Property</span></span>

<span data-ttu-id="ef642-187">指定要检索的实例属性集。</span><span class="sxs-lookup"><span data-stu-id="ef642-187">Specifies a set of instance properties to retrieve.</span></span> <span data-ttu-id="ef642-188">如果需要减小返回对象的大小（在内存中或网络上），请使用此参数。</span><span class="sxs-lookup"><span data-stu-id="ef642-188">Use this parameter when you need to reduce the size of the object returned, either in memory or over the network.</span></span> <span data-ttu-id="ef642-189">返回的对象还包含键属性，即使您未使用 **Property** 参数列出它们也是如此。</span><span class="sxs-lookup"><span data-stu-id="ef642-189">The object returned also contains the key properties even if you have not listed them using the **Property** parameter.</span></span> <span data-ttu-id="ef642-190">类的其他属性存在，但未填充它们。</span><span class="sxs-lookup"><span data-stu-id="ef642-190">Other properties of the class are present but they are not populated.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-191">-Query</span><span class="sxs-lookup"><span data-stu-id="ef642-191">-Query</span></span>

<span data-ttu-id="ef642-192">指定要在 CIM 服务器上运行的查询。</span><span class="sxs-lookup"><span data-stu-id="ef642-192">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="ef642-193">如果指定的值包含双引号 `"` 、单引号 `'` 或反斜杠 `\` ，则必须通过在它们前面加上反斜杠字符来对这些字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="ef642-193">If the value specified contains double quotes `"`, single quotes `'`, or a backslash `\`, you must escape those characters by prefixing them with the backslash character.</span></span> <span data-ttu-id="ef642-194">如果指定的值使用 WQL **LIKE** 运算符，则必须通过将以下字符括在方括号中来对其进行转义 `[]` ：百分比 `%` 、下划线 `_` 或左方括号 `[` 。</span><span class="sxs-lookup"><span data-stu-id="ef642-194">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets `[]`: percent `%`, underscore `_`, or opening square bracket `[`.</span></span>

<span data-ttu-id="ef642-195">不能使用元数据查询来检索类或事件查询的列表。</span><span class="sxs-lookup"><span data-stu-id="ef642-195">You cannot use a metadata query to retrieve a list of classes or an event query.</span></span> <span data-ttu-id="ef642-196">若要检索类的列表，请使用 `Get-CimClass` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef642-196">To retrieve a list of classes, use the `Get-CimClass` cmdlet.</span></span> <span data-ttu-id="ef642-197">若要检索事件查询，请使用 `Register-CimIndicationEvent` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef642-197">To retrieve an event query, use the `Register-CimIndicationEvent` cmdlet.</span></span>

<span data-ttu-id="ef642-198">您可以使用 **QueryDialect** 参数指定查询方言。</span><span class="sxs-lookup"><span data-stu-id="ef642-198">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-199">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="ef642-199">-QueryDialect</span></span>

<span data-ttu-id="ef642-200">指定用于查询参数的查询语言。</span><span class="sxs-lookup"><span data-stu-id="ef642-200">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="ef642-201">此参数的可接受值为： **WQL** 或 **CQL** 。</span><span class="sxs-lookup"><span data-stu-id="ef642-201">The acceptable values for this parameter are: **WQL** or **CQL** .</span></span> <span data-ttu-id="ef642-202">默认值为 **WQL** 。</span><span class="sxs-lookup"><span data-stu-id="ef642-202">The default value is **WQL** .</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-203">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="ef642-203">-ResourceUri</span></span>

<span data-ttu-id="ef642-204">指定资源类或实例 (URI) 的资源统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="ef642-204">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="ef642-205">URI 用于标识计算机上特定类型的资源，例如磁盘或进程。</span><span class="sxs-lookup"><span data-stu-id="ef642-205">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="ef642-206">URI 由前缀和指向资源的路径组成。</span><span class="sxs-lookup"><span data-stu-id="ef642-206">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="ef642-207">例如：</span><span class="sxs-lookup"><span data-stu-id="ef642-207">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="ef642-208">默认情况下，如果不指定此参数，则将使用 DMTF 标准资源 URI， `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` 并向其追加类名称。</span><span class="sxs-lookup"><span data-stu-id="ef642-208">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="ef642-209">**ResourceURI** 只能与使用 wsman 协议创建的 cim 会话一起使用，也可以在指定 **ComputerName** 参数时使用，后者使用 wsman 创建 cim 会话。</span><span class="sxs-lookup"><span data-stu-id="ef642-209">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="ef642-210">如果在不指定 **ComputerName** 参数的情况下指定此参数，或指定使用 DCOM 协议创建的 CIM 会话，则将收到错误，因为 DCOM 协议不支持 **ResourceURI** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef642-210">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="ef642-211">如果同时指定了 **ResourceUri** 参数和 **筛选器** 参数，则忽略 **筛选器** 参数。</span><span class="sxs-lookup"><span data-stu-id="ef642-211">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-212">-浅</span><span class="sxs-lookup"><span data-stu-id="ef642-212">-Shallow</span></span>

<span data-ttu-id="ef642-213">指示返回类的实例，但不包含任何子类的实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-213">Indicates that the instances of a class are returned without including the instances of any child classes.</span></span> <span data-ttu-id="ef642-214">默认情况下，该 cmdlet 将返回类及其子类的实例。</span><span class="sxs-lookup"><span data-stu-id="ef642-214">By default, the cmdlet returns the instances of a class and its child classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef642-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ef642-215">CommonParameters</span></span>

<span data-ttu-id="ef642-216">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ef642-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef642-217">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ef642-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef642-218">输入</span><span class="sxs-lookup"><span data-stu-id="ef642-218">INPUTS</span></span>

### <span data-ttu-id="ef642-219">CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-219">CIM Instance</span></span>

<span data-ttu-id="ef642-220">此 cmdlet 接受使用 InputObject 参数指定的输入对象。</span><span class="sxs-lookup"><span data-stu-id="ef642-220">This cmdlet accepts an input objects specified with the InputObject parameter.</span></span>

## <span data-ttu-id="ef642-221">输出</span><span class="sxs-lookup"><span data-stu-id="ef642-221">OUTPUTS</span></span>

### <span data-ttu-id="ef642-222">CIM 实例</span><span class="sxs-lookup"><span data-stu-id="ef642-222">CIM Instance</span></span>

<span data-ttu-id="ef642-223">此 cmdlet 将返回一个或多个 CIM 实例对象，这些对象表示 CIM 服务器上 CIM 实例的快照。</span><span class="sxs-lookup"><span data-stu-id="ef642-223">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances on the CIM server.</span></span>

## <span data-ttu-id="ef642-224">注释</span><span class="sxs-lookup"><span data-stu-id="ef642-224">NOTES</span></span>

## <span data-ttu-id="ef642-225">相关链接</span><span class="sxs-lookup"><span data-stu-id="ef642-225">RELATED LINKS</span></span>

[<span data-ttu-id="ef642-226">Format-Table</span><span class="sxs-lookup"><span data-stu-id="ef642-226">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="ef642-227">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="ef642-227">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)

[<span data-ttu-id="ef642-228">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="ef642-228">Get-CimClass</span></span>](Get-CimClass.md)

[<span data-ttu-id="ef642-229">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="ef642-229">Invoke-CimMethod</span></span>](invoke-cimmethod.md)

[<span data-ttu-id="ef642-230">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="ef642-230">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="ef642-231">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="ef642-231">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)

[<span data-ttu-id="ef642-232">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="ef642-232">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="ef642-233">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="ef642-233">Set-CimInstance</span></span>](Set-CimInstance.md)
