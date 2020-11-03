---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8e64c3e3a782fadf1669f1310d1615f3a014ccee
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196931"
---
# <span data-ttu-id="619eb-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="619eb-103">New-WinEvent</span></span>

## <span data-ttu-id="619eb-104">摘要</span><span class="sxs-lookup"><span data-stu-id="619eb-104">SYNOPSIS</span></span>
<span data-ttu-id="619eb-105">为指定的事件提供程序创建一个新的 Windows 事件。</span><span class="sxs-lookup"><span data-stu-id="619eb-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="619eb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="619eb-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="619eb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="619eb-107">DESCRIPTION</span></span>

<span data-ttu-id="619eb-108">**New-WinEvent** cmdlet 可为事件提供程序创建 Windows 事件跟踪 (ETW) 事件。</span><span class="sxs-lookup"><span data-stu-id="619eb-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="619eb-109">可以使用此 cmdlet 将事件从 PowerShell 添加到 ETW 通道。</span><span class="sxs-lookup"><span data-stu-id="619eb-109">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="619eb-110">示例</span><span class="sxs-lookup"><span data-stu-id="619eb-110">EXAMPLES</span></span>

### <span data-ttu-id="619eb-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="619eb-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="619eb-112">此命令使用 **New-WinEvent** cmdlet 为 Microsoft-Windows-PowerShell 提供程序创建事件 45090。</span><span class="sxs-lookup"><span data-stu-id="619eb-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="619eb-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="619eb-113">PARAMETERS</span></span>

### <span data-ttu-id="619eb-114">-Id</span><span class="sxs-lookup"><span data-stu-id="619eb-114">-Id</span></span>

<span data-ttu-id="619eb-115">指定通过检测清单注册的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="619eb-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="619eb-116">-Payload</span><span class="sxs-lookup"><span data-stu-id="619eb-116">-Payload</span></span>

<span data-ttu-id="619eb-117">指定事件的消息。</span><span class="sxs-lookup"><span data-stu-id="619eb-117">Specifies the message for the event.</span></span> <span data-ttu-id="619eb-118">当事件写入事件日志后，负载将存储在事件对象的 **Message** 属性中。</span><span class="sxs-lookup"><span data-stu-id="619eb-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="619eb-119">当指定的负载与事件定义中的负载不匹配时，PowerShell 会生成一个警告，但命令仍会成功。</span><span class="sxs-lookup"><span data-stu-id="619eb-119">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="619eb-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="619eb-120">-ProviderName</span></span>

<span data-ttu-id="619eb-121">指定将事件写入事件日志的事件提供程序，例如“Microsoft-Windows-PowerShell”。</span><span class="sxs-lookup"><span data-stu-id="619eb-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="619eb-122">ETW 事件提供程序是将事件写入 ETW 会话的逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="619eb-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

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

### <span data-ttu-id="619eb-123">-Version</span><span class="sxs-lookup"><span data-stu-id="619eb-123">-Version</span></span>

<span data-ttu-id="619eb-124">指定事件的版本号。</span><span class="sxs-lookup"><span data-stu-id="619eb-124">Specifies the version number of the event.</span></span> <span data-ttu-id="619eb-125">键入事件数。</span><span class="sxs-lookup"><span data-stu-id="619eb-125">Type the event number.</span></span> <span data-ttu-id="619eb-126">PowerShell 将数字转换为所需的字节类型。</span><span class="sxs-lookup"><span data-stu-id="619eb-126">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="619eb-127">如果为同一事件定义了不同版本，则可以使用此参数指定事件。</span><span class="sxs-lookup"><span data-stu-id="619eb-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="619eb-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="619eb-128">CommonParameters</span></span>

<span data-ttu-id="619eb-129">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="619eb-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="619eb-130">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="619eb-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="619eb-131">输入</span><span class="sxs-lookup"><span data-stu-id="619eb-131">INPUTS</span></span>

### <span data-ttu-id="619eb-132">无</span><span class="sxs-lookup"><span data-stu-id="619eb-132">None</span></span>

<span data-ttu-id="619eb-133">此 cmdlet 不通过管道接受输入。</span><span class="sxs-lookup"><span data-stu-id="619eb-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="619eb-134">输出</span><span class="sxs-lookup"><span data-stu-id="619eb-134">OUTPUTS</span></span>

### <span data-ttu-id="619eb-135">无</span><span class="sxs-lookup"><span data-stu-id="619eb-135">None</span></span>

<span data-ttu-id="619eb-136">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="619eb-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="619eb-137">注释</span><span class="sxs-lookup"><span data-stu-id="619eb-137">NOTES</span></span>

* <span data-ttu-id="619eb-138">在提供程序将甚至写入到 eventlog 后，可以使用 Get-WinEvent cmdlet 从事件日志中获取事件。</span><span class="sxs-lookup"><span data-stu-id="619eb-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="619eb-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="619eb-139">RELATED LINKS</span></span>

[<span data-ttu-id="619eb-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="619eb-140">Get-WinEvent</span></span>](Get-WinEvent.md)
