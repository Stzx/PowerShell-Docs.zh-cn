---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 769d1ac91cbbc580b3488ba84d14a759b6ef65d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198101"
---
# <span data-ttu-id="9530a-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9530a-103">Unregister-PSRepository</span></span>

## <span data-ttu-id="9530a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9530a-104">SYNOPSIS</span></span>
<span data-ttu-id="9530a-105">取消注册存储库。</span><span class="sxs-lookup"><span data-stu-id="9530a-105">Unregisters a repository.</span></span>

## <span data-ttu-id="9530a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9530a-106">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="9530a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9530a-107">DESCRIPTION</span></span>

<span data-ttu-id="9530a-108">`Unregister-PSRepository`Cmdlet 将为当前用户注销存储库。</span><span class="sxs-lookup"><span data-stu-id="9530a-108">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="9530a-109">示例</span><span class="sxs-lookup"><span data-stu-id="9530a-109">EXAMPLES</span></span>

### <span data-ttu-id="9530a-110">示例1：取消注册存储库</span><span class="sxs-lookup"><span data-stu-id="9530a-110">Example 1: Unregister a repository</span></span>

<span data-ttu-id="9530a-111">此示例将注销名为 myNuGetSource 的存储库。</span><span class="sxs-lookup"><span data-stu-id="9530a-111">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="9530a-112">示例2：取消注册所有存储库</span><span class="sxs-lookup"><span data-stu-id="9530a-112">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="9530a-113">此示例使用 `Get-PSRepository` 来获取所有已注册的存储库，并使用管道运算符将其传递给 `Unregister-PSRepository` 以将其注销。</span><span class="sxs-lookup"><span data-stu-id="9530a-113">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="9530a-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9530a-114">PARAMETERS</span></span>

### <span data-ttu-id="9530a-115">-Name</span><span class="sxs-lookup"><span data-stu-id="9530a-115">-Name</span></span>

<span data-ttu-id="9530a-116">指定要删除的存储库的名称数组。</span><span class="sxs-lookup"><span data-stu-id="9530a-116">Specifies an array of names of the repositories to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9530a-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9530a-117">CommonParameters</span></span>

<span data-ttu-id="9530a-118">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9530a-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9530a-119">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9530a-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9530a-120">输入</span><span class="sxs-lookup"><span data-stu-id="9530a-120">INPUTS</span></span>

### <span data-ttu-id="9530a-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="9530a-121">System.String[]</span></span>

## <span data-ttu-id="9530a-122">输出</span><span class="sxs-lookup"><span data-stu-id="9530a-122">OUTPUTS</span></span>

### <span data-ttu-id="9530a-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="9530a-123">System.Object</span></span>

## <span data-ttu-id="9530a-124">注释</span><span class="sxs-lookup"><span data-stu-id="9530a-124">NOTES</span></span>

## <span data-ttu-id="9530a-125">相关链接</span><span class="sxs-lookup"><span data-stu-id="9530a-125">RELATED LINKS</span></span>

[<span data-ttu-id="9530a-126">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9530a-126">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="9530a-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9530a-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="9530a-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9530a-128">Set-PSRepository</span></span>](Set-PSRepository.md)
