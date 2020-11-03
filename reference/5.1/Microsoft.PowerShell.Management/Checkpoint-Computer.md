---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198332"
---
# <span data-ttu-id="d80f6-103">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="d80f6-103">Checkpoint-Computer</span></span>

## <span data-ttu-id="d80f6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="d80f6-104">SYNOPSIS</span></span>
<span data-ttu-id="d80f6-105">在本地计算机上创建系统还原点。</span><span class="sxs-lookup"><span data-stu-id="d80f6-105">Creates a system restore point on the local computer.</span></span>

## <span data-ttu-id="d80f6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d80f6-106">SYNTAX</span></span>

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## <span data-ttu-id="d80f6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d80f6-107">DESCRIPTION</span></span>

<span data-ttu-id="d80f6-108">`Checkpoint-Computer`Cmdlet 在本地计算机上创建系统还原点。</span><span class="sxs-lookup"><span data-stu-id="d80f6-108">The `Checkpoint-Computer` cmdlet creates a system restore point on the local computer.</span></span>

<span data-ttu-id="d80f6-109">系统还原点和 `Checkpoint-Computer` cmdlet 仅在客户端操作系统（如 windows 8、windows 7、Windows Vista 和 WINDOWS XP）上受支持。</span><span class="sxs-lookup"><span data-stu-id="d80f6-109">System restore points and the `Checkpoint-Computer` cmdlet are supported only on client operating systems, such as Windows 8, Windows 7, Windows Vista, and Windows XP.</span></span>

<span data-ttu-id="d80f6-110">从 Windows 8 开始， `Checkpoint-Computer` 每日创建的检查点不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="d80f6-110">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one checkpoint each day.</span></span>

## <span data-ttu-id="d80f6-111">示例</span><span class="sxs-lookup"><span data-stu-id="d80f6-111">EXAMPLES</span></span>

### <span data-ttu-id="d80f6-112">示例 1：创建系统还原点</span><span class="sxs-lookup"><span data-stu-id="d80f6-112">Example 1: Create a system restore point</span></span>

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

<span data-ttu-id="d80f6-113">此命令将创建一个名为 Install MyApp 的系统还原点。</span><span class="sxs-lookup"><span data-stu-id="d80f6-113">This command creates a system restore point called Install MyApp.</span></span>
<span data-ttu-id="d80f6-114">它使用默认的 APPLICATION_INSTALL 还原点类型。</span><span class="sxs-lookup"><span data-stu-id="d80f6-114">It uses the default APPLICATION_INSTALL restore point type.</span></span>

### <span data-ttu-id="d80f6-115">示例 2：创建系统 MODIFY_SETTINGS 还原点</span><span class="sxs-lookup"><span data-stu-id="d80f6-115">Example 2: Create a system MODIFY_SETTINGS restore point</span></span>

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

<span data-ttu-id="d80f6-116">此命令将创建一个名为“ChangeNetSettings”的 MODIFY_SETTINGS 系统还原点。</span><span class="sxs-lookup"><span data-stu-id="d80f6-116">This command creates a MODIFY_SETTINGS system restore point called "ChangeNetSettings".</span></span>

## <span data-ttu-id="d80f6-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d80f6-117">PARAMETERS</span></span>

### <span data-ttu-id="d80f6-118">-Description</span><span class="sxs-lookup"><span data-stu-id="d80f6-118">-Description</span></span>

<span data-ttu-id="d80f6-119">指定还原点的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="d80f6-119">Specifies a descriptive name for the restore point.</span></span>
<span data-ttu-id="d80f6-120">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="d80f6-120">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d80f6-121">-RestorePointType</span><span class="sxs-lookup"><span data-stu-id="d80f6-121">-RestorePointType</span></span>

<span data-ttu-id="d80f6-122">指定还原点的类型。</span><span class="sxs-lookup"><span data-stu-id="d80f6-122">Specifies the type of restore point.</span></span>
<span data-ttu-id="d80f6-123">默认值为 APPLICATION_INSTALL。</span><span class="sxs-lookup"><span data-stu-id="d80f6-123">The default is APPLICATION_INSTALL.</span></span>

<span data-ttu-id="d80f6-124">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="d80f6-124">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d80f6-125">APPLICATION_INSTALL</span><span class="sxs-lookup"><span data-stu-id="d80f6-125">APPLICATION_INSTALL</span></span>
- <span data-ttu-id="d80f6-126">APPLICATION_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="d80f6-126">APPLICATION_UNINSTALL</span></span>
- <span data-ttu-id="d80f6-127">DEVICE_DRIVER_INSTALL</span><span class="sxs-lookup"><span data-stu-id="d80f6-127">DEVICE_DRIVER_INSTALL</span></span>
- <span data-ttu-id="d80f6-128">MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="d80f6-128">MODIFY_SETTINGS</span></span>
- <span data-ttu-id="d80f6-129">CANCELLED_OPERATION</span><span class="sxs-lookup"><span data-stu-id="d80f6-129">CANCELLED_OPERATION</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d80f6-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d80f6-130">CommonParameters</span></span>

<span data-ttu-id="d80f6-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="d80f6-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d80f6-132">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="d80f6-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d80f6-133">输入</span><span class="sxs-lookup"><span data-stu-id="d80f6-133">INPUTS</span></span>

### <span data-ttu-id="d80f6-134">无</span><span class="sxs-lookup"><span data-stu-id="d80f6-134">None</span></span>

<span data-ttu-id="d80f6-135">不能通过管道将对象传递给 `Checkpoint-Computer` 。</span><span class="sxs-lookup"><span data-stu-id="d80f6-135">You cannot pipe objects to `Checkpoint-Computer`.</span></span>

## <span data-ttu-id="d80f6-136">输出</span><span class="sxs-lookup"><span data-stu-id="d80f6-136">OUTPUTS</span></span>

### <span data-ttu-id="d80f6-137">无</span><span class="sxs-lookup"><span data-stu-id="d80f6-137">None</span></span>

<span data-ttu-id="d80f6-138">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="d80f6-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d80f6-139">注释</span><span class="sxs-lookup"><span data-stu-id="d80f6-139">NOTES</span></span>

- <span data-ttu-id="d80f6-140">此 cmdlet 将 **SystemRestore** 类的 **CreateRestorePoint** 方法与 **BEGIN_SYSTEM_CHANGE** 事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="d80f6-140">This cmdlet uses the **CreateRestorePoint** method of the **SystemRestore** class with a **BEGIN_SYSTEM_CHANGE** event.</span></span>
- <span data-ttu-id="d80f6-141">从 Windows 8 开始， `Checkpoint-Computer` 每天无法创建多个系统还原点。</span><span class="sxs-lookup"><span data-stu-id="d80f6-141">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one system restore point each day.</span></span> <span data-ttu-id="d80f6-142">如果你尝试在 24 小时内再创建一个新的还原点，则 Windows PowerShell 将生成以下错误：</span><span class="sxs-lookup"><span data-stu-id="d80f6-142">If you try to create a new restore point before the 24-hour period has elapsed, Windows PowerShell generates the following error:</span></span>

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## <span data-ttu-id="d80f6-143">相关链接</span><span class="sxs-lookup"><span data-stu-id="d80f6-143">RELATED LINKS</span></span>

[<span data-ttu-id="d80f6-144">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="d80f6-144">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="d80f6-145">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="d80f6-145">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="d80f6-146">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="d80f6-146">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="d80f6-147">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="d80f6-147">Restore-Computer</span></span>](Restore-Computer.md)
