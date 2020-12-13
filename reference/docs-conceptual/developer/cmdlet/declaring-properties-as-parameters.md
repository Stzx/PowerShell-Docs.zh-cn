---
ms.date: 09/13/2016
ms.topic: reference
title: 将属性声明为参数
description: 将属性声明为参数
ms.openlocfilehash: ade7928e2ca277da8bbd1a5e04997bd1d05f1e5d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653159"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="3e06c-103">将属性声明为参数</span><span class="sxs-lookup"><span data-stu-id="3e06c-103">Declaring Properties as Parameters</span></span>

<span data-ttu-id="3e06c-104">本主题提供在声明 cmdlet 参数之前必须了解的基本信息。</span><span class="sxs-lookup"><span data-stu-id="3e06c-104">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="3e06c-105">若要声明 cmdlet 类中 cmdlet 的参数，请定义表示每个参数的公共属性，然后将一个或多个参数特性添加到每个属性。</span><span class="sxs-lookup"><span data-stu-id="3e06c-105">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="3e06c-106">Windows PowerShell 运行时使用参数属性将属性标识为 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="3e06c-106">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="3e06c-107">用于声明参数特性的基本语法是 `[Parameter()]` 。</span><span class="sxs-lookup"><span data-stu-id="3e06c-107">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="3e06c-108">下面是一个定义为所需参数的属性示例。</span><span class="sxs-lookup"><span data-stu-id="3e06c-108">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="3e06c-109">下面是一些关于参数的注意事项。</span><span class="sxs-lookup"><span data-stu-id="3e06c-109">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="3e06c-110">参数必须显式标记为公共。</span><span class="sxs-lookup"><span data-stu-id="3e06c-110">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="3e06c-111">未标记为 "公共" 的参数默认为内部参数，将不会被 Windows PowerShell 运行时发现。</span><span class="sxs-lookup"><span data-stu-id="3e06c-111">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="3e06c-112">应将参数定义为 Microsoft .NET 框架类型，以提供更好的参数验证。</span><span class="sxs-lookup"><span data-stu-id="3e06c-112">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="3e06c-113">例如，限制为一组值中的一个值的参数应定义为枚举类型。</span><span class="sxs-lookup"><span data-stu-id="3e06c-113">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="3e06c-114">采用统一资源标识符 (URI) 值的参数应为[system.string 类型。](/dotnet/api/System.Uri)</span><span class="sxs-lookup"><span data-stu-id="3e06c-114">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="3e06c-115">避免为所有自由格式的文本属性提供基本的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="3e06c-115">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="3e06c-116">可以将参数添加到任意数量的参数集。</span><span class="sxs-lookup"><span data-stu-id="3e06c-116">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="3e06c-117">有关参数集的详细信息，请参阅 [Cmdlet 参数集](./cmdlet-parameter-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="3e06c-117">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="3e06c-118">Windows PowerShell 还提供了一组自动可用于每个 cmdlet 的通用参数。</span><span class="sxs-lookup"><span data-stu-id="3e06c-118">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="3e06c-119">有关这些参数及其别名的详细信息，请参阅 [Cmdlet 公用参数](./common-parameter-names.md)。</span><span class="sxs-lookup"><span data-stu-id="3e06c-119">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3e06c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e06c-120">See Also</span></span>

[<span data-ttu-id="3e06c-121">Cmdlet 通用参数</span><span class="sxs-lookup"><span data-stu-id="3e06c-121">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="3e06c-122">Cmdlet 参数的类型</span><span class="sxs-lookup"><span data-stu-id="3e06c-122">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

[<span data-ttu-id="3e06c-123">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3e06c-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
