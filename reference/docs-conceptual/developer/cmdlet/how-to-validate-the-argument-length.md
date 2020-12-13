---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数长度
description: 如何验证参数长度
ms.openlocfilehash: 460aedbe6847033f976cb7bf70b6c77ac5a3a3c9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652626"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="e3f96-103">如何验证参数长度</span><span class="sxs-lookup"><span data-stu-id="e3f96-103">How to Validate the Argument Length</span></span>

<span data-ttu-id="e3f96-104">此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查在运行 cmdlet 之前 (参数参数长度) 的字符数。</span><span class="sxs-lookup"><span data-stu-id="e3f96-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="e3f96-105">可以通过声明 ValidateLength 属性设置此验证规则。</span><span class="sxs-lookup"><span data-stu-id="e3f96-105">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="e3f96-106">有关用于定义此属性的类的详细信息，请参阅 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)。</span><span class="sxs-lookup"><span data-stu-id="e3f96-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="e3f96-107">验证参数长度</span><span class="sxs-lookup"><span data-stu-id="e3f96-107">To validate the argument length</span></span>

- <span data-ttu-id="e3f96-108">添加 Validate 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="e3f96-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="e3f96-109">此示例指定参数的长度应为0到10个字符。</span><span class="sxs-lookup"><span data-stu-id="e3f96-109">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

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

<span data-ttu-id="e3f96-110">有关如何声明此特性的详细信息，请参阅 [ValidateLength 特性声明](./validatelength-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f96-110">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3f96-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3f96-111">See Also</span></span>

[<span data-ttu-id="e3f96-112">ValidateLength 属性声明</span><span class="sxs-lookup"><span data-stu-id="e3f96-112">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="e3f96-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3f96-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
