---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: e9170a8023977f485a99e5e7fc59fb2280a8081e
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347578"
---
# <span data-ttu-id="77618-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="77618-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="77618-104">摘要</span><span class="sxs-lookup"><span data-stu-id="77618-104">SYNOPSIS</span></span>
<span data-ttu-id="77618-105">获取系统属性和操作系统属性的合并对象。</span><span class="sxs-lookup"><span data-stu-id="77618-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="77618-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77618-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="77618-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77618-107">DESCRIPTION</span></span>

<span data-ttu-id="77618-108">`Get-ComputerInfo`Cmdlet 将获取系统属性和操作系统属性的合并对象。</span><span class="sxs-lookup"><span data-stu-id="77618-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="77618-109">此 cmdlet 是在 Windows PowerShell 5.1 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77618-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="77618-110">示例</span><span class="sxs-lookup"><span data-stu-id="77618-110">EXAMPLES</span></span>

### <span data-ttu-id="77618-111">示例1：获取所有计算机属性</span><span class="sxs-lookup"><span data-stu-id="77618-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="77618-112">此命令从计算机中获取所有系统属性和操作系统属性。</span><span class="sxs-lookup"><span data-stu-id="77618-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="77618-113">示例2：获取所有计算机操作系统属性</span><span class="sxs-lookup"><span data-stu-id="77618-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="77618-114">此命令从计算机中获取所有操作系统属性。</span><span class="sxs-lookup"><span data-stu-id="77618-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="77618-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77618-115">PARAMETERS</span></span>

### <span data-ttu-id="77618-116">-Property</span><span class="sxs-lookup"><span data-stu-id="77618-116">-Property</span></span>

<span data-ttu-id="77618-117">以字符串数组的形式指定此 cmdlet 显示的计算机属性。</span><span class="sxs-lookup"><span data-stu-id="77618-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="77618-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="77618-118">CommonParameters</span></span>

<span data-ttu-id="77618-119">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="77618-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77618-120">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="77618-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="77618-121">输入</span><span class="sxs-lookup"><span data-stu-id="77618-121">INPUTS</span></span>

### <span data-ttu-id="77618-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="77618-122">System.String[]</span></span>

## <span data-ttu-id="77618-123">输出</span><span class="sxs-lookup"><span data-stu-id="77618-123">OUTPUTS</span></span>

### <span data-ttu-id="77618-124">ComputerInfo。</span><span class="sxs-lookup"><span data-stu-id="77618-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="77618-125">注释</span><span class="sxs-lookup"><span data-stu-id="77618-125">NOTES</span></span>

<span data-ttu-id="77618-126">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="77618-126">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="77618-127">相关链接</span><span class="sxs-lookup"><span data-stu-id="77618-127">RELATED LINKS</span></span>
