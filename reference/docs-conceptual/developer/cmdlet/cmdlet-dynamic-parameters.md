---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 动态参数
description: Cmdlet 动态参数
ms.openlocfilehash: b44dda2354e8b689e419c7bf4deefadfc4edcb07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653427"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="335e9-103">Cmdlet 动态参数</span><span class="sxs-lookup"><span data-stu-id="335e9-103">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="335e9-104">Cmdlet 可以定义在特殊条件下可用于用户的参数，如其他参数的参数是特定值时。</span><span class="sxs-lookup"><span data-stu-id="335e9-104">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="335e9-105">这些参数是在运行时添加的，它们被称为动态参数，因为它们仅在需要时才添加。</span><span class="sxs-lookup"><span data-stu-id="335e9-105">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="335e9-106">例如，你可以设计仅在指定了特定交换机参数时添加多个参数的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="335e9-106">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="335e9-107">提供程序和 PowerShell 函数也可以定义动态参数。</span><span class="sxs-lookup"><span data-stu-id="335e9-107">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="335e9-108">PowerShell cmdlet 中的动态参数</span><span class="sxs-lookup"><span data-stu-id="335e9-108">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="335e9-109">PowerShell 在其提供程序 cmdlet 中使用动态参数。</span><span class="sxs-lookup"><span data-stu-id="335e9-109">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="335e9-110">例如， `Get-Item` `Get-ChildItem` 当 **Path** 参数指定了 **证书** 提供程序路径时，和 Cmdlet 会在运行时添加 **CodeSigningCert** 参数。</span><span class="sxs-lookup"><span data-stu-id="335e9-110">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="335e9-111">如果 **path** 参数指定了不同提供程序的路径，则 **CodeSigningCert** 参数不可用。</span><span class="sxs-lookup"><span data-stu-id="335e9-111">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="335e9-112">下面的示例演示如何在运行时在运行时添加 **CodeSigningCert** 参数 `Get-Item` 。</span><span class="sxs-lookup"><span data-stu-id="335e9-112">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="335e9-113">在此示例中，PowerShell 运行时添加了参数，且 cmdlet 成功。</span><span class="sxs-lookup"><span data-stu-id="335e9-113">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="335e9-114">在此示例中，指定了一个 **FileSystem** 驱动器并返回错误。</span><span class="sxs-lookup"><span data-stu-id="335e9-114">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="335e9-115">错误消息指示找不到 **CodeSigningCert** 参数。</span><span class="sxs-lookup"><span data-stu-id="335e9-115">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="335e9-116">支持动态参数</span><span class="sxs-lookup"><span data-stu-id="335e9-116">Support for dynamic parameters</span></span>

<span data-ttu-id="335e9-117">若要支持动态参数，必须在 cmdlet 代码中包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="335e9-117">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="335e9-118">接口</span><span class="sxs-lookup"><span data-stu-id="335e9-118">Interface</span></span>

<span data-ttu-id="335e9-119">[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters)）。</span><span class="sxs-lookup"><span data-stu-id="335e9-119">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="335e9-120">此接口提供检索动态参数的方法。</span><span class="sxs-lookup"><span data-stu-id="335e9-120">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="335e9-121">例如：</span><span class="sxs-lookup"><span data-stu-id="335e9-121">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="335e9-122">方法</span><span class="sxs-lookup"><span data-stu-id="335e9-122">Method</span></span>

<span data-ttu-id="335e9-123">[IDynamicParameters. GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)。</span><span class="sxs-lookup"><span data-stu-id="335e9-123">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="335e9-124">此方法检索包含动态参数定义的对象。</span><span class="sxs-lookup"><span data-stu-id="335e9-124">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="335e9-125">例如：</span><span class="sxs-lookup"><span data-stu-id="335e9-125">For example:</span></span>

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a><span data-ttu-id="335e9-126">类</span><span class="sxs-lookup"><span data-stu-id="335e9-126">Class</span></span>

<span data-ttu-id="335e9-127">定义要添加的动态参数的类。</span><span class="sxs-lookup"><span data-stu-id="335e9-127">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="335e9-128">此类必须包括每个参数的 **参数** 属性以及 cmdlet 所需的任何可选 **别名** 和 **验证** 属性。</span><span class="sxs-lookup"><span data-stu-id="335e9-128">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="335e9-129">例如：</span><span class="sxs-lookup"><span data-stu-id="335e9-129">For example:</span></span>

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

<span data-ttu-id="335e9-130">有关支持动态参数的 cmdlet 的完整示例，请参阅 [如何声明动态参数](./how-to-declare-dynamic-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="335e9-130">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="335e9-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="335e9-131">See also</span></span>

[<span data-ttu-id="335e9-132">System.web. IDynamicParameters</span><span class="sxs-lookup"><span data-stu-id="335e9-132">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="335e9-133">IDynamicParameters. GetDynamicParameters。</span><span class="sxs-lookup"><span data-stu-id="335e9-133">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="335e9-134">如何声明动态参数</span><span class="sxs-lookup"><span data-stu-id="335e9-134">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="335e9-135">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="335e9-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
