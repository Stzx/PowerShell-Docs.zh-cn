---
description: 介绍可用于获取 Windows PowerShell 中的 WMI 对象的 WMI 查询语言 (WQL)。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200227"
---
# <a name="about-wql"></a><span data-ttu-id="3e814-104">关于 WQL</span><span class="sxs-lookup"><span data-stu-id="3e814-104">About WQL</span></span>

## <a name="short-description"></a><span data-ttu-id="3e814-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="3e814-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="3e814-106">介绍可用于获取 Windows PowerShell 中的 WMI 对象的 WMI 查询语言 (WQL)。</span><span class="sxs-lookup"><span data-stu-id="3e814-106">Describes WMI Query Language (WQL), which can be used to get WMI objects in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3e814-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="3e814-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3e814-108">WQL 是 Windows Management Instrumentation (WMI) 查询语言，这是用于从 WMI 获取信息的语言。</span><span class="sxs-lookup"><span data-stu-id="3e814-108">WQL is the Windows Management Instrumentation (WMI) query language, which is the language used to get information from WMI.</span></span>

<span data-ttu-id="3e814-109">不需要使用 WQL 在 Windows PowerShell 中执行 WMI 查询。</span><span class="sxs-lookup"><span data-stu-id="3e814-109">You are not required to use WQL to perform a WMI query in Windows PowerShell.</span></span>
<span data-ttu-id="3e814-110">相反，你可以使用 Get-WmiObject 或 Get-CimInstance cmdlet 的参数。</span><span class="sxs-lookup"><span data-stu-id="3e814-110">Instead, you can use the parameters of the Get-WmiObject or Get-CimInstance cmdlets.</span></span> <span data-ttu-id="3e814-111">WQL 查询比标准 Get-WmiObject 命令要快一些，而且在数百个系统上运行命令时，性能得到了改善。</span><span class="sxs-lookup"><span data-stu-id="3e814-111">WQL queries are somewhat faster than standard Get-WmiObject commands and the improved performance is evident when the commands run on hundreds of systems.</span></span> <span data-ttu-id="3e814-112">但是，请确保编写成功的 WQL 查询所花费的时间不会提高性能。</span><span class="sxs-lookup"><span data-stu-id="3e814-112">However, be sure that the time you spend to write a successful WQL query doesn't outweigh the performance improvement.</span></span>

<span data-ttu-id="3e814-113">需要使用 WQL 的基本 WQL 语句为 Select、Where 和 From。</span><span class="sxs-lookup"><span data-stu-id="3e814-113">The basic WQL statements you need to use WQL are Select, Where, and From.</span></span>

## <a name="when-to-use-wql"></a><span data-ttu-id="3e814-114">何时使用 WQL</span><span class="sxs-lookup"><span data-stu-id="3e814-114">WHEN TO USE WQL</span></span>

<span data-ttu-id="3e814-115">使用 WMI 时，尤其是在使用 WQL 时，请不要忘记你也在使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3e814-115">When working with WMI, and especially with WQL, do not forget that you are also using Windows PowerShell.</span></span> <span data-ttu-id="3e814-116">通常，如果 WQL 查询不按预期工作，则使用标准 Windows PowerShell 命令比调试 WQL 查询更容易。</span><span class="sxs-lookup"><span data-stu-id="3e814-116">Often, if a WQL query does not work as expected, it's easier to use a standard Windows PowerShell command than to debug the WQL query.</span></span>

<span data-ttu-id="3e814-117">如果要从带宽受限的远程系统返回大量数据，则在有一个完全可接受的 Windows cmdlet 执行相同操作时，花费很多时间来尝试完美的复杂 WQL 查询，这种情况很少。</span><span class="sxs-lookup"><span data-stu-id="3e814-117">Unless you are returning massive amounts of data from across bandwidth-constrained remote systems, it is rarely productive to spend hours trying to perfect a complicated and convoluted WQL query when there is a perfectly acceptable Windows cmdlet that does the same thing, if a bit more slowly.</span></span>

## <a name="using-the-select-statement"></a><span data-ttu-id="3e814-118">使用 SELECT 语句</span><span class="sxs-lookup"><span data-stu-id="3e814-118">USING THE SELECT STATEMENT</span></span>

<span data-ttu-id="3e814-119">典型的 WMI 查询以 Select 语句开始，该语句获取 WMI 类的所有属性或特定属性。</span><span class="sxs-lookup"><span data-stu-id="3e814-119">A typical WMI query begins with a Select statement that gets all properties or particular properties of a WMI class.</span></span> <span data-ttu-id="3e814-120">若要选择 WMI 类的所有属性，请使用星号 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="3e814-120">To select all properties of a WMI class, use an asterisk (\*).</span></span> <span data-ttu-id="3e814-121">From 关键字指定 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="3e814-121">The From keyword specifies the WMI class.</span></span>

