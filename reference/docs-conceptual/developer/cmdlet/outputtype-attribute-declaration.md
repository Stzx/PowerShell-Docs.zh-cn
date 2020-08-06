---
title: OutputType 特性声明 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786537"
---
# <a name="outputtype-attribute-declaration"></a><span data-ttu-id="3aa83-102">OutputType 属性声明</span><span class="sxs-lookup"><span data-stu-id="3aa83-102">OutputType Attribute Declaration</span></span>

<span data-ttu-id="3aa83-103">`OutputType`属性标识由 cmdlet、函数或脚本返回的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="3aa83-103">The `OutputType` attribute identifies the .NET Framework types returned by a cmdlet, function, or script.</span></span>

## <a name="syntax"></a><span data-ttu-id="3aa83-104">语法</span><span class="sxs-lookup"><span data-stu-id="3aa83-104">Syntax</span></span>

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="3aa83-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3aa83-105">Parameters</span></span>

<span data-ttu-id="3aa83-106">需要键入 (`string[]` 或 `Type[]`) 。</span><span class="sxs-lookup"><span data-stu-id="3aa83-106">Type (`string[]` or `Type[]`) Required.</span></span> <span data-ttu-id="3aa83-107">指定由 cmdlet 函数或脚本返回的类型。</span><span class="sxs-lookup"><span data-stu-id="3aa83-107">Specifies the types returned by the cmdlet function, or script.</span></span>

<span data-ttu-id="3aa83-108">ParameterSetName (string [] ) 可选的。</span><span class="sxs-lookup"><span data-stu-id="3aa83-108">ParameterSetName (string[]) Optional.</span></span> <span data-ttu-id="3aa83-109">指定返回参数中指定的类型的参数集 `type` 。</span><span class="sxs-lookup"><span data-stu-id="3aa83-109">Specifies the parameter sets that return the types specified in the `type` parameter.</span></span>

<span data-ttu-id="3aa83-110">providerCmdlet 可选。</span><span class="sxs-lookup"><span data-stu-id="3aa83-110">providerCmdlet Optional.</span></span> <span data-ttu-id="3aa83-111">指定提供程序 cmdlet，该 cmdlet 返回参数中指定的类型 `type` 。</span><span class="sxs-lookup"><span data-stu-id="3aa83-111">Specifies the provider cmdlet that returns the types specified in the `type` parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="3aa83-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3aa83-112">See Also</span></span>

[<span data-ttu-id="3aa83-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3aa83-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
