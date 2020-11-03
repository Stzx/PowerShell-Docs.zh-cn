---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198080"
---
# <span data-ttu-id="3472e-103">New-WebServiceProxy</span><span class="sxs-lookup"><span data-stu-id="3472e-103">New-WebServiceProxy</span></span>

## <span data-ttu-id="3472e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3472e-104">SYNOPSIS</span></span>
<span data-ttu-id="3472e-105">创建一个 Web 服务代理对象，用于在 PowerShell 中使用和管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3472e-105">Creates a Web service proxy object that lets you use and manage the Web service in PowerShell.</span></span>

## <span data-ttu-id="3472e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3472e-106">SYNTAX</span></span>

### <span data-ttu-id="3472e-107">NoCredentials（默认值）</span><span class="sxs-lookup"><span data-stu-id="3472e-107">NoCredentials (Default)</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### <span data-ttu-id="3472e-108">凭据</span><span class="sxs-lookup"><span data-stu-id="3472e-108">Credential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="3472e-109">UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="3472e-109">UseDefaultCredential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## <span data-ttu-id="3472e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3472e-110">DESCRIPTION</span></span>

<span data-ttu-id="3472e-111">`New-WebServiceProxy`Cmdlet 可让你在 PowerShell 中使用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3472e-111">The `New-WebServiceProxy` cmdlet lets you use a Web service in PowerShell.</span></span> <span data-ttu-id="3472e-112">Cmdlet 连接到 Web 服务，并在 PowerShell 中创建 Web 服务代理对象。</span><span class="sxs-lookup"><span data-stu-id="3472e-112">The cmdlet connects to a Web service and creates a Web service proxy object in PowerShell.</span></span> <span data-ttu-id="3472e-113">你可以使用代理对象管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3472e-113">You can use the proxy object to manage the Web service.</span></span>

<span data-ttu-id="3472e-114">Web 服务是一种基于 XML 的程序，它通过网络（特别是 Internet）来交换数据。</span><span class="sxs-lookup"><span data-stu-id="3472e-114">A Web service is an XML-based program that exchanges data over a network, especially over the Internet.</span></span> <span data-ttu-id="3472e-115">Microsoft .NET Framework 提供了将 Web 服务表示为 .NET Framework 对象的 Web 服务代理对象。</span><span class="sxs-lookup"><span data-stu-id="3472e-115">The Microsoft .NET Framework provides Web service proxy objects that represent the Web service as a .NET Framework object.</span></span>

## <span data-ttu-id="3472e-116">示例</span><span class="sxs-lookup"><span data-stu-id="3472e-116">EXAMPLES</span></span>

### <span data-ttu-id="3472e-117">示例1：创建 Web 服务的代理</span><span class="sxs-lookup"><span data-stu-id="3472e-117">Example 1: Create a proxy for a Web service</span></span>

<span data-ttu-id="3472e-118">此示例在 Windows PowerShell 中创建计算器 Web 服务的 .NET Framework 代理。</span><span class="sxs-lookup"><span data-stu-id="3472e-118">This example creates a .NET Framework proxy of the calculator Web service in Windows PowerShell.</span></span>

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### <span data-ttu-id="3472e-119">示例2：创建 Web 服务的代理并指定命名空间和类</span><span class="sxs-lookup"><span data-stu-id="3472e-119">Example 2: Create a proxy for a Web service and specify namespace and class</span></span>

<span data-ttu-id="3472e-120">此示例使用 `New-WebServiceProxy` cmdlet 创建计算器 Web 服务的 .NET Framework 代理。</span><span class="sxs-lookup"><span data-stu-id="3472e-120">This example uses the `New-WebServiceProxy` cmdlet to create a .NET Framework proxy of the calculator Web service.</span></span>

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

<span data-ttu-id="3472e-121">该命令使用 **uri** 参数指定 uri，并使用 **namespace** 和 **class** 参数指定对象的命名空间和类。</span><span class="sxs-lookup"><span data-stu-id="3472e-121">The command uses the **Uri** parameter to specify the URI and the **Namespace** and **Class** parameters to specify the namespace and class of the object.</span></span>

### <span data-ttu-id="3472e-122">示例3：显示 Web 服务代理的方法</span><span class="sxs-lookup"><span data-stu-id="3472e-122">Example 3: Display methods of a Web service proxy</span></span>

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

