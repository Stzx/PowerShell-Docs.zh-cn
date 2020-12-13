---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数模式
description: 如何验证参数模式
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666903"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="6a45a-103">如何验证参数模式</span><span class="sxs-lookup"><span data-stu-id="6a45a-103">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="6a45a-104">此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则在运行 cmdlet 之前检查参数参数的字符模式。</span><span class="sxs-lookup"><span data-stu-id="6a45a-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="6a45a-105">可以通过声明 ValidatePattern 属性设置此验证规则。</span><span class="sxs-lookup"><span data-stu-id="6a45a-105">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="6a45a-106">有关用于定义此属性的类的详细信息，请参阅 [Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)。</span><span class="sxs-lookup"><span data-stu-id="6a45a-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="6a45a-107">验证参数模式</span><span class="sxs-lookup"><span data-stu-id="6a45a-107">To validate an argument pattern</span></span>

- <span data-ttu-id="6a45a-108">添加 Validate 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6a45a-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="6a45a-109">此示例指定四位数的模式，其中每个数字的值都为0到9。</span><span class="sxs-lookup"><span data-stu-id="6a45a-109">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

<span data-ttu-id="6a45a-110">有关如何声明此特性的详细信息，请参阅 [ValidatePattern 特性声明](./validatepattern-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="6a45a-110">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a45a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a45a-111">See Also</span></span>

[<span data-ttu-id="6a45a-112">ValidatePattern 属性声明</span><span class="sxs-lookup"><span data-stu-id="6a45a-112">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="6a45a-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6a45a-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
