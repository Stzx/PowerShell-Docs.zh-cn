---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 63f9f644a81886dab498e46fce90d4ff2f7be91b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198699"
---
# <span data-ttu-id="09b20-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="09b20-102">Get-LogProperties</span></span>

## <span data-ttu-id="09b20-103">摘要</span><span class="sxs-lookup"><span data-stu-id="09b20-103">SYNOPSIS</span></span>
<span data-ttu-id="09b20-104">检索 Windows 事件日志的属性。</span><span class="sxs-lookup"><span data-stu-id="09b20-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="09b20-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09b20-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="09b20-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09b20-106">DESCRIPTION</span></span>

<span data-ttu-id="09b20-107">此 cmdlet 将获取 Windows 事件日志的配置设置。</span><span class="sxs-lookup"><span data-stu-id="09b20-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="09b20-108">此 cmdlet 由 `Enable-PSTrace` 和 `Disable-PSTrace` cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="09b20-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="09b20-109">示例</span><span class="sxs-lookup"><span data-stu-id="09b20-109">EXAMPLES</span></span>

### <span data-ttu-id="09b20-110">示例1：获取 Windows PowerShell 事件日志的配置设置</span><span class="sxs-lookup"><span data-stu-id="09b20-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="09b20-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09b20-111">PARAMETERS</span></span>

### <span data-ttu-id="09b20-112">-Name</span><span class="sxs-lookup"><span data-stu-id="09b20-112">-Name</span></span>

<span data-ttu-id="09b20-113">事件提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="09b20-113">The name of the event provider.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="09b20-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="09b20-114">CommonParameters</span></span>

<span data-ttu-id="09b20-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="09b20-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09b20-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="09b20-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="09b20-117">输入</span><span class="sxs-lookup"><span data-stu-id="09b20-117">INPUTS</span></span>

### <span data-ttu-id="09b20-118">System.String</span><span class="sxs-lookup"><span data-stu-id="09b20-118">System.String</span></span>

## <span data-ttu-id="09b20-119">输出</span><span class="sxs-lookup"><span data-stu-id="09b20-119">OUTPUTS</span></span>

### <span data-ttu-id="09b20-120">LogDetails。</span><span class="sxs-lookup"><span data-stu-id="09b20-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="09b20-121">**PSDiagnostics** 模块将 **LogDetails** 类添加到 `Microsoft.PowerShell.Diagnostics` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="09b20-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="09b20-122">注释</span><span class="sxs-lookup"><span data-stu-id="09b20-122">NOTES</span></span>

## <span data-ttu-id="09b20-123">相关链接</span><span class="sxs-lookup"><span data-stu-id="09b20-123">RELATED LINKS</span></span>

[<span data-ttu-id="09b20-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="09b20-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="09b20-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="09b20-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="09b20-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="09b20-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
