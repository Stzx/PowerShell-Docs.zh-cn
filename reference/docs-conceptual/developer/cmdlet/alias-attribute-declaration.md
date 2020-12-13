---
ms.date: 09/13/2016
ms.topic: reference
title: 别名属性声明
description: 别名属性声明
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668297"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="21d00-103">别名属性声明</span><span class="sxs-lookup"><span data-stu-id="21d00-103">Alias Attribute Declaration</span></span>

<span data-ttu-id="21d00-104">Alias 属性允许用户为 cmdlet 参数指定不同的名称。</span><span class="sxs-lookup"><span data-stu-id="21d00-104">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="21d00-105">可以使用别名提供参数名称的快捷方式，也可以提供适用于不同方案的不同名称。</span><span class="sxs-lookup"><span data-stu-id="21d00-105">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="21d00-106">语法</span><span class="sxs-lookup"><span data-stu-id="21d00-106">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="21d00-107">parameters</span><span class="sxs-lookup"><span data-stu-id="21d00-107">Parameters</span></span>

<span data-ttu-id="21d00-108">`aliasName` 需要 (String [] ) 。</span><span class="sxs-lookup"><span data-stu-id="21d00-108">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="21d00-109">指定 cmdlet 参数的一组以逗号分隔的别名。</span><span class="sxs-lookup"><span data-stu-id="21d00-109">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="21d00-110">备注</span><span class="sxs-lookup"><span data-stu-id="21d00-110">Remarks</span></span>

- <span data-ttu-id="21d00-111">当指定 cmdlet 参数时，会将 Alias 特性与参数特性一起使用。</span><span class="sxs-lookup"><span data-stu-id="21d00-111">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="21d00-112">有关如何声明这些属性的详细信息，请参阅 [如何声明 Cmdlet 参数](./how-to-declare-cmdlet-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="21d00-112">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="21d00-113">每个别名在 cmdlet 中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="21d00-113">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="21d00-114">Windows PowerShell 不会检查是否存在重复的别名。</span><span class="sxs-lookup"><span data-stu-id="21d00-114">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="21d00-115">为 cmdlet 中的每个参数使用一次 Alias 特性。</span><span class="sxs-lookup"><span data-stu-id="21d00-115">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="21d00-116">Alias 特性是由 [Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) 类定义的。</span><span class="sxs-lookup"><span data-stu-id="21d00-116">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="21d00-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21d00-117">See Also</span></span>

[<span data-ttu-id="21d00-118">参数别名</span><span class="sxs-lookup"><span data-stu-id="21d00-118">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="21d00-119">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="21d00-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
