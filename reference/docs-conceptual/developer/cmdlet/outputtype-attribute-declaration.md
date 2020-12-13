---
ms.date: 09/13/2016
ms.topic: reference
title: OutputType 属性声明
description: OutputType 属性声明
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646457"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="6ac45-103">OutputType 属性声明</span><span class="sxs-lookup"><span data-stu-id="6ac45-103">OutputType Attribute Declaration</span></span>

<span data-ttu-id="6ac45-104">`OutputType`属性标识由 cmdlet、函数或脚本返回的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="6ac45-104">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ac45-105">语法</span><span class="sxs-lookup"><span data-stu-id="6ac45-105">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="6ac45-106">parameters</span><span class="sxs-lookup"><span data-stu-id="6ac45-106">Parameters</span></span>

<span data-ttu-id="6ac45-107">需要键入 (`string[]` 或 `Type[]`) 。</span><span class="sxs-lookup"><span data-stu-id="6ac45-107">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="6ac45-108">指定由 cmdlet 函数或脚本返回的类型。</span><span class="sxs-lookup"><span data-stu-id="6ac45-108">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="6ac45-109">ParameterSetName (string [] ) 可选的。</span><span class="sxs-lookup"><span data-stu-id="6ac45-109">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="6ac45-110">指定返回参数中指定的类型的参数集 `type` 。</span><span class="sxs-lookup"><span data-stu-id="6ac45-110">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="6ac45-111">providerCmdlet 可选。</span><span class="sxs-lookup"><span data-stu-id="6ac45-111">providerCmdlet Optional.</span></span> <span data-ttu-id="6ac45-112">指定提供程序 cmdlet，该 cmdlet 返回参数中指定的类型 `type` 。</span><span class="sxs-lookup"><span data-stu-id="6ac45-112">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ac45-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ac45-113">See Also</span></span>

[<span data-ttu-id="6ac45-114">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6ac45-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
