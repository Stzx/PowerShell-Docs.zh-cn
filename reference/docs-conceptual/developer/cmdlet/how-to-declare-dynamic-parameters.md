---
title: 如何声明动态参数 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8839aa8841bf94a9b7f8f930ca315fe0ccedb30
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784174"
---
# <a name="how-to-declare-dynamic-parameters"></a>如何声明动态参数

此示例演示如何定义在运行时添加到 cmdlet 的动态参数。 在此示例中， `Department` 只要用户指定开关参数，就会将参数添加到 cmdlet `Employee` 。 有关动态参数的详细信息，请参阅[Cmdlet 动态参数](./cmdlet-dynamic-parameters.md)。

## <a name="to-define-dynamic-parameters"></a>定义动态参数

1. 在 cmdlet 类声明中，按如下所示添加[Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)接口。

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. 调用[Idynamicparameters. Getdynamicparameters *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)方法，该方法返回在其中定义动态参数的对象。 在此示例中，当指定了参数时，将调用方法 `Employee` 。

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

3. 声明一个定义要添加的动态参数的类。 你可以使用用于声明静态 cmdlet 参数的属性来声明动态参数。

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

## <a name="example"></a>示例

在此示例中， `Department` 只要用户指定参数，就会添加参数 `Employee` 。 `Department`参数是一个可选参数，ValidateSet 属性用于指定允许的参数。

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

## <a name="see-also"></a>另请参阅

[System.web. Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[Idynamicparameters. Getdynamicparameters *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[Cmdlet 动态参数](./cmdlet-dynamic-parameters.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
