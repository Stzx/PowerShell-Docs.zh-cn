---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 输出
description: Cmdlet 输出
ms.openlocfilehash: 37606e57d9dff3ed9fa25b2b99eb07efa0147127
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653252"
---
# <a name="cmdlet-output"></a><span data-ttu-id="a020f-103">Cmdlet 输出</span><span class="sxs-lookup"><span data-stu-id="a020f-103">Cmdlet Output</span></span>

<span data-ttu-id="a020f-104">本部分讨论 cmdlet 输出的类型，以及 cmdlet 可调用以生成输出（如错误消息和对象）的方法。</span><span class="sxs-lookup"><span data-stu-id="a020f-104">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="a020f-105">本节还介绍如何定义 cmdlet 返回的 .NET Framework 类型以及这些对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a020f-105">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a020f-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="a020f-106">In This Section</span></span>

<span data-ttu-id="a020f-107">[Cmdlet 输出的类型](./types-of-cmdlet-output.md) 介绍 cmdlet 可以生成的类型和输出，以及 cmdlet 调用以生成输出的方法。</span><span class="sxs-lookup"><span data-stu-id="a020f-107">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="a020f-108">[Cmdlet 错误报告](./cmdlet-error-reporting.md) 讨论 cmdlet 错误报告，这是 cmdlet 输出的子集。</span><span class="sxs-lookup"><span data-stu-id="a020f-108">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="a020f-109">[扩展输出对象](./extending-output-objects.md) 讨论如何使用类型文件 () 来扩展由 cmdlet、函数和脚本返回的 .NET Framework 对象。</span><span class="sxs-lookup"><span data-stu-id="a020f-109">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="a020f-110">[PowerShell 格式化文件](../format/powershell-formatting-files.md) 介绍 ( # B0 xml) 文件的格式设置文件，这些文件定义了 Windows PowerShell 中一组特定 .NET Framework 对象的默认显示。</span><span class="sxs-lookup"><span data-stu-id="a020f-110">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="a020f-111">[自定义格式设置文件](./custom-formatting-files.md) 描述如何创建您自己的自定义格式设置文件以覆盖默认显示格式或定义您自己的命令返回的对象的显示。</span><span class="sxs-lookup"><span data-stu-id="a020f-111">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="a020f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a020f-112">See Also</span></span>

[<span data-ttu-id="a020f-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a020f-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
