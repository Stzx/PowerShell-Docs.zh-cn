---
title: ValidateCount 特性声明 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.openlocfilehash: c013a354ee339bd14508fe30549673bc79d5c616
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786316"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="17b38-102">ValidateCount 属性声明</span><span class="sxs-lookup"><span data-stu-id="17b38-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="17b38-103">ValidateCount 属性指定 cmdlet 参数允许的最小和最大参数数量。</span><span class="sxs-lookup"><span data-stu-id="17b38-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="17b38-104">语法</span><span class="sxs-lookup"><span data-stu-id="17b38-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="17b38-105">parameters</span><span class="sxs-lookup"><span data-stu-id="17b38-105">Parameters</span></span>

<span data-ttu-id="17b38-106">`MinLength`需要[ () 。][]</span><span class="sxs-lookup"><span data-stu-id="17b38-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="17b38-107">指定参数的最小数目。</span><span class="sxs-lookup"><span data-stu-id="17b38-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="17b38-108">`MaxLength`需要[ () 。][]</span><span class="sxs-lookup"><span data-stu-id="17b38-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="17b38-109">指定参数的最大数目。</span><span class="sxs-lookup"><span data-stu-id="17b38-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="17b38-110">备注</span><span class="sxs-lookup"><span data-stu-id="17b38-110">Remarks</span></span>

- <span data-ttu-id="17b38-111">有关如何声明此属性的详细信息，请参阅[如何验证参数计数][]。</span><span class="sxs-lookup"><span data-stu-id="17b38-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="17b38-112">如果未调用此属性，则对应的 cmdlet 参数可以有任意数量的参数。</span><span class="sxs-lookup"><span data-stu-id="17b38-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="17b38-113">Windows PowerShell 运行时在以下条件下引发错误：</span><span class="sxs-lookup"><span data-stu-id="17b38-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="17b38-114">`MinLength`和 `MaxLength` 特性参数的类型不是[system.object][]。</span><span class="sxs-lookup"><span data-stu-id="17b38-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="17b38-115">Attribute 参数的值 `MaxLength` 小于 `MinLength` attribute 参数的值。</span><span class="sxs-lookup"><span data-stu-id="17b38-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="17b38-116">ValidateCount 特性是由[ValidateCountAttribute][]类定义的。</span><span class="sxs-lookup"><span data-stu-id="17b38-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="17b38-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17b38-117">See Also</span></span>

<span data-ttu-id="17b38-118">[System.web. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="17b38-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="17b38-119">[如何验证参数计数][]</span><span class="sxs-lookup"><span data-stu-id="17b38-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="17b38-120">[编写 Windows PowerShell Cmdlet][]</span><span class="sxs-lookup"><span data-stu-id="17b38-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[如何验证参数计数]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[编写 Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.web. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