<span data-ttu-id="3472e-123">此示例使用 `Get-Member` cmdlet 来显示变量中 Web 服务代理对象的方法 `$calc` 。</span><span class="sxs-lookup"><span data-stu-id="3472e-123">This example uses the `Get-Member` cmdlet to display the methods of the Web service proxy object in the `$calc` variable.</span></span> <span data-ttu-id="3472e-124">在下面的示例中，我们使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="3472e-124">We uses these methods in the following example.</span></span>

<span data-ttu-id="3472e-125">请注意，代理对象 New-webserviceproxy 的 **TypeName** 反映了上一示例中指定的命名空间和类名。</span><span class="sxs-lookup"><span data-stu-id="3472e-125">Notice that the **TypeName** of the proxy object, WebServiceProxy, reflects the namespace and class names that were specified in the previous example.</span></span>

### <span data-ttu-id="3472e-126">示例4：使用 Web 服务代理</span><span class="sxs-lookup"><span data-stu-id="3472e-126">Example 4: Use a Web service proxy</span></span>

```powershell
PS> $calc.Multiply(6,7)
42
```

<span data-ttu-id="3472e-127">此示例使用存储在变量中的 Web 服务代理 `$calc` 。</span><span class="sxs-lookup"><span data-stu-id="3472e-127">This example uses the Web service proxy stored in the `$calc` variable.</span></span> <span data-ttu-id="3472e-128">该命令使用代理的 **乘法** 方法。</span><span class="sxs-lookup"><span data-stu-id="3472e-128">The command uses the **Multiply** method of the proxy.</span></span>

## <span data-ttu-id="3472e-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3472e-129">PARAMETERS</span></span>

### <span data-ttu-id="3472e-130">-Class</span><span class="sxs-lookup"><span data-stu-id="3472e-130">-Class</span></span>

<span data-ttu-id="3472e-131">指定该 cmdlet 为 Web 服务创建的代理类的名称。</span><span class="sxs-lookup"><span data-stu-id="3472e-131">Specifies a name for the proxy class that the cmdlet creates for the Web service.</span></span> <span data-ttu-id="3472e-132">此参数的值与 **Namespace** 参数一起使用，为类提供完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="3472e-132">The value of this parameter is used together with the **Namespace** parameter to provide a fully qualified name for the class.</span></span> <span data-ttu-id="3472e-133">默认值是从统一资源标识符 (URI) 生成的。</span><span class="sxs-lookup"><span data-stu-id="3472e-133">The default value is generated from the Uniform Resource Identifier (URI).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3472e-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="3472e-134">-Credential</span></span>

<span data-ttu-id="3472e-135">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3472e-135">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="3472e-136">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="3472e-136">The default is the current user.</span></span> <span data-ttu-id="3472e-137">这是使用 **UseDefaultCredential** 参数的替代方法。</span><span class="sxs-lookup"><span data-stu-id="3472e-137">This is an alternative to using the **UseDefaultCredential** parameter.</span></span>

<span data-ttu-id="3472e-138">键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="3472e-138">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3472e-139">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="3472e-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3472e-140">-Namespace</span><span class="sxs-lookup"><span data-stu-id="3472e-140">-Namespace</span></span>

<span data-ttu-id="3472e-141">指定新类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3472e-141">Specifies a namespace for the new class.</span></span>

<span data-ttu-id="3472e-142">此参数的值与 **class** 参数的值一起使用，以生成该类的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="3472e-142">The value of this parameter is used together with the value of the **Class** parameter to generate a fully qualified name for the class.</span></span> <span data-ttu-id="3472e-143">默认值为 **microsoft.powershell.commands.newwebserviceproxy.autogeneratedtypes. microsoft.powershell.commands.newwebserviceproxy.autogeneratedtypes 和** 加上从 URI 生成的类型。</span><span class="sxs-lookup"><span data-stu-id="3472e-143">The default value is **Microsoft.PowerShell.Commands.NewWebserviceProxy.AutogeneratedTypes** plus a type that is generated from the URI.</span></span>

