---
ms.date: 09/13/2016
ms.topic: reference
title: 如何声明动态参数
description: 如何声明动态参数
ms.openlocfilehash: 0f5a8f249b414663aa9702a908ea5c8ca24755ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667073"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="bd886-103">如何声明动态参数</span><span class="sxs-lookup"><span data-stu-id="bd886-103">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="bd886-104">此示例演示如何定义在运行时添加到 cmdlet 的动态参数。</span><span class="sxs-lookup"><span data-stu-id="bd886-104">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="bd886-105">在此示例中， `Department` 只要用户指定开关参数，就会将参数添加到 cmdlet `Employee` 。</span><span class="sxs-lookup"><span data-stu-id="bd886-105">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="bd886-106">有关动态参数的详细信息，请参阅 [Cmdlet 动态参数](./cmdlet-dynamic-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="bd886-106">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="bd886-107">定义动态参数</span><span class="sxs-lookup"><span data-stu-id="bd886-107">To define dynamic parameters</span></span>

1. <span data-ttu-id="bd886-108">在 cmdlet 类声明中，按如下所示添加 [Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) 接口。</span><span class="sxs-lookup"><span data-stu-id="bd886-108">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="bd886-109">调用 [Idynamicparameters. Getdynamicparameters \*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) 方法，该方法返回在其中定义动态参数的对象。</span><span class="sxs-lookup"><span data-stu-id="bd886-109">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="bd886-110">在此示例中，当指定了参数时，将调用方法 `Employee` 。</span><span class="sxs-lookup"><span data-stu-id="bd886-110">In this example, the method is called when the `Employee` parameter is specified.</span></span>

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

3. <span data-ttu-id="bd886-111">声明一个定义要添加的动态参数的类。</span><span class="sxs-lookup"><span data-stu-id="bd886-111">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="bd886-112">你可以使用用于声明静态 cmdlet 参数的属性来声明动态参数。</span><span class="sxs-lookup"><span data-stu-id="bd886-112">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

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

## <a name="example"></a><span data-ttu-id="bd886-113">示例</span><span class="sxs-lookup"><span data-stu-id="bd886-113">Example</span></span>

<span data-ttu-id="bd886-114">在此示例中， `Department` 只要用户指定参数，就会添加参数 `Employee` 。</span><span class="sxs-lookup"><span data-stu-id="bd886-114">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="bd886-115">`Department`参数是一个可选参数，ValidateSet 属性用于指定允许的参数。</span><span class="sxs-lookup"><span data-stu-id="bd886-115">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
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

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
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
}
```

## <a name="see-also"></a><span data-ttu-id="bd886-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd886-116">See Also</span></span>

[<span data-ttu-id="bd886-117">System.web. Runtimedefinedparameterdictionary</span><span class="sxs-lookup"><span data-stu-id="bd886-117">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="bd886-118">Idynamicparameters. Getdynamicparameters \*</span><span class="sxs-lookup"><span data-stu-id="bd886-118">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="bd886-119">Cmdlet 动态参数</span><span class="sxs-lookup"><span data-stu-id="bd886-119">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="bd886-120">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="bd886-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
