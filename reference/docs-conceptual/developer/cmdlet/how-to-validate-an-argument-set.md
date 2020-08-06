---
title: 如何验证参数集 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateSet attribute, example
ms.openlocfilehash: 6173f1380583f5b27e2b188990a5ea041f447c57
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781998"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="238b4-102">如何验证参数集</span><span class="sxs-lookup"><span data-stu-id="238b4-102">How to Validate an Argument Set</span></span>

<span data-ttu-id="238b4-103">此示例演示如何在运行 cmdlet 之前指定 Windows PowerShell 运行时可用于检查参数参数的验证规则。</span><span class="sxs-lookup"><span data-stu-id="238b4-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="238b4-104">此验证规则为参数参数提供了一组有效值。</span><span class="sxs-lookup"><span data-stu-id="238b4-104">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="238b4-105">有关用于定义此属性的类的详细信息，请参阅[Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)。</span><span class="sxs-lookup"><span data-stu-id="238b4-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="238b4-106">验证参数集</span><span class="sxs-lookup"><span data-stu-id="238b4-106">To validate an argument set</span></span>

- <span data-ttu-id="238b4-107">添加 ValidateSet 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="238b4-107">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="238b4-108">此示例为参数指定了三个可能的值集 `UserName` 。</span><span class="sxs-lookup"><span data-stu-id="238b4-108">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

<span data-ttu-id="238b4-109">有关如何声明此特性的详细信息，请参阅[ValidateSet 特性声明](./validateset-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="238b4-109">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="238b4-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="238b4-110">See Also</span></span>

[<span data-ttu-id="238b4-111">System.web. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="238b4-111">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="238b4-112">ValidateSet 属性声明</span><span class="sxs-lookup"><span data-stu-id="238b4-112">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="238b4-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="238b4-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