<span data-ttu-id="3472e-144">你可以设置 **Namespace** 参数的值，以便可以访问具有相同名称的多个 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3472e-144">You can set the value of the **Namespace** parameter so that you can access multiple Web services that have the same name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3472e-145">-Uri</span><span class="sxs-lookup"><span data-stu-id="3472e-145">-Uri</span></span>

<span data-ttu-id="3472e-146">指定 Web 服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="3472e-146">Specifies the URI of the Web service.</span></span> <span data-ttu-id="3472e-147">输入 URI 或包含服务说明的文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="3472e-147">Enter a URI or the path and filename of a file that contains a service description.</span></span>

<span data-ttu-id="3472e-148">URI 必须返回 `.asmx` 页面或返回服务说明的页面。</span><span class="sxs-lookup"><span data-stu-id="3472e-148">The URI must return an `.asmx` page or to a page that returns a service description.</span></span> <span data-ttu-id="3472e-149">若要返回使用 ASP.NET 创建的 Web 服务的服务说明，请追加 "？WSDL "到 Web 服务的 URL (例如， `http://www.contoso.com/MyWebService.asmx?WSDL`) 。</span><span class="sxs-lookup"><span data-stu-id="3472e-149">To return a service description of a Web service that was created using ASP.NET, append "?WSDL" to the URL of the Web service (for example, `http://www.contoso.com/MyWebService.asmx?WSDL`).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3472e-150">-UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="3472e-150">-UseDefaultCredential</span></span>

<span data-ttu-id="3472e-151">指示此 cmdlet 使用默认凭据。</span><span class="sxs-lookup"><span data-stu-id="3472e-151">Indicates that this cmdlet uses the default credential.</span></span> <span data-ttu-id="3472e-152">此 cmdlet 将生成的代理对象中的 **UseDefaultCredential** 属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="3472e-152">This cmdlet sets the **UseDefaultCredential** property in the resulting proxy object to True.</span></span> <span data-ttu-id="3472e-153">这是使用 **Credential** 参数的替代方法。</span><span class="sxs-lookup"><span data-stu-id="3472e-153">This is an alternative to using the **Credential** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3472e-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3472e-154">CommonParameters</span></span>

<span data-ttu-id="3472e-155">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3472e-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3472e-156">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3472e-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3472e-157">输入</span><span class="sxs-lookup"><span data-stu-id="3472e-157">INPUTS</span></span>

### <span data-ttu-id="3472e-158">无</span><span class="sxs-lookup"><span data-stu-id="3472e-158">None</span></span>

<span data-ttu-id="3472e-159">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3472e-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3472e-160">输出</span><span class="sxs-lookup"><span data-stu-id="3472e-160">OUTPUTS</span></span>

### <span data-ttu-id="3472e-161">Web 服务代理对象</span><span class="sxs-lookup"><span data-stu-id="3472e-161">A Web service proxy object</span></span>

<span data-ttu-id="3472e-162">此 cmdlet 将返回一个 Web 服务代理对象。</span><span class="sxs-lookup"><span data-stu-id="3472e-162">This cmdlet returns a Web service proxy object.</span></span> <span data-ttu-id="3472e-163">该对象的命名空间和类由该命令的参数确定。</span><span class="sxs-lookup"><span data-stu-id="3472e-163">The namespace and class of the object are determined by the parameters of the command.</span></span> <span data-ttu-id="3472e-164">默认值是从输入 URI 生成的。</span><span class="sxs-lookup"><span data-stu-id="3472e-164">The default is generated from the input URI.</span></span>

## <span data-ttu-id="3472e-165">注释</span><span class="sxs-lookup"><span data-stu-id="3472e-165">NOTES</span></span>

<span data-ttu-id="3472e-166">`New-WebServiceProxy` 使用 **系统 .net** node.js 类加载指定的 Web services。</span><span class="sxs-lookup"><span data-stu-id="3472e-166">`New-WebServiceProxy` uses the **System.Net.WebClient** class to load the specified Web service.</span></span>

## <span data-ttu-id="3472e-167">相关链接</span><span class="sxs-lookup"><span data-stu-id="3472e-167">RELATED LINKS</span></span>

[<span data-ttu-id="3472e-168">New-Service</span><span class="sxs-lookup"><span data-stu-id="3472e-168">New-Service</span></span>](New-Service.md)
