---
title: 如何编写简单的 Cmdlet |Microsoft Docs
ms.date: 01/15/2019
ms.openlocfilehash: 2ff0b47454804c9becd6f03ac521946b9596bb8b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784055"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="3e1fa-102">如何编写 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e1fa-102">How to write a cmdlet</span></span>

<span data-ttu-id="3e1fa-103">本文介绍如何编写 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-103">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="3e1fa-104">`Send-Greeting`Cmdlet 使用单个用户名作为输入，然后将问候语写入该用户。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-104">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="3e1fa-105">尽管此 cmdlet 不会执行许多工作，但本示例演示了 cmdlet 的主要部分。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-105">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="3e1fa-106">编写 cmdlet 的步骤</span><span class="sxs-lookup"><span data-stu-id="3e1fa-106">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="3e1fa-107">若要将类声明为 cmdlet，请使用**cmdlet**特性。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-107">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="3e1fa-108">**Cmdlet**属性指定该 cmdlet 名称的动词和名词。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-108">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="3e1fa-109">有关**Cmdlet**特性的详细信息，请参阅[CmdletAttribute 声明](cmdlet-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-109">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="3e1fa-110">指定类的名称。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-110">Specify the name of the class.</span></span>

3. <span data-ttu-id="3e1fa-111">指定该 cmdlet 派生自以下任一类：</span><span class="sxs-lookup"><span data-stu-id="3e1fa-111">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="3e1fa-112">System.object。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-112">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="3e1fa-113">System.web. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="3e1fa-113">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="3e1fa-114">若要定义 cmdlet 的参数，请使用**Parameter**特性。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-114">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="3e1fa-115">在这种情况下，只指定了一个必需的参数。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-115">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="3e1fa-116">有关**参数**属性的详细信息，请参阅[ParameterAttribute 声明](parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-116">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="3e1fa-117">重写处理输入的输入处理方法。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-117">Override the input processing method that processes the input.</span></span> <span data-ttu-id="3e1fa-118">在这种情况下，将重写[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-118">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="3e1fa-119">若要编写问候语，请使用方法[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-119">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="3e1fa-120">该问候语按以下格式显示：</span><span class="sxs-lookup"><span data-stu-id="3e1fa-120">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="3e1fa-121">示例</span><span class="sxs-lookup"><span data-stu-id="3e1fa-121">Example</span></span>

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="3e1fa-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e1fa-122">See also</span></span>

[<span data-ttu-id="3e1fa-123">System.object。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-123">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="3e1fa-124">System.web. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="3e1fa-124">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="3e1fa-125">"ProcessRecord"。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-125">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="3e1fa-126">"WriteObject"。</span><span class="sxs-lookup"><span data-stu-id="3e1fa-126">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="3e1fa-127">CmdletAttribute 声明</span><span class="sxs-lookup"><span data-stu-id="3e1fa-127">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="3e1fa-128">ParameterAttribute 声明</span><span class="sxs-lookup"><span data-stu-id="3e1fa-128">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="3e1fa-129">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e1fa-129">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
