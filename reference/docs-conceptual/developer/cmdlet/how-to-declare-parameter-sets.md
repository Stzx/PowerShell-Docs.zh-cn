---
title: 如何声明参数集 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e6d06a9a78356693fe7a338dc5c9207044b23441
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784157"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="2852e-102">如何声明参数集</span><span class="sxs-lookup"><span data-stu-id="2852e-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="2852e-103">此示例演示如何在声明 cmdlet 的参数时定义两个参数集。</span><span class="sxs-lookup"><span data-stu-id="2852e-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="2852e-104">每个参数集都具有唯一参数和两个参数集均使用的共享参数。</span><span class="sxs-lookup"><span data-stu-id="2852e-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="2852e-105">有关参数集的详细信息，包括如何指定默认参数集，请参阅[Cmdlet 参数集](./cmdlet-parameter-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="2852e-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2852e-106">尽可能将参数集的唯一参数定义为必需的参数。</span><span class="sxs-lookup"><span data-stu-id="2852e-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="2852e-107">但是，如果想要在不指定任何参数的情况下运行 cmdlet，则 unique 参数可以是可选参数。</span><span class="sxs-lookup"><span data-stu-id="2852e-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="2852e-108">例如，cmdlet 的唯一参数 `Get-Command` 是可选的。</span><span class="sxs-lookup"><span data-stu-id="2852e-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="2852e-109">如何定义两个参数集</span><span class="sxs-lookup"><span data-stu-id="2852e-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="2852e-110">将 `ParameterSet` 关键字添加到第一个参数集的 unique 参数的 parameter 特性中。</span><span class="sxs-lookup"><span data-stu-id="2852e-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. <span data-ttu-id="2852e-111">`ParameterSet`对于第二个参数集的唯一参数，将关键字添加到参数特性。</span><span class="sxs-lookup"><span data-stu-id="2852e-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. <span data-ttu-id="2852e-112">对于属于这两个参数集的参数，请为每个参数集添加一个参数特性，然后将 `ParameterSet` 关键字添加到每个集合。</span><span class="sxs-lookup"><span data-stu-id="2852e-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="2852e-113">在每个参数特性中，可以指定如何定义该参数。</span><span class="sxs-lookup"><span data-stu-id="2852e-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="2852e-114">参数在一组中是可选的，另一种是强制参数。</span><span class="sxs-lookup"><span data-stu-id="2852e-114">A parameter can be optional in one set and mandatory in another.</span></span>

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a><span data-ttu-id="2852e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2852e-115">See Also</span></span>

[<span data-ttu-id="2852e-116">Cmdlet 参数集</span><span class="sxs-lookup"><span data-stu-id="2852e-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="2852e-117">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2852e-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
