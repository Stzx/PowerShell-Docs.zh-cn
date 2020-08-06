---
title: Cmdlet 代码中的属性 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1f92e329d304754d5596cef0c95dc597aca3a538
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774909"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="cdb72-102">Cmdlet 代码中的属性</span><span class="sxs-lookup"><span data-stu-id="cdb72-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="cdb72-103">若要使用 Windows PowerShell 提供的通用功能，请使用属性修饰 cmdlet 代码中定义的类和公共属性。</span><span class="sxs-lookup"><span data-stu-id="cdb72-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="cdb72-104">例如，下面的类定义使用 Cmdlet 特性来标识实现了**get-help** Cmdlet 的 Microsoft .NET 框架类。</span><span class="sxs-lookup"><span data-stu-id="cdb72-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="cdb72-105"> (此 cmdlet 用作本文档中的示例，类似于 `Get-Process` Windows PowerShell 提供的 cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="cdb72-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="cdb72-106">这些属性被视为元数据，因为它们的实现与 cmdlet 代码的实现不同。</span><span class="sxs-lookup"><span data-stu-id="cdb72-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="cdb72-107">当 Windows PowerShell 运行时运行该 cmdlet 时，它会识别这些属性，然后针对每个属性执行相应的操作。</span><span class="sxs-lookup"><span data-stu-id="cdb72-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="cdb72-108">尽管你可能想要实现这些属性提供的功能版本，但良好的 cmdlet 设计则使用这些常见功能。</span><span class="sxs-lookup"><span data-stu-id="cdb72-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="cdb72-109">有关可在 cmdlet 中声明的不同属性的详细信息，请参阅[属性类型](./attribute-types.md)。</span><span class="sxs-lookup"><span data-stu-id="cdb72-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cdb72-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdb72-110">See Also</span></span>

[<span data-ttu-id="cdb72-111">属性类型</span><span class="sxs-lookup"><span data-stu-id="cdb72-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="cdb72-112">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cdb72-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
