---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateRange 属性声明
description: ValidateRange 属性声明
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660610"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="202c9-103">ValidateRange 属性声明</span><span class="sxs-lookup"><span data-stu-id="202c9-103">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="202c9-104">ValidateRange 属性指定 cmdlet 参数参数 (范围) 的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="202c9-104">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="202c9-105">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="202c9-105">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="202c9-106">语法</span><span class="sxs-lookup"><span data-stu-id="202c9-106">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="202c9-107">parameters</span><span class="sxs-lookup"><span data-stu-id="202c9-107">Parameters</span></span>

<span data-ttu-id="202c9-108">`MinRange`需要[ () 。](/dotnet/api/system.object)</span><span class="sxs-lookup"><span data-stu-id="202c9-108">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="202c9-109">指定允许的最小值。</span><span class="sxs-lookup"><span data-stu-id="202c9-109">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="202c9-110">`MaxRange`需要[ () 。](/dotnet/api/system.object)</span><span class="sxs-lookup"><span data-stu-id="202c9-110">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="202c9-111">指定允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="202c9-111">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="202c9-112">备注</span><span class="sxs-lookup"><span data-stu-id="202c9-112">Remarks</span></span>

- <span data-ttu-id="202c9-113">当参数的值大于参数的值时，Windows PowerShell 运行时将引发构造错误 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="202c9-113">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="202c9-114">Windows PowerShell 运行时在以下条件下引发验证错误：</span><span class="sxs-lookup"><span data-stu-id="202c9-114">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="202c9-115">当参数的值小于 `MinRange` 或大于限制时 `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="202c9-115">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="202c9-116">参数的类型与 `MinRange` 和 `MaxRange` 参数不同。</span><span class="sxs-lookup"><span data-stu-id="202c9-116">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="202c9-117">ValidateRange 特性是由 [Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) 类定义的。</span><span class="sxs-lookup"><span data-stu-id="202c9-117">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="202c9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="202c9-118">See Also</span></span>

[<span data-ttu-id="202c9-119">System.web. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="202c9-119">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="202c9-120">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="202c9-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
