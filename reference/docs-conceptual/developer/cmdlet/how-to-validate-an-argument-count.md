---
title: 如何验证参数计数 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782117"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="2a1f1-102">如何验证参数计数</span><span class="sxs-lookup"><span data-stu-id="2a1f1-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="2a1f1-103">此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查参数数目 (在运行 cmdlet 之前参数接受的计数) 。</span><span class="sxs-lookup"><span data-stu-id="2a1f1-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="2a1f1-104">可以通过声明 ValidateCount 属性设置此验证规则。</span><span class="sxs-lookup"><span data-stu-id="2a1f1-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="2a1f1-105">有关用于定义此属性的类的详细信息，请参阅[Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute)。</span><span class="sxs-lookup"><span data-stu-id="2a1f1-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="2a1f1-106">验证参数计数</span><span class="sxs-lookup"><span data-stu-id="2a1f1-106">To validate an argument count</span></span>

- <span data-ttu-id="2a1f1-107">添加 Validate 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="2a1f1-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="2a1f1-108">此示例指定参数将接受一个参数或多达三个参数。</span><span class="sxs-lookup"><span data-stu-id="2a1f1-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

<span data-ttu-id="2a1f1-109">有关如何声明此特性的详细信息，请参阅[ValidateCount 特性声明](./validatecount-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1f1-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a1f1-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a1f1-110">See Also</span></span>

[<span data-ttu-id="2a1f1-111">ValidateCount 属性声明</span><span class="sxs-lookup"><span data-stu-id="2a1f1-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="2a1f1-112">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2a1f1-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
