---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数集
description: 如何验证参数集
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650366"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="c34ba-103">如何验证参数集</span><span class="sxs-lookup"><span data-stu-id="c34ba-103">How to Validate an Argument Set</span></span>

<span data-ttu-id="c34ba-104">此示例演示如何在运行 cmdlet 之前指定 Windows PowerShell 运行时可用于检查参数参数的验证规则。</span><span class="sxs-lookup"><span data-stu-id="c34ba-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="c34ba-105">此验证规则为参数参数提供了一组有效值。</span><span class="sxs-lookup"><span data-stu-id="c34ba-105">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="c34ba-106">有关用于定义此属性的类的详细信息，请参阅 [Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)。</span><span class="sxs-lookup"><span data-stu-id="c34ba-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="c34ba-107">验证参数集</span><span class="sxs-lookup"><span data-stu-id="c34ba-107">To validate an argument set</span></span>

- <span data-ttu-id="c34ba-108">添加 ValidateSet 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="c34ba-108">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="c34ba-109">此示例为参数指定了三个可能的值集 `UserName` 。</span><span class="sxs-lookup"><span data-stu-id="c34ba-109">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="c34ba-110">有关如何声明此特性的详细信息，请参阅 [ValidateSet 特性声明](./validateset-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="c34ba-110">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c34ba-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c34ba-111">See Also</span></span>

[<span data-ttu-id="c34ba-112">System.web. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="c34ba-112">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="c34ba-113">ValidateSet 属性声明</span><span class="sxs-lookup"><span data-stu-id="c34ba-113">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="c34ba-114">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c34ba-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
