---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数范围
description: 如何验证参数范围
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666920"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="41e73-103">如何验证参数范围</span><span class="sxs-lookup"><span data-stu-id="41e73-103">How to Validate an Argument Range</span></span>

<span data-ttu-id="41e73-104">此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则在运行 cmdlet 之前检查参数参数的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="41e73-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="41e73-105">可以通过声明 ValidateRange 属性设置此验证规则。</span><span class="sxs-lookup"><span data-stu-id="41e73-105">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="41e73-106">有关用于定义此属性的类的详细信息，请参阅 [Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)。</span><span class="sxs-lookup"><span data-stu-id="41e73-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="41e73-107">验证参数范围</span><span class="sxs-lookup"><span data-stu-id="41e73-107">To validate an argument range</span></span>

- <span data-ttu-id="41e73-108">添加 ValidateRange 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="41e73-108">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="41e73-109">此示例指定参数的范围为0到 5 `InputData` 。</span><span class="sxs-lookup"><span data-stu-id="41e73-109">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

<span data-ttu-id="41e73-110">有关如何声明此特性的详细信息，请参阅 [ValidateRange 特性声明](./validaterange-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="41e73-110">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41e73-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41e73-111">See Also</span></span>

[<span data-ttu-id="41e73-112">ValidateRange 属性声明</span><span class="sxs-lookup"><span data-stu-id="41e73-112">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="41e73-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="41e73-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