<span data-ttu-id="3e814-122">Select 语句具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="3e814-122">A Select statement has the following format:</span></span>

```
Select <property> from <WMI-class>
```

<span data-ttu-id="3e814-123">例如，下面的 Select 语句从 Win32_Bios WMI 类的实例中选择 ( \* ) 的所有属性。</span><span class="sxs-lookup"><span data-stu-id="3e814-123">For example, the following Select statement selects all properties (\*) from the instances of the Win32_Bios WMI class.</span></span>

```
Select * from Win32_Bios
```

<span data-ttu-id="3e814-124">若要选择 WMI 类的特定属性，请将属性名称置于 Select 和 From 关键字之间。</span><span class="sxs-lookup"><span data-stu-id="3e814-124">To select a particular property of a WMI class, place the property name between the Select and From keywords.</span></span>

<span data-ttu-id="3e814-125">下面的查询仅选择 Win32_Bios WMI 类中的 BIOS 的名称。</span><span class="sxs-lookup"><span data-stu-id="3e814-125">The following query selects only the name of the BIOS from the Win32_Bios WMI class.</span></span> <span data-ttu-id="3e814-126">该命令将查询保存在 $queryName 变量中。</span><span class="sxs-lookup"><span data-stu-id="3e814-126">The command saves the query in the $queryName variable.</span></span>

```
Select Name from Win32_Bios
```

<span data-ttu-id="3e814-127">若要选择多个属性，请使用逗号分隔属性名称。</span><span class="sxs-lookup"><span data-stu-id="3e814-127">To select more than one property, use commas to separate the property names.</span></span>
<span data-ttu-id="3e814-128">以下 WMI 查询选择 Win32_Bios WMI 类的名称和版本。</span><span class="sxs-lookup"><span data-stu-id="3e814-128">The following WMI query selects the name and the version of the Win32_Bios WMI class.</span></span> <span data-ttu-id="3e814-129">该命令将查询保存在 $queryNameVersion 变量中。</span><span class="sxs-lookup"><span data-stu-id="3e814-129">The command saves the query in the $queryNameVersion variable.</span></span>

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a><span data-ttu-id="3e814-130">使用 WQL 查询</span><span class="sxs-lookup"><span data-stu-id="3e814-130">USING THE WQL QUERY</span></span>

<span data-ttu-id="3e814-131">有三种方法可在 Windows PowerShell 命令中使用 WQL 查询。</span><span class="sxs-lookup"><span data-stu-id="3e814-131">There are three ways to use WQL query in Windows PowerShell command.</span></span>

- <span data-ttu-id="3e814-132">使用 Get-WmiObject cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e814-132">Use the Get-WmiObject cmdlet</span></span>
- <span data-ttu-id="3e814-133">使用 Get-CimInstance cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e814-133">Use the Get-CimInstance cmdlet</span></span>
- <span data-ttu-id="3e814-134">使用 [wmisearcher] 类型加速器。</span><span class="sxs-lookup"><span data-stu-id="3e814-134">Use the [wmisearcher] type accelerator.</span></span>

## <a name="using-the-get-wmiobject-cmdlet"></a><span data-ttu-id="3e814-135">使用 GET-WMIOBJECT CMDLET</span><span class="sxs-lookup"><span data-stu-id="3e814-135">USING THE GET-WMIOBJECT CMDLET</span></span>

<span data-ttu-id="3e814-136">使用 WQL 查询的最基本方法是将其括在引号中 (作为字符串) ，然后使用查询字符串作为 Get-WmiObject cmdlet 的 Query 参数的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-136">The most basic way to use the WQL query is to enclose it in quotation marks (as a string) and then use the query string as the value of the Query parameter of the Get-WmiObject cmdlet, as shown in the following example.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="3e814-137">你还可以将 WQL 语句保存在一个变量中，然后将该变量用作 Query 参数的值，如下面的命令中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-137">You can also save the WQL statement in a variable and then use the variable as the value of the Query parameter, as shown in the following command.</span></span>

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

<span data-ttu-id="3e814-138">可以在任何 WQL 语句中使用这两种格式。</span><span class="sxs-lookup"><span data-stu-id="3e814-138">You can use either format with any WQL statement.</span></span> <span data-ttu-id="3e814-139">以下命令使用 $queryName 变量中的查询来仅获取系统 BIOS 的名称和版本属性。</span><span class="sxs-lookup"><span data-stu-id="3e814-139">The following command uses the query in the $queryName variable to get only the name and version properties of the system BIOS.</span></span>

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

