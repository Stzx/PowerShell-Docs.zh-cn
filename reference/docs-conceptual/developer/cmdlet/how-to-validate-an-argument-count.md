---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数计数
description: 如何验证参数计数
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666937"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="86688-103">如何验证参数计数</span><span class="sxs-lookup"><span data-stu-id="86688-103">How to Validate an Argument Count</span></span>

<span data-ttu-id="86688-104">此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查参数数目 (在运行 cmdlet 之前参数接受的计数) 。</span><span class="sxs-lookup"><span data-stu-id="86688-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="86688-105">可以通过声明 ValidateCount 属性设置此验证规则。</span><span class="sxs-lookup"><span data-stu-id="86688-105">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="86688-106">有关用于定义此属性的类的详细信息，请参阅 [Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute)。</span><span class="sxs-lookup"><span data-stu-id="86688-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="86688-107">验证参数计数</span><span class="sxs-lookup"><span data-stu-id="86688-107">To validate an argument count</span></span>

- <span data-ttu-id="86688-108">添加 Validate 特性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="86688-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="86688-109">此示例指定参数将接受一个参数或多达三个参数。</span><span class="sxs-lookup"><span data-stu-id="86688-109">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="86688-110">有关如何声明此特性的详细信息，请参阅 [ValidateCount 特性声明](./validatecount-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="86688-110">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="86688-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86688-111">See Also</span></span>

[<span data-ttu-id="86688-112">ValidateCount 属性声明</span><span class="sxs-lookup"><span data-stu-id="86688-112">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="86688-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="86688-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
