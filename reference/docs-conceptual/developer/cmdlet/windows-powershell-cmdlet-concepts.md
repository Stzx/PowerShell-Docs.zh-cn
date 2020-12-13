---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell Cmdlet 概念
description: Windows PowerShell Cmdlet 概念
ms.openlocfilehash: da34d3d229f6d57ee22d84fc024b31eb2ee27ba3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652520"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="2078c-103">Windows PowerShell Cmdlet 概念</span><span class="sxs-lookup"><span data-stu-id="2078c-103">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="2078c-104">本部分介绍 cmdlet 的工作原理。</span><span class="sxs-lookup"><span data-stu-id="2078c-104">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2078c-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2078c-105">In This Section</span></span>

<span data-ttu-id="2078c-106">本部分包括以下主题。</span><span class="sxs-lookup"><span data-stu-id="2078c-106">This section includes the following topics.</span></span>

<span data-ttu-id="2078c-107">[Cmdlet 开发指南](./cmdlet-development-guidelines.md) 本主题提供可用于生成格式正确的 cmdlet 的开发指南。</span><span class="sxs-lookup"><span data-stu-id="2078c-107">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="2078c-108">[Cmdlet 类声明](./cmdlet-class-declaration.md) 本主题介绍 cmdlet 类声明。</span><span class="sxs-lookup"><span data-stu-id="2078c-108">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="2078c-109">[Windows PowerShell 命令的批准的谓词](./approved-verbs-for-windows-powershell-commands.md) 本主题列出了在声明 cmdlet 类时可以使用的预定义 cmdlet 谓词。</span><span class="sxs-lookup"><span data-stu-id="2078c-109">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="2078c-110">[Cmdlet 输入处理方法](./cmdlet-input-processing-methods.md) 本主题介绍允许 cmdlet 执行预处理操作、输入处理操作和后处理操作的方法。</span><span class="sxs-lookup"><span data-stu-id="2078c-110">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="2078c-111">[Cmdlet 参数](./cmdlet-parameters.md) 本部分介绍可添加到 cmdlet 的不同类型的参数。</span><span class="sxs-lookup"><span data-stu-id="2078c-111">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="2078c-112">[Cmdlet 属性](./cmdlet-attributes.md) 本部分介绍用于将 .NET Framework 类声明为 cmdlet、将字段声明为 cmdlet 参数以及为参数声明输入验证规则的属性。</span><span class="sxs-lookup"><span data-stu-id="2078c-112">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="2078c-113">[Cmdlet 别名](./cmdlet-aliases.md) 本主题介绍 cmdlet 别名。</span><span class="sxs-lookup"><span data-stu-id="2078c-113">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="2078c-114">[Cmdlet 输出](./cmdlet-output.md) 本部分介绍 cmdlet 可以返回的输出的类型，以及如何定义和显示由 cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="2078c-114">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="2078c-115">[注册 cmdlet](./modules-and-snap-ins.md) 本部分介绍如何使用模块和管理单元注册 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2078c-115">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="2078c-116">[请求确认](./requesting-confirmation-from-cmdlets.md) 本部分介绍了在用户更改系统之前，cmdlet 如何请求用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="2078c-116">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="2078c-117">[Windows PowerShell 错误报告](./error-reporting-concepts.md) 本节介绍 cmdlet 如何报告终止错误和非终止错误，并说明如何解释错误记录。</span><span class="sxs-lookup"><span data-stu-id="2078c-117">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="2078c-118">[后台作业](./background-jobs.md) 本主题介绍如何在不影响当前会话中执行的命令的后台作业中执行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2078c-118">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="2078c-119">[在 Cmdlet 中调用 cmdlet 和脚本](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) 本主题介绍了 cmdlet 如何从其输入处理方法中调用其他 cmdlet 和脚本。</span><span class="sxs-lookup"><span data-stu-id="2078c-119">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="2078c-120">[Cmdlet 集](./cmdlet-sets.md) 本主题介绍如何使用基类创建 cmdlet 集。</span><span class="sxs-lookup"><span data-stu-id="2078c-120">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="2078c-121">[Windows PowerShell 会话状态](./windows-powershell-session-state.md) 本主题介绍 Windows PowerShell 会话状态。</span><span class="sxs-lookup"><span data-stu-id="2078c-121">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