<span data-ttu-id="3e814-140">请记住，可以使用 Get-WmiObject cmdlet 的参数获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="3e814-140">Remember that you can use the parameters of the Get-WmiObject cmdlet to get the same result.</span></span> <span data-ttu-id="3e814-141">例如，以下命令还获取 Win32_Bios WMI 类的实例的 Name 和 Version 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3e814-141">For example, the following command also gets the values of the Name and Version properties of instances of the Win32_Bios WMI class.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a><span data-ttu-id="3e814-142">使用 CIMINSTANCE CMDLET</span><span class="sxs-lookup"><span data-stu-id="3e814-142">USING THE GET-CIMINSTANCE CMDLET</span></span>

<span data-ttu-id="3e814-143">从 Windows PowerShell 3.0 开始，可以使用 Get-CimInstance cmdlet 来运行 WQL 查询。</span><span class="sxs-lookup"><span data-stu-id="3e814-143">Beginning in Windows PowerShell 3.0, you can use the Get-CimInstance cmdlet to run WQL queries.</span></span>

<span data-ttu-id="3e814-144">Get-CimInstance 获取与 CIM 兼容的类（包括 WMI 类）的实例。</span><span class="sxs-lookup"><span data-stu-id="3e814-144">Get-CimInstance gets instances of CIM-compliant classes, including WMI classes.</span></span> <span data-ttu-id="3e814-145">Windows PowerShell 3.0 引入的 CIM cmdlet 执行与 WMI cmdlet 相同的任务。</span><span class="sxs-lookup"><span data-stu-id="3e814-145">The CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="3e814-146">CIM cmdlet 符合 WS-Management (WSMan) 标准和通用信息模型 (CIM) 标准，这使 cmdlet 能够使用相同的技术来管理运行其他操作系统的 Windows 计算机和计算机。</span><span class="sxs-lookup"><span data-stu-id="3e814-146">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage Windows computers and computers that are running other operating systems.</span></span>

<span data-ttu-id="3e814-147">以下命令使用 Get-CimInstance cmdlet 来运行 WQL 查询。</span><span class="sxs-lookup"><span data-stu-id="3e814-147">The following command uses the Get-CimInstance cmdlet to run a WQL query.</span></span>

<span data-ttu-id="3e814-148">任何可与 Get-WmiObject 一起使用的 WQL 查询也可用于 CimInstance。</span><span class="sxs-lookup"><span data-stu-id="3e814-148">Any WQL query that can be used with Get-WmiObject can also be used with Get-CimInstance.</span></span>

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="3e814-149">Get-CimInstance 返回 CimInstance 对象，而不是 Get-WmiObject 返回的 System.management.managementobject，但对象非常类似。</span><span class="sxs-lookup"><span data-stu-id="3e814-149">Get-CimInstance returns a CimInstance object, instead of the ManagementObject that Get-WmiObject returns, but the objects are quite similar.</span></span>

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a><span data-ttu-id="3e814-150">使用 [wmisearcher] 类型加速器</span><span class="sxs-lookup"><span data-stu-id="3e814-150">USING THE [wmisearcher] TYPE ACCELERATOR</span></span>

<span data-ttu-id="3e814-151">[Wmisearcher] 类型加速器从 WQL 语句字符串创建 ManagementObjectSearcher 对象。</span><span class="sxs-lookup"><span data-stu-id="3e814-151">The [wmisearcher] type accelerator creates a ManagementObjectSearcher object from a WQL statement string.</span></span> <span data-ttu-id="3e814-152">ManagementObjectSearcher 对象具有多个属性和方法，但最基本的方法是 Get 方法，该方法调用指定的 WMI 查询并返回生成的对象。</span><span class="sxs-lookup"><span data-stu-id="3e814-152">The ManagementObjectSearcher object has many properties and methods, but the most basic method is the Get method, which invokes the specified WMI query and returns the resulting objects.</span></span>

<span data-ttu-id="3e814-153">通过使用 [wmisearcher]，可轻松访问 ManagementObjectSearcher .NET Framework 类。</span><span class="sxs-lookup"><span data-stu-id="3e814-153">By using the [wmisearcher], you gain easy access to the ManagementObjectSearcher .NET Framework class.</span></span> <span data-ttu-id="3e814-154">这使你能够查询 WMI 并配置执行查询的方式。</span><span class="sxs-lookup"><span data-stu-id="3e814-154">This lets you query WMI and to configure the way the query is conducted.</span></span>

<span data-ttu-id="3e814-155">使用 [wmisearcher] 类型加速器：</span><span class="sxs-lookup"><span data-stu-id="3e814-155">To use the [wmisearcher] type accelerator:</span></span>

