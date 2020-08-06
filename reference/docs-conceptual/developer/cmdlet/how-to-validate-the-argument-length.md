---
title: 如何验证参数长度 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784072"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="faa2f-102">如何验证参数长度</span><span class="sxs-lookup"><span data-stu-id="faa2f-102">How to Validate the Argument Length</span></span>

<span data-ttu-id="faa2f-103">此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查在运行 cmdlet 之前 (参数参数长度) 的字符数。</span><span class="sxs-lookup"><span data-stu-id="faa2f-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="faa2f-104">可以通过声明 ValidateLength 属性设置此验证规则。</span><span class="sxs-lookup"><span data-stu-id="faa2f-104">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="faa2f-105">有关用于定义此属性的类的详细信息，请参阅[Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)。</span><span class="sxs-lookup"><span data-stu-id="faa2f-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="faa2f-106">验证参数长度</span><span class="sxs-lookup"><span data-stu-id="faa2f-106">To validate the argument length</span></span>

- <span data-ttu-id="faa2f-107">添加 Validate 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="faa2f-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="faa2f-108">此示例指定参数的长度应为0到10个字符。</span><span class="sxs-lookup"><span data-stu-id="faa2f-108">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="faa2f-109">有关如何声明此特性的详细信息，请参阅[ValidateLength 特性声明](./validatelength-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="faa2f-109">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="faa2f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faa2f-110">See Also</span></span>

[<span data-ttu-id="faa2f-111">ValidateLength 属性声明</span><span class="sxs-lookup"><span data-stu-id="faa2f-111">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="faa2f-112">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="faa2f-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
