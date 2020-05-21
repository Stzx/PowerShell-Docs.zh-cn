---
title: ValidateCount 特性声明 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692369"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="e084a-102">ValidateCount 属性声明</span><span class="sxs-lookup"><span data-stu-id="e084a-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="e084a-103">ValidateCount 属性指定 cmdlet 参数允许的最小和最大参数数量。</span><span class="sxs-lookup"><span data-stu-id="e084a-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="e084a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e084a-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="e084a-105">参数</span><span class="sxs-lookup"><span data-stu-id="e084a-105">Parameters</span></span>

<span data-ttu-id="e084a-106">`MinLength`必需[System.Int32][]。</span><span class="sxs-lookup"><span data-stu-id="e084a-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="e084a-107">指定参数的最小数目。</span><span class="sxs-lookup"><span data-stu-id="e084a-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="e084a-108">`MaxLength`必需[System.Int32][]。</span><span class="sxs-lookup"><span data-stu-id="e084a-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="e084a-109">指定参数的最大数目。</span><span class="sxs-lookup"><span data-stu-id="e084a-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="e084a-110">备注</span><span class="sxs-lookup"><span data-stu-id="e084a-110">Remarks</span></span>

- <span data-ttu-id="e084a-111">有关如何声明此属性的详细信息，请参阅[如何验证参数计数][]。</span><span class="sxs-lookup"><span data-stu-id="e084a-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="e084a-112">如果未调用此属性，则对应的 cmdlet 参数可以有任意数量的参数。</span><span class="sxs-lookup"><span data-stu-id="e084a-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="e084a-113">Windows PowerShell 运行时在以下条件下引发错误：</span><span class="sxs-lookup"><span data-stu-id="e084a-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="e084a-114">`MinLength`和 `MaxLength` 特性参数的类型不是[system.object][]。</span><span class="sxs-lookup"><span data-stu-id="e084a-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="e084a-115">Attribute 参数的值 `MaxLength` 小于 `MinLength` attribute 参数的值。</span><span class="sxs-lookup"><span data-stu-id="e084a-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="e084a-116">ValidateCount 特性是由[ValidateCountAttribute][]类定义的。</span><span class="sxs-lookup"><span data-stu-id="e084a-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="e084a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e084a-117">See Also</span></span>

<span data-ttu-id="e084a-118">[System.web. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="e084a-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="e084a-119">[如何验证参数计数][]</span><span class="sxs-lookup"><span data-stu-id="e084a-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="e084a-120">[编写 Windows PowerShell Cmdlet][]</span><span class="sxs-lookup"><span data-stu-id="e084a-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[如何验证参数计数]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[编写 Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.web. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
