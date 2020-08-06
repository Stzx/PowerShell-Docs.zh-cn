---
title: ValidateRange 特性声明 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787778"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="eaf1f-102">ValidateRange 属性声明</span><span class="sxs-lookup"><span data-stu-id="eaf1f-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="eaf1f-103">ValidateRange 属性指定 cmdlet 参数参数 (范围) 的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="eaf1f-104">此属性也可由 Windows PowerShell 函数使用。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="eaf1f-105">语法</span><span class="sxs-lookup"><span data-stu-id="eaf1f-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="eaf1f-106">parameters</span><span class="sxs-lookup"><span data-stu-id="eaf1f-106">Parameters</span></span>

<span data-ttu-id="eaf1f-107">`MinRange`需要[ () 。](/dotnet/api/system.object)</span><span class="sxs-lookup"><span data-stu-id="eaf1f-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="eaf1f-108">指定允许的最小值。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="eaf1f-109">`MaxRange`需要[ () 。](/dotnet/api/system.object)</span><span class="sxs-lookup"><span data-stu-id="eaf1f-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="eaf1f-110">指定允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="eaf1f-111">备注</span><span class="sxs-lookup"><span data-stu-id="eaf1f-111">Remarks</span></span>

- <span data-ttu-id="eaf1f-112">当参数的值大于参数的值时，Windows PowerShell 运行时将引发构造错误 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="eaf1f-113">Windows PowerShell 运行时在以下条件下引发验证错误：</span><span class="sxs-lookup"><span data-stu-id="eaf1f-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="eaf1f-114">当参数的值小于 `MinRange` 或大于限制时 `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="eaf1f-115">参数的类型与 `MinRange` 和 `MaxRange` 参数不同。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="eaf1f-116">ValidateRange 特性是由[Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)类定义的。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaf1f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eaf1f-117">See Also</span></span>

[<span data-ttu-id="eaf1f-118">System.web. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="eaf1f-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="eaf1f-119">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="eaf1f-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
