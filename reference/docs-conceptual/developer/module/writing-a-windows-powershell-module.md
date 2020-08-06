---
title: 编写 Windows PowerShell 模块 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d2398a8111a9832af2465d045be0bdefc3cf927a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779142"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="1093c-102">编写 Windows PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1093c-102">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="1093c-103">本文档针对需要打包和分发其 Windows PowerShell cmdlet 的管理员、脚本开发人员和 cmdlet 开发人员编写。</span><span class="sxs-lookup"><span data-stu-id="1093c-103">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1093c-104">通过使用 Windows PowerShell 模块，无需使用编译语言即可打包和分发 Windows PowerShell 解决方案。</span><span class="sxs-lookup"><span data-stu-id="1093c-104">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="1093c-105">使用 windows PowerShell 模块，可以将 Windows PowerShell 代码分区、组织和抽象到独立的可重用单元中。</span><span class="sxs-lookup"><span data-stu-id="1093c-105">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="1093c-106">使用这些可重用单元，可以轻松地与他人直接共享你的模块。</span><span class="sxs-lookup"><span data-stu-id="1093c-106">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="1093c-107">如果你是脚本开发人员，还可以重新打包第三方模块，以创建基于脚本的自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="1093c-107">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="1093c-108">模块与其他脚本编写语言（如 Perl 和 Python）中的模块相似，可实现使用可重用的可再发行组件的生产就绪脚本解决方案，并提供使你能够重新打包和抽象多个组件以创建自定义解决方案的优势。</span><span class="sxs-lookup"><span data-stu-id="1093c-108">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="1093c-109">在最基本的情况下，Windows PowerShell 会将 hbase-runner.psm1 文件中保存的任何有效的 Windows PowerShell 脚本代码视为模块。</span><span class="sxs-lookup"><span data-stu-id="1093c-109">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="1093c-110">PowerShell 还会将任何二进制 cmdlet 程序集自动视为模块。</span><span class="sxs-lookup"><span data-stu-id="1093c-110">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="1093c-111">不过，还可以使用模块 (或更具体地说，) 将整个解决方案捆绑在一起的模块清单。</span><span class="sxs-lookup"><span data-stu-id="1093c-111">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="1093c-112">以下方案介绍了 Windows PowerShell 模块的典型用法。</span><span class="sxs-lookup"><span data-stu-id="1093c-112">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="1093c-113">库</span><span class="sxs-lookup"><span data-stu-id="1093c-113">Libraries</span></span>

<span data-ttu-id="1093c-114">模块可用于打包和分发执行常见任务的具有相同功能的库。</span><span class="sxs-lookup"><span data-stu-id="1093c-114">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="1093c-115">通常情况下，这些函数的名称共享一个或多个名词，其中反映了它们所使用的常见任务。</span><span class="sxs-lookup"><span data-stu-id="1093c-115">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="1093c-116">这些函数也可以与 .NET Framework 类类似，因为它们可以拥有公共和私有成员。</span><span class="sxs-lookup"><span data-stu-id="1093c-116">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="1093c-117">例如，库可以包含一组用于文件传输的函数。</span><span class="sxs-lookup"><span data-stu-id="1093c-117">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="1093c-118">在这种情况下，反映常见任务的名词可能是 "file"。</span><span class="sxs-lookup"><span data-stu-id="1093c-118">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="1093c-119">配置</span><span class="sxs-lookup"><span data-stu-id="1093c-119">Configuration</span></span>

<span data-ttu-id="1093c-120">通过添加特定的 cmdlet、提供程序、函数和变量，可使用模块自定义环境。</span><span class="sxs-lookup"><span data-stu-id="1093c-120">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="1093c-121">编译的代码开发和分发</span><span class="sxs-lookup"><span data-stu-id="1093c-121">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="1093c-122">Cmdlet 和提供程序开发人员可以使用模块来测试和分发其已编译的代码，而无需创建管理单元。它们可以将包含已编译代码的程序集作为 (二进制模块的模块导入) ，而无需创建和注册管理单元。</span><span class="sxs-lookup"><span data-stu-id="1093c-122">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="1093c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1093c-123">See Also</span></span>

[<span data-ttu-id="1093c-124">了解 Windows PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1093c-124">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="1093c-125">如何编写 PowerShell 脚本模块</span><span class="sxs-lookup"><span data-stu-id="1093c-125">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="1093c-126">如何编写 PowerShell 二进制模块</span><span class="sxs-lookup"><span data-stu-id="1093c-126">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="1093c-127">如何编写 PowerShell 模块清单</span><span class="sxs-lookup"><span data-stu-id="1093c-127">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="1093c-128">修改 PSModulePath 安装路径</span><span class="sxs-lookup"><span data-stu-id="1093c-128">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="1093c-129">导入 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1093c-129">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="1093c-130">安装 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="1093c-130">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
