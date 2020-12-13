---
ms.date: 01/15/2019
ms.topic: reference
title: 如何编写简单的 Cmdlet
description: 如何编写简单的 Cmdlet
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646488"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="e495a-103">如何编写 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e495a-103">How to write a cmdlet</span></span>

<span data-ttu-id="e495a-104">本文介绍如何编写 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e495a-104">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="e495a-105">`Send-Greeting`Cmdlet 使用单个用户名作为输入，然后将问候语写入该用户。</span><span class="sxs-lookup"><span data-stu-id="e495a-105">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="e495a-106">尽管此 cmdlet 不会执行许多工作，但本示例演示了 cmdlet 的主要部分。</span><span class="sxs-lookup"><span data-stu-id="e495a-106">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="e495a-107">编写 cmdlet 的步骤</span><span class="sxs-lookup"><span data-stu-id="e495a-107">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="e495a-108">若要将类声明为 cmdlet，请使用 **cmdlet** 特性。</span><span class="sxs-lookup"><span data-stu-id="e495a-108">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="e495a-109">**Cmdlet** 属性指定该 cmdlet 名称的动词和名词。</span><span class="sxs-lookup"><span data-stu-id="e495a-109">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="e495a-110">有关 **Cmdlet** 特性的详细信息，请参阅 [CmdletAttribute 声明](cmdlet-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="e495a-110">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="e495a-111">指定类的名称。</span><span class="sxs-lookup"><span data-stu-id="e495a-111">Specify the name of the class.</span></span>

3. <span data-ttu-id="e495a-112">指定该 cmdlet 派生自以下任一类：</span><span class="sxs-lookup"><span data-stu-id="e495a-112">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="e495a-113">System.object。</span><span class="sxs-lookup"><span data-stu-id="e495a-113">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="e495a-114">System.web. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="e495a-114">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="e495a-115">若要定义 cmdlet 的参数，请使用 **Parameter** 特性。</span><span class="sxs-lookup"><span data-stu-id="e495a-115">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="e495a-116">在这种情况下，只指定了一个必需的参数。</span><span class="sxs-lookup"><span data-stu-id="e495a-116">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="e495a-117">有关 **参数** 属性的详细信息，请参阅 [ParameterAttribute 声明](parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="e495a-117">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="e495a-118">重写处理输入的输入处理方法。</span><span class="sxs-lookup"><span data-stu-id="e495a-118">Override the input processing method that processes the input.</span></span> <span data-ttu-id="e495a-119">在这种情况下，将重写 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法。</span><span class="sxs-lookup"><span data-stu-id="e495a-119">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="e495a-120">若要编写问候语，请使用方法 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)。</span><span class="sxs-lookup"><span data-stu-id="e495a-120">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="e495a-121">该问候语按以下格式显示：</span><span class="sxs-lookup"><span data-stu-id="e495a-121">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="e495a-122">示例</span><span class="sxs-lookup"><span data-stu-id="e495a-122">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e495a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e495a-123">See also</span></span>

[<span data-ttu-id="e495a-124">System.object。</span><span class="sxs-lookup"><span data-stu-id="e495a-124">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="e495a-125">System.web. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="e495a-125">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="e495a-126">"ProcessRecord"。</span><span class="sxs-lookup"><span data-stu-id="e495a-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="e495a-127">"WriteObject"。</span><span class="sxs-lookup"><span data-stu-id="e495a-127">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="e495a-128">CmdletAttribute 声明</span><span class="sxs-lookup"><span data-stu-id="e495a-128">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="e495a-129">ParameterAttribute 声明</span><span class="sxs-lookup"><span data-stu-id="e495a-129">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="e495a-130">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e495a-130">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