1. <span data-ttu-id="3e814-156">将 WQL 字符串强制转换为 ManagementObjectSearcher 对象。</span><span class="sxs-lookup"><span data-stu-id="3e814-156">Cast the  WQL string into a ManagementObjectSearcher object.</span></span>
2. <span data-ttu-id="3e814-157">调用 ManagementObjectSearcher 对象的 Get 方法。</span><span class="sxs-lookup"><span data-stu-id="3e814-157">Call the Get method of the ManagementObjectSearcher object.</span></span>

<span data-ttu-id="3e814-158">例如，以下命令强制转换 "全选" 查询，将结果保存在 $bios 变量中，然后调用 $bios 变量中 ManagementObjectSearcher 对象的 Get 方法。</span><span class="sxs-lookup"><span data-stu-id="3e814-158">For example, the following command casts the "select all" query, saves the result in the $bios variable, and then calls the Get method of the ManagementObjectSearcher object in the $bios variable.</span></span>

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="3e814-159">注意：默认情况下，仅显示所选的对象属性。</span><span class="sxs-lookup"><span data-stu-id="3e814-159">NOTE: Only selected object properties are displayed by default.</span></span> <span data-ttu-id="3e814-160">这些属性是在 Types.ps1xml 文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="3e814-160">These properties are defined in the Types.ps1xml file.</span></span>

<span data-ttu-id="3e814-161">可以使用 [wmisearcher] 类型加速器来转换查询或变量。</span><span class="sxs-lookup"><span data-stu-id="3e814-161">You can use the [wmisearcher] type accelerator to cast the query or the variable.</span></span> <span data-ttu-id="3e814-162">在下面的示例中，将使用 [wmisearcher] 类型加速器来转换变量。</span><span class="sxs-lookup"><span data-stu-id="3e814-162">In the following example, the [wmisearcher] type accelerator is used to cast the variable.</span></span> <span data-ttu-id="3e814-163">结果是相同的。</span><span class="sxs-lookup"><span data-stu-id="3e814-163">The result is the same.</span></span>

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="3e814-164">使用 [wmisearcher] 类型加速器时，它会将查询字符串更改为 ManagementObjectSearcher 对象，如以下命令中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-164">When you use the [wmisearcher] type accelerator, it changes the query string into a ManagementObjectSearcher object, as shown in the following commands.</span></span>

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

<span data-ttu-id="3e814-165">此命令格式适用于任何查询。</span><span class="sxs-lookup"><span data-stu-id="3e814-165">This command format works on any query.</span></span> <span data-ttu-id="3e814-166">下面的命令获取 Win32_Bios WMI 类的 Name 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3e814-166">The following command gets the value of the Name property of the Win32_Bios WMI class.</span></span>

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

<span data-ttu-id="3e814-167">可以在单个命令中执行此操作，尽管命令更难解释。</span><span class="sxs-lookup"><span data-stu-id="3e814-167">You can perform this operation in a single command, although the command is a bit more difficult to interpret.</span></span>

