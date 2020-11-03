---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0f1173cbfab139438d55ff49272f9625579820dc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197267"
---
# <span data-ttu-id="23286-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="23286-103">Unregister-PSRepository</span></span>

## <span data-ttu-id="23286-104">摘要</span><span class="sxs-lookup"><span data-stu-id="23286-104">SYNOPSIS</span></span>
<span data-ttu-id="23286-105">取消注册存储库。</span><span class="sxs-lookup"><span data-stu-id="23286-105">Unregisters a repository.</span></span>

## <span data-ttu-id="23286-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23286-106">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="23286-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23286-107">DESCRIPTION</span></span>

<span data-ttu-id="23286-108">`Unregister-PSRepository`Cmdlet 将为当前用户注销存储库。</span><span class="sxs-lookup"><span data-stu-id="23286-108">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="23286-109">示例</span><span class="sxs-lookup"><span data-stu-id="23286-109">EXAMPLES</span></span>

### <span data-ttu-id="23286-110">示例1：取消注册存储库</span><span class="sxs-lookup"><span data-stu-id="23286-110">Example 1: Unregister a repository</span></span>

<span data-ttu-id="23286-111">此示例将注销名为 myNuGetSource 的存储库。</span><span class="sxs-lookup"><span data-stu-id="23286-111">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="23286-112">示例2：取消注册所有存储库</span><span class="sxs-lookup"><span data-stu-id="23286-112">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="23286-113">此示例使用 `Get-PSRepository` 来获取所有已注册的存储库，并使用管道运算符将其传递给 `Unregister-PSRepository` 以将其注销。</span><span class="sxs-lookup"><span data-stu-id="23286-113">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="23286-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23286-114">PARAMETERS</span></span>

### <span data-ttu-id="23286-115">-Name</span><span class="sxs-lookup"><span data-stu-id="23286-115">-Name</span></span>

<span data-ttu-id="23286-116">指定要删除的存储库的名称数组。</span><span class="sxs-lookup"><span data-stu-id="23286-116">Specifies an array of names of the repositories to remove.</span></span>

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

### <span data-ttu-id="23286-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23286-117">CommonParameters</span></span>

<span data-ttu-id="23286-118">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="23286-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23286-119">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="23286-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23286-120">输入</span><span class="sxs-lookup"><span data-stu-id="23286-120">INPUTS</span></span>

### <span data-ttu-id="23286-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="23286-121">System.String[]</span></span>

## <span data-ttu-id="23286-122">输出</span><span class="sxs-lookup"><span data-stu-id="23286-122">OUTPUTS</span></span>

### <span data-ttu-id="23286-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="23286-123">System.Object</span></span>

## <span data-ttu-id="23286-124">注释</span><span class="sxs-lookup"><span data-stu-id="23286-124">NOTES</span></span>

## <span data-ttu-id="23286-125">相关链接</span><span class="sxs-lookup"><span data-stu-id="23286-125">RELATED LINKS</span></span>

[<span data-ttu-id="23286-126">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="23286-126">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="23286-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="23286-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="23286-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="23286-128">Set-PSRepository</span></span>](Set-PSRepository.md)
