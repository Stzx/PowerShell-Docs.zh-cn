---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateCount 属性声明
description: ValidateCount 属性声明
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646267"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="57b5d-103">ValidateCount 属性声明</span><span class="sxs-lookup"><span data-stu-id="57b5d-103">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="57b5d-104">ValidateCount 属性指定 cmdlet 参数允许的最小和最大参数数量。</span><span class="sxs-lookup"><span data-stu-id="57b5d-104">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="57b5d-105">语法</span><span class="sxs-lookup"><span data-stu-id="57b5d-105">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="57b5d-106">parameters</span><span class="sxs-lookup"><span data-stu-id="57b5d-106">Parameters</span></span>

<span data-ttu-id="57b5d-107">`MinLength`需要[ () 。][]</span><span class="sxs-lookup"><span data-stu-id="57b5d-107">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="57b5d-108">指定参数的最小数目。</span><span class="sxs-lookup"><span data-stu-id="57b5d-108">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="57b5d-109">`MaxLength`需要[ () 。][]</span><span class="sxs-lookup"><span data-stu-id="57b5d-109">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="57b5d-110">指定参数的最大数目。</span><span class="sxs-lookup"><span data-stu-id="57b5d-110">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="57b5d-111">备注</span><span class="sxs-lookup"><span data-stu-id="57b5d-111">Remarks</span></span>

- <span data-ttu-id="57b5d-112">有关如何声明此属性的详细信息，请参阅 [如何验证参数计数][]。</span><span class="sxs-lookup"><span data-stu-id="57b5d-112">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="57b5d-113">如果未调用此属性，则对应的 cmdlet 参数可以有任意数量的参数。</span><span class="sxs-lookup"><span data-stu-id="57b5d-113">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="57b5d-114">Windows PowerShell 运行时在以下条件下引发错误：</span><span class="sxs-lookup"><span data-stu-id="57b5d-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="57b5d-115">`MinLength`和 `MaxLength` 特性参数的类型不是[system.object][]。</span><span class="sxs-lookup"><span data-stu-id="57b5d-115">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="57b5d-116">Attribute 参数的值 `MaxLength` 小于 `MinLength` attribute 参数的值。</span><span class="sxs-lookup"><span data-stu-id="57b5d-116">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="57b5d-117">ValidateCount 特性是由 [ValidateCountAttribute][] 类定义的。</span><span class="sxs-lookup"><span data-stu-id="57b5d-117">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="57b5d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57b5d-118">See Also</span></span>

<span data-ttu-id="57b5d-119">[System.web. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="57b5d-119">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="57b5d-120">[如何验证参数计数][]</span><span class="sxs-lookup"><span data-stu-id="57b5d-120">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="57b5d-121">[编写 Windows PowerShell Cmdlet][]</span><span class="sxs-lookup"><span data-stu-id="57b5d-121">[Writing a Windows PowerShell Cmdlet][]</span></span>

[如何验证参数计数]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[编写 Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.web. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