<span data-ttu-id="3e814-168">采用这种格式时，请使用 [wmisearcher] 类型加速器将 WQL 查询字符串转换为 ManagementObjectSearcher，然后对对象调用 Get 方法，只需要在单个命令中调用 Get 方法。</span><span class="sxs-lookup"><span data-stu-id="3e814-168">In this format, you use the [wmisearcher] type accelerator to cast the WQL query string to a ManagementObjectSearcher, and then call the Get method on the object -- all in a single command.</span></span> <span data-ttu-id="3e814-169">圆括号 ( # A1，用来在调用方法之前，将强制转换字符串 direct Windows PowerShell 强制转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="3e814-169">The parentheses () that enclose the casted string direct Windows PowerShell to cast the string before calling the method.</span></span>

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a><span data-ttu-id="3e814-170">使用基本 WQL WHERE 语句</span><span class="sxs-lookup"><span data-stu-id="3e814-170">USING THE BASIC WQL WHERE STATEMENT</span></span>

<span data-ttu-id="3e814-171">Where 语句为 Select 语句返回的数据建立条件。</span><span class="sxs-lookup"><span data-stu-id="3e814-171">A Where statement establishes conditions for the data that a Select statement returns.</span></span>

<span data-ttu-id="3e814-172">Where 语句具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="3e814-172">The Where statement has the following format:</span></span>

```
where <property> <operator> <value>
```

<span data-ttu-id="3e814-173">例如：</span><span class="sxs-lookup"><span data-stu-id="3e814-173">For example:</span></span>

```
where Name = 'Notepad.exe'
```

<span data-ttu-id="3e814-174">Where 语句用于 Select 语句，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-174">The Where statement is used with the Select statement, as shown in the following example.</span></span>

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

<span data-ttu-id="3e814-175">使用 Where 语句时，属性名称和值必须准确。</span><span class="sxs-lookup"><span data-stu-id="3e814-175">When using the Where statement, the property name and value must be accurate.</span></span>

<span data-ttu-id="3e814-176">例如，以下命令将获取本地计算机上的记事本进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-176">For example, the following command gets the Notepad processes on the local computer.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

<span data-ttu-id="3e814-177">但是，下面的命令将失败，因为进程名称包含 ".exe" 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="3e814-177">However, the following command fails, because the process name includes the ".exe" file name extension.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a><span data-ttu-id="3e814-178">WHERE 语句比较运算符</span><span class="sxs-lookup"><span data-stu-id="3e814-178">WHERE STATEMENT COMPARISON OPERATORS</span></span>

<span data-ttu-id="3e814-179">以下运算符在 WQL Where 语句中有效。</span><span class="sxs-lookup"><span data-stu-id="3e814-179">The following operators are valid in a WQL Where statement.</span></span>

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

<span data-ttu-id="3e814-180">还有其他运算符，但这些运算符用于进行比较。</span><span class="sxs-lookup"><span data-stu-id="3e814-180">There are other operators, but these are the ones used for making comparisons.</span></span>

<span data-ttu-id="3e814-181">例如，下面的查询从 Win32_Process 类中的进程选择进程优先级大于或等于11的进程的名称和优先级属性。</span><span class="sxs-lookup"><span data-stu-id="3e814-181">For example, the following query selects the Name and Priority properties from processes in the Win32_Process class where the process priority is greater than or equal to 11.</span></span> <span data-ttu-id="3e814-182">Get-WmiObject cmdlet 将运行查询。</span><span class="sxs-lookup"><span data-stu-id="3e814-182">The Get-WmiObject cmdlet runs the query.</span></span>

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a><span data-ttu-id="3e814-183">在 FILTER 参数中使用 WQL 运算符</span><span class="sxs-lookup"><span data-stu-id="3e814-183">USING THE WQL OPERATORS IN THE FILTER PARAMETER</span></span>

<span data-ttu-id="3e814-184">WQL 运算符还可用于 Get-WmiObject 或 Get-CimInstance cmdlet 的 Filter 参数的值，以及这些 cmdlet 的查询参数值中。</span><span class="sxs-lookup"><span data-stu-id="3e814-184">The WQL operators can also be used in the value of the Filter parameter of the Get-WmiObject or Get-CimInstance cmdlets, as well as in the value of the Query parameters of these cmdlets.</span></span>

<span data-ttu-id="3e814-185">例如，以下命令将获取 ProcessID 值大于1004的最后五个进程的 Name 和 ProcessID 属性。</span><span class="sxs-lookup"><span data-stu-id="3e814-185">For example, the following command gets the Name and ProcessID properties of the last five processes that have ProcessID values greater than 1004.</span></span> <span data-ttu-id="3e814-186">该命令使用筛选器参数来指定 ProcessID 条件。</span><span class="sxs-lookup"><span data-stu-id="3e814-186">The command uses the Filter parameter to specify the ProcessID condition.</span></span>

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a><span data-ttu-id="3e814-187">使用 LIKE 运算符</span><span class="sxs-lookup"><span data-stu-id="3e814-187">USING THE LIKE OPERATOR</span></span>

<span data-ttu-id="3e814-188">Like 运算符使你可以使用通配符来筛选 WQL 查询的结果。</span><span class="sxs-lookup"><span data-stu-id="3e814-188">The Like operator lets you use wildcard characters to filter the results of a WQL query.</span></span>

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

<span data-ttu-id="3e814-189">当使用 Like 运算符时，如果不使用任何通配符或范围运算符，则该运算符的行为类似于相等运算符 (=) 并仅在它们与模式完全匹配时才返回对象。</span><span class="sxs-lookup"><span data-stu-id="3e814-189">When the Like operator is used without any wildcard characters or range operators, it behaves like the equality operator (=) and returns objects only when they are an exact match for the pattern.</span></span>

<span data-ttu-id="3e814-190">可以将范围操作与百分号通配符组合在一起，以创建简单但功能强大的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3e814-190">You can combine the range operation with the percent wildcard character to create simple, yet powerful filters.</span></span>

### <a name="like-operator-examples"></a><span data-ttu-id="3e814-191">LIKE 运算符示例</span><span class="sxs-lookup"><span data-stu-id="3e814-191">LIKE OPERATOR EXAMPLES</span></span>

#### <a name="example-1-range"></a><span data-ttu-id="3e814-192">示例1： [ \<range> ]</span><span class="sxs-lookup"><span data-stu-id="3e814-192">EXAMPLE 1: [\<range>]</span></span>

<span data-ttu-id="3e814-193">以下命令将启动 "记事本"，然后搜索 Win32_Process 类的实例，该实例的名称以字母 "H" 和 "N" （ (不区分大小写的) ）开头。</span><span class="sxs-lookup"><span data-stu-id="3e814-193">The following commands start Notepad and then search for an instance of the Win32_Process class that has a name that starts with a letter between "H" and "N" (case-insensitive).</span></span>

<span data-ttu-id="3e814-194">查询应返回从 Hotpad.exe 到 Notepad.exe 的任何进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-194">The query should return any process from Hotpad.exe through Notepad.exe.</span></span>

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a><span data-ttu-id="3e814-195">示例2： [ \<range> ] 和%</span><span class="sxs-lookup"><span data-stu-id="3e814-195">EXAMPLE 2: [\<range>] and %</span></span>

<span data-ttu-id="3e814-196">以下命令选择名称以字母开头且不区分大小写的所有进程 (不区分大小写的) 后跟任何组合中的零个或多个字母。</span><span class="sxs-lookup"><span data-stu-id="3e814-196">The following commands select all process that have a name that begins with a letter between A and P (case-insensitive) followed by zero or more letters in any combination.</span></span>

<span data-ttu-id="3e814-197">Get-WmiObject cmdlet 运行查询，Select-Object cmdlet 获取名称和 ProcessID 属性，Sort-Object cmdlet 按名称的字母顺序对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="3e814-197">The Get-WmiObject cmdlet runs the query, the Select-Object cmdlet gets the Name and ProcessID properties, and the Sort-Object cmdlet sorts the results in alphabetical order by name.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a><span data-ttu-id="3e814-198">示例3：不在范围 (^) </span><span class="sxs-lookup"><span data-stu-id="3e814-198">EXAMPLE 3: Not in Range (^)</span></span>

<span data-ttu-id="3e814-199">以下命令将获取名称不以以下任何字母开头的进程： A、S、W、P、R、C、U、N</span><span class="sxs-lookup"><span data-stu-id="3e814-199">The following command gets processes whose names do not begin with any of the following letters: A, S, W, P, R, C, U, N</span></span>

<span data-ttu-id="3e814-200">并遵循零个或多个字母。</span><span class="sxs-lookup"><span data-stu-id="3e814-200">and followed zero or more letters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a><span data-ttu-id="3e814-201">示例4：任何字符--或 none (% ) </span><span class="sxs-lookup"><span data-stu-id="3e814-201">EXAMPLE 4: Any characters -- or none (%)</span></span>

<span data-ttu-id="3e814-202">以下命令将获取名称以 "calc" 开头的进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-202">The following commands get processes that have names that begin with "calc".</span></span>
<span data-ttu-id="3e814-203">WQL 中的% 符号等效于 \* 正则表达式中的星号 () 符号。</span><span class="sxs-lookup"><span data-stu-id="3e814-203">The % symbol in WQL is equivalent to the asterisk (\*) symbol in regular expressions.</span></span>

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a><span data-ttu-id="3e814-204">示例5：一个字符 (_) </span><span class="sxs-lookup"><span data-stu-id="3e814-204">EXAMPLE 5: One character (_)</span></span>

<span data-ttu-id="3e814-205">以下命令将获取名称具有以下模式的进程： "c_lc.exe"，其中的下划线字符表示任意一个字符。</span><span class="sxs-lookup"><span data-stu-id="3e814-205">The following commands get processes that have names that have the following pattern, "c_lc.exe" where the underscore character represents any one character.</span></span> <span data-ttu-id="3e814-206">此模式将 calc.exe 中的任何名称与 czlc.exe 或 c9lc.exe 匹配，但不匹配 "c" 和 "l" 之间用多个字符分隔的名称。</span><span class="sxs-lookup"><span data-stu-id="3e814-206">This pattern matches any name from calc.exe through czlc.exe, or c9lc.exe, but does not match names in which the "c" and "l" are separated by more than one character.</span></span>

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a><span data-ttu-id="3e814-207">示例6：完全匹配</span><span class="sxs-lookup"><span data-stu-id="3e814-207">EXAMPLE 6: Exact match</span></span>

<span data-ttu-id="3e814-208">以下命令将获取名为 WLIDSVC.exe 的进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-208">The following commands get processes named WLIDSVC.exe.</span></span> <span data-ttu-id="3e814-209">即使查询使用 Like 关键字，它也需要完全匹配，因为该值不包含任何通配符。</span><span class="sxs-lookup"><span data-stu-id="3e814-209">Even though the query uses the Like keyword, it requires an exact match, because the value does not include any wildcard characters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a><span data-ttu-id="3e814-210">使用 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="3e814-210">USING THE OR OPERATOR</span></span>

<span data-ttu-id="3e814-211">若要指定多个独立条件，请使用或关键字。</span><span class="sxs-lookup"><span data-stu-id="3e814-211">To specify multiple independent conditions, use the Or keyword.</span></span> <span data-ttu-id="3e814-212">或关键字显示在 Where 子句中。</span><span class="sxs-lookup"><span data-stu-id="3e814-212">The Or keyword appears in the Where clause.</span></span> <span data-ttu-id="3e814-213">它对两个 (或多个) 条件执行包含或运算，并返回满足任何条件的项。</span><span class="sxs-lookup"><span data-stu-id="3e814-213">It performs an inclusive OR operation on two (or more) conditions and returns items that meet any of the conditions.</span></span>

<span data-ttu-id="3e814-214">Or 运算符具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="3e814-214">The Or operator has the following format:</span></span>

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

<span data-ttu-id="3e814-215">例如，下面的命令获取 Win32_Process WMI 类的所有实例，但仅当进程名称为 winword.exe 或 excel.exe 时才返回它们。</span><span class="sxs-lookup"><span data-stu-id="3e814-215">For example, the following commands get all instances of the Win32_Process WMI class but returns them only if the process name is winword.exe or excel.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

<span data-ttu-id="3e814-216">或语句可用于两个以上的条件。</span><span class="sxs-lookup"><span data-stu-id="3e814-216">The Or statement can be used with more than two conditions.</span></span> <span data-ttu-id="3e814-217">在下面的查询中，或语句获取 Winword.exe、Excel.exe 或 Powershell.exe。</span><span class="sxs-lookup"><span data-stu-id="3e814-217">In the following query, the Or statement gets Winword.exe, Excel.exe, or Powershell.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a><span data-ttu-id="3e814-218">使用 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="3e814-218">USING THE AND OPERATOR</span></span>

<span data-ttu-id="3e814-219">若要指定多个相关条件，请使用和关键字。</span><span class="sxs-lookup"><span data-stu-id="3e814-219">To specify multiple related conditions, use the And keyword.</span></span> <span data-ttu-id="3e814-220">和关键字显示在 Where 子句中。</span><span class="sxs-lookup"><span data-stu-id="3e814-220">The And keyword appears in the Where clause.</span></span> <span data-ttu-id="3e814-221">它将返回满足所有条件的项。</span><span class="sxs-lookup"><span data-stu-id="3e814-221">It returns items that meet all of the conditions.</span></span>

<span data-ttu-id="3e814-222">和运算符具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="3e814-222">The And operator has the following format:</span></span>

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

<span data-ttu-id="3e814-223">例如，以下命令将获取名称为 "Winword.exe"，进程 ID 为6512的进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-223">For example, the following commands get processes that have a name of "Winword.exe" and the process ID of 6512.</span></span>

<span data-ttu-id="3e814-224">请注意，这些命令使用 Get-CimInstance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e814-224">Note that the commands use the Get-CimInstance cmdlet.</span></span>

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

<span data-ttu-id="3e814-225">所有运算符，包括 Like 运算符都适用于或和和运算符。</span><span class="sxs-lookup"><span data-stu-id="3e814-225">All operators, including the Like operators are valid with the Or and And operators.</span></span> <span data-ttu-id="3e814-226">而且，你可以在单个查询中将 Or 和 And 运算符与指示 Windows PowerShell 首先处理的子句的括号组合在一起。</span><span class="sxs-lookup"><span data-stu-id="3e814-226">And, you can combine the Or and And operators in a single query with parentheses that tell Windows PowerShell which clauses to process first.</span></span>

<span data-ttu-id="3e814-227">此命令使用 Windows PowerShell 继续符 (") 将命令分为两行。</span><span class="sxs-lookup"><span data-stu-id="3e814-227">This command uses the Windows PowerShell continuation character (\`) divide the command into two lines.</span></span>

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a><span data-ttu-id="3e814-228">搜索 NULL 值</span><span class="sxs-lookup"><span data-stu-id="3e814-228">SEARCHING FOR NULL VALUES</span></span>

<span data-ttu-id="3e814-229">在 WMI 中搜索 null 值非常困难，因为这可能导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="3e814-229">Searching for null values in WMI is challenging, because it can lead to unpredictable results.</span></span> <span data-ttu-id="3e814-230">Null 不为零，且不等同于或为空字符串。</span><span class="sxs-lookup"><span data-stu-id="3e814-230">Null is not zero and it is not equivalent or to an empty string.</span></span> <span data-ttu-id="3e814-231">一些 WMI 类属性已初始化，而其他属性不会进行初始化，因此对于所有属性，搜索 null 可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="3e814-231">Some WMI class properties are initialized and others are not, so a search for null might not work for all properties.</span></span>

<span data-ttu-id="3e814-232">若要搜索 null 值，请使用值为 "null" 的 Is 运算符。</span><span class="sxs-lookup"><span data-stu-id="3e814-232">To search for null values, use the Is operator with a value of "null".</span></span>

<span data-ttu-id="3e814-233">例如，以下命令将获取 IntallDate 属性的值为 null 的进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-233">For example, the following commands get processes that have a null value for the IntallDate property.</span></span> <span data-ttu-id="3e814-234">命令返回多个进程。</span><span class="sxs-lookup"><span data-stu-id="3e814-234">The commands return many processes.</span></span>

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="3e814-235">相反，下面的命令获取 Description 属性的 null 值的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3e814-235">In contrast, the following command, gets user accounts that have a null value for the Description property.</span></span> <span data-ttu-id="3e814-236">此命令不会返回任何用户帐户，即使大多数用户帐户没有 "说明" 属性的任何值。</span><span class="sxs-lookup"><span data-stu-id="3e814-236">This command does not return any user accounts, even though most user accounts do not have any value for the Description property.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="3e814-237">若要查找 "Description" 属性没有值的用户帐户，请使用相等运算符获取空字符串。</span><span class="sxs-lookup"><span data-stu-id="3e814-237">To find the user accounts that have no value for the Description property, use the equality operator to get an empty string.</span></span> <span data-ttu-id="3e814-238">若要表示空字符串，请使用两个连续的单引号。</span><span class="sxs-lookup"><span data-stu-id="3e814-238">To represent the empty string, use two consecutive single quotation marks.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a><span data-ttu-id="3e814-239">使用 TRUE 或 FALSE</span><span class="sxs-lookup"><span data-stu-id="3e814-239">USING TRUE OR FALSE</span></span>

<span data-ttu-id="3e814-240">若要在 WMI 对象的属性中获取布尔值，请使用 True 和 False。</span><span class="sxs-lookup"><span data-stu-id="3e814-240">To get Boolean values in the properties of WMI objects, use True and False.</span></span>
<span data-ttu-id="3e814-241">不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="3e814-241">They are not case sensitive.</span></span>

<span data-ttu-id="3e814-242">以下 WQL 查询仅返回已加入域的计算机中的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3e814-242">The following WQL query returns only local user accounts from a domain joined computer.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

<span data-ttu-id="3e814-243">若要查找域帐户，请使用值 False，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-243">To find domain accounts, use a value of False, as shown in the following example.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a><span data-ttu-id="3e814-244">使用转义符</span><span class="sxs-lookup"><span data-stu-id="3e814-244">USING THE ESCAPE CHARACTER</span></span>

<span data-ttu-id="3e814-245">WQL 使用反斜杠 (\) 作为其转义字符。</span><span class="sxs-lookup"><span data-stu-id="3e814-245">WQL uses the backslash (\) as its escape character.</span></span> <span data-ttu-id="3e814-246">这不同于 Windows PowerShell，后者使用反撇号字符 (") 。</span><span class="sxs-lookup"><span data-stu-id="3e814-246">This is different from Windows PowerShell, which uses the backtick character (\`).</span></span>

<span data-ttu-id="3e814-247">引号以及用引号引起来的字符通常需要转义，以便不会被误解。</span><span class="sxs-lookup"><span data-stu-id="3e814-247">Quotation marks, and the characters used for quotation marks, often need to be escaped so that they are not misinterpreted.</span></span>

<span data-ttu-id="3e814-248">若要查找名称中包含单引号的用户，请使用反斜杠来转义单引号，如以下命令中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-248">To find a user whose name includes a single quotation mark, use a backslash to escape the single quotation mark, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

<span data-ttu-id="3e814-249">在某些情况下，还需要转义反斜杠。</span><span class="sxs-lookup"><span data-stu-id="3e814-249">In some case, the backslash also needs to be escaped.</span></span> <span data-ttu-id="3e814-250">例如，以下命令将生成无效的查询错误，因为标题值中有反斜杠。</span><span class="sxs-lookup"><span data-stu-id="3e814-250">For example, the following commands generate an Invalid Query error due to the backslash in the Caption value.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

<span data-ttu-id="3e814-251">若要对反斜杠进行转义，请使用第二个反斜杠字符，如下面的命令中所示。</span><span class="sxs-lookup"><span data-stu-id="3e814-251">To escape the backslash, use a second backslash character, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a><span data-ttu-id="3e814-252">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e814-252">SEE ALSO</span></span>

[<span data-ttu-id="3e814-253">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="3e814-253">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="3e814-254">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="3e814-254">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="3e814-255">about_WMI</span><span class="sxs-lookup"><span data-stu-id="3e814-255">about_WMI</span></span>](about_WMI.md)

[<span data-ttu-id="3e814-256">about_WMI_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e814-256">about_WMI_Cmdlets</span></span>](about_WMI_Cmdlets.md)
