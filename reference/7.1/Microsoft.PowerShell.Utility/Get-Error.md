---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: c29115a65b46d38039d78b10eee293e6944cede5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197706"
---
# <span data-ttu-id="a4c29-103">Get-Error</span><span class="sxs-lookup"><span data-stu-id="a4c29-103">Get-Error</span></span>

## <span data-ttu-id="a4c29-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a4c29-104">SYNOPSIS</span></span>

<span data-ttu-id="a4c29-105">获取并显示当前会话中最近的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a4c29-105">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="a4c29-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4c29-106">SYNTAX</span></span>

### <span data-ttu-id="a4c29-107">最新 (默认值) </span><span class="sxs-lookup"><span data-stu-id="a4c29-107">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a4c29-108">错误</span><span class="sxs-lookup"><span data-stu-id="a4c29-108">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="a4c29-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a4c29-109">DESCRIPTION</span></span>

<span data-ttu-id="a4c29-110">该 `Get-Error` cmdlet 将获取一个 **PSExtendedError** 对象，该对象表示会话中发生的最后一个错误的当前错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4c29-110">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="a4c29-111">您可以使用 `Get-Error` 来显示在当前会话中使用 **最新** 参数发生的指定数量的错误。</span><span class="sxs-lookup"><span data-stu-id="a4c29-111">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="a4c29-112">该 `Get-Error` cmdlet 还从集合接收错误对象，例如 `$Error` ，用于显示当前会话中的多个错误。</span><span class="sxs-lookup"><span data-stu-id="a4c29-112">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="a4c29-113">示例</span><span class="sxs-lookup"><span data-stu-id="a4c29-113">EXAMPLES</span></span>

### <span data-ttu-id="a4c29-114">示例1：获取最新的错误详细信息</span><span class="sxs-lookup"><span data-stu-id="a4c29-114">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="a4c29-115">在此示例中， `Get-Error` 显示当前会话中发生的最新错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4c29-115">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### <span data-ttu-id="a4c29-116">示例2：获取当前会话中发生的指定数量的错误消息</span><span class="sxs-lookup"><span data-stu-id="a4c29-116">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="a4c29-117">此示例演示如何将 `Get-Error` 与 **最新** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="a4c29-117">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="a4c29-118">在此示例中， **最新** 返回此会话中发生的3个最新错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4c29-118">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="a4c29-119">示例3：发送错误集合以接收详细消息</span><span class="sxs-lookup"><span data-stu-id="a4c29-119">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="a4c29-120">`$Error`自动变量包含当前会话中的错误对象的数组。</span><span class="sxs-lookup"><span data-stu-id="a4c29-120">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="a4c29-121">可以通过管道将对象数组发送到 `Get-Error` ，以接收详细的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a4c29-121">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="a4c29-122">在此示例中， `$Error` 将通过管道传递给 `Get-Error` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4c29-122">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="a4c29-123">结果为详细的错误消息列表，类似于示例1的结果。</span><span class="sxs-lookup"><span data-stu-id="a4c29-123">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="a4c29-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4c29-124">PARAMETERS</span></span>

### <span data-ttu-id="a4c29-125">-Newest</span><span class="sxs-lookup"><span data-stu-id="a4c29-125">-Newest</span></span>

<span data-ttu-id="a4c29-126">指定当前会话中已发生的错误数。</span><span class="sxs-lookup"><span data-stu-id="a4c29-126">Specifies the number of errors to display that have occurred in the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4c29-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a4c29-127">-InputObject</span></span>

<span data-ttu-id="a4c29-128">此参数用于管道输入。</span><span class="sxs-lookup"><span data-stu-id="a4c29-128">This parameter is used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a4c29-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a4c29-129">CommonParameters</span></span>

<span data-ttu-id="a4c29-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a4c29-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4c29-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a4c29-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4c29-132">输入</span><span class="sxs-lookup"><span data-stu-id="a4c29-132">INPUTS</span></span>

### <span data-ttu-id="a4c29-133">PSObject</span><span class="sxs-lookup"><span data-stu-id="a4c29-133">PSObject</span></span>

<span data-ttu-id="a4c29-134">支持来自任何 **PSObject** 的输入，但结果不同，除非提供了 **ErrorRecord** 或 **Exception** 对象。</span><span class="sxs-lookup"><span data-stu-id="a4c29-134">Supports input from any **PSObject** , but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="a4c29-135">输出</span><span class="sxs-lookup"><span data-stu-id="a4c29-135">OUTPUTS</span></span>

### <span data-ttu-id="a4c29-136">ErrorRecord # PSExtendedError。</span><span class="sxs-lookup"><span data-stu-id="a4c29-136">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="a4c29-137">**PSExtendedError** 对象中的输出。</span><span class="sxs-lookup"><span data-stu-id="a4c29-137">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="a4c29-138">注释</span><span class="sxs-lookup"><span data-stu-id="a4c29-138">NOTES</span></span>

<span data-ttu-id="a4c29-139">`Get-Error` 接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="a4c29-139">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="a4c29-140">例如，`$Error | Get-Error`。</span><span class="sxs-lookup"><span data-stu-id="a4c29-140">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="a4c29-141">相关链接</span><span class="sxs-lookup"><span data-stu-id="a4c29-141">RELATED LINKS</span></span>

[<span data-ttu-id="a4c29-142">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="a4c29-142">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
