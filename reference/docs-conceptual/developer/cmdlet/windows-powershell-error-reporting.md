---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 错误报告
description: Windows PowerShell 错误报告
ms.openlocfilehash: 438e3d96bf52d8ac1f770c0550ae49b356d616eb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650113"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="00b7b-103">Windows PowerShell 错误报告</span><span class="sxs-lookup"><span data-stu-id="00b7b-103">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="00b7b-104">本部分中的主题讨论了 cmdlet 报告错误的方式。</span><span class="sxs-lookup"><span data-stu-id="00b7b-104">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="00b7b-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="00b7b-105">In This Section</span></span>

<span data-ttu-id="00b7b-106">[错误报告概念](./error-reporting-concepts.md) 介绍 cmdlet 可用于报告错误的两种机制。</span><span class="sxs-lookup"><span data-stu-id="00b7b-106">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="00b7b-107">[终止错误](./terminating-errors.md) 描述用于报告终止错误的方法，在此方法中，可以从 cmdlet 内调用此方法，并在调用方法时由 Windows PowerShell 运行时返回异常。</span><span class="sxs-lookup"><span data-stu-id="00b7b-107">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="00b7b-108">[非终止错误](./non-terminating-errors.md) 介绍用于报告非终止错误的方法，以及可以从 cmdlet 中调用该方法的位置。</span><span class="sxs-lookup"><span data-stu-id="00b7b-108">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="00b7b-109">[按类别显示错误信息](./displaying-error-information.md) 讨论用户显示错误的方式。</span><span class="sxs-lookup"><span data-stu-id="00b7b-109">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="00b7b-110">[Windows PowerShell 错误记录](./windows-powershell-error-records.md) 说明错误记录的组成部分。</span><span class="sxs-lookup"><span data-stu-id="00b7b-110">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="00b7b-111">[解释 ErrorRecord 对象](./interpreting-errorrecord-objects.md) 讨论如何解释 ErrorRecord 对象。</span><span class="sxs-lookup"><span data-stu-id="00b7b-111">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="00b7b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00b7b-112">See Also</span></span>

[<span data-ttu-id="00b7b-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="00b7b-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
