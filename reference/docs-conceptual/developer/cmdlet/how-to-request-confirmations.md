---
title: 如何请求确认 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ebe928724f1b750afc11c1e3c1207375f4ec8e42
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784089"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="2275a-102">如何请求确认</span><span class="sxs-lookup"><span data-stu-id="2275a-102">How to Request Confirmations</span></span>

<span data-ttu-id="2275a-103">此示例演示如何调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)和[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法，以便在执行操作之前请求从用户确认的确认请求的方法的用户确认。</span><span class="sxs-lookup"><span data-stu-id="2275a-103">This example shows how to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2275a-104">有关 Windows PowerShell 如何处理这些请求的详细信息，请参阅[请求确认](./requesting-confirmation-from-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="2275a-104">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="2275a-105">请求确认</span><span class="sxs-lookup"><span data-stu-id="2275a-105">To request confirmation</span></span>

1. <span data-ttu-id="2275a-106">确保 `SupportsShouldProcess` 将 Cmdlet 特性的参数设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="2275a-106">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="2275a-107">函数 (这是 CmdletBinding 属性的参数。 ) </span><span class="sxs-lookup"><span data-stu-id="2275a-107">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="2275a-108">将 `Force` 参数添加到 cmdlet，以使用户能够覆盖确认请求。</span><span class="sxs-lookup"><span data-stu-id="2275a-108">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="2275a-109">添加一 `if` 条语句，该语句使用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法的返回值来确定是否调用了[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的调用程序。）。</span><span class="sxs-lookup"><span data-stu-id="2275a-109">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="2275a-110">添加第二个 `if` 语句，该语句使用[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的返回值和参数的值 `Force` 来确定是否应执行该操作。</span><span class="sxs-lookup"><span data-stu-id="2275a-110">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="2275a-111">示例</span><span class="sxs-lookup"><span data-stu-id="2275a-111">Example</span></span>

<span data-ttu-id="2275a-112">在下面的代码示例中，将从[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法的重写中调用 ShouldContinue 方法，并调用[该方法中](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)的方法来调用[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的方法。</span><span class="sxs-lookup"><span data-stu-id="2275a-112">In the following code example, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="2275a-113">但是，也可以从其他输入处理方法中调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="2275a-113">However, you can also call these methods from the other input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="2275a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2275a-114">See Also</span></span>

[<span data-ttu-id="2275a-115">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2275a-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
