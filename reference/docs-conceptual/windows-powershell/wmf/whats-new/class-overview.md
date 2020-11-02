---
ms.date: 07/29/2020
title: PowerShell 5.0 中的新语言功能
description: PowerShell 5.0 添加了使用类似于其他面向对象的编程语言的语法和语义定义类和其他用户定义的类型的功能。
ms.openlocfilehash: 31ff54ba6f2800a0680c1a2db3832ca97246973d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663303"
---
# <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="3f270-103">PowerShell 5.0 中的新语言功能</span><span class="sxs-lookup"><span data-stu-id="3f270-103">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="3f270-104">PowerShell 5.0 添加了使用类似于其他面向对象的编程语言的语法和语义定义类和其他用户定义的类型的功能。</span><span class="sxs-lookup"><span data-stu-id="3f270-104">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="3f270-105">目标是使开发人员和 IT 专业人员在更广泛的用例中使用 PowerShell，从而简化 PowerShell 项目开发（如 DSC 资源），并加速覆盖管理面。</span><span class="sxs-lookup"><span data-stu-id="3f270-105">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

<span data-ttu-id="3f270-106">PowerShell 5.0 引入了以下 PowerShell 中的新语言元素：</span><span class="sxs-lookup"><span data-stu-id="3f270-106">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="3f270-107">Class 关键字</span><span class="sxs-lookup"><span data-stu-id="3f270-107">Class keyword</span></span>

<span data-ttu-id="3f270-108">`class` 关键字定义了一个新类。</span><span class="sxs-lookup"><span data-stu-id="3f270-108">The `class` keyword defines a new class.</span></span> <span data-ttu-id="3f270-109">这是真正的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="3f270-109">This is a true .NET Framework type.</span></span> <span data-ttu-id="3f270-110">Class 成员是公开的，但仅在模块作用域内公开。</span><span class="sxs-lookup"><span data-stu-id="3f270-110">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="3f270-111">不能引用类型名称作为字符串（例如，`New-Object` 不起作用），并且在此版本中，也不能在该类定义的脚本或模块文件外部使用类型文本（例如，`[MyClass]`）。</span><span class="sxs-lookup"><span data-stu-id="3f270-111">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="3f270-112">Enum 关键字和枚举</span><span class="sxs-lookup"><span data-stu-id="3f270-112">Enum keyword and enumerations</span></span>

<span data-ttu-id="3f270-113">已添加对 `enum` 关键字的支持，它使用换行符作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="3f270-113">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="3f270-114">当前，不能根据自身定义枚举器。</span><span class="sxs-lookup"><span data-stu-id="3f270-114">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="3f270-115">但是，可以根据一个枚举初始化另一个枚举，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3f270-115">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="3f270-116">此外，不能指定基类型；它始终是 `[int]`。</span><span class="sxs-lookup"><span data-stu-id="3f270-116">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="3f270-117">枚举器值必须是分析时间常量。</span><span class="sxs-lookup"><span data-stu-id="3f270-117">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="3f270-118">不能将其设置为调用命令的结果。</span><span class="sxs-lookup"><span data-stu-id="3f270-118">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="3f270-119">枚举支持算术运算，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3f270-119">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="3f270-120">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="3f270-120">Import-DscResource</span></span>

<span data-ttu-id="3f270-121">`Import-DscResource` 现在是一个真正的动态关键字。</span><span class="sxs-lookup"><span data-stu-id="3f270-121">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="3f270-122">PowerShell 用于分析指定的模块的根模块，搜索包含 DscResource 属性的类。</span><span class="sxs-lookup"><span data-stu-id="3f270-122">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="3f270-123">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="3f270-123">ImplementingAssembly</span></span>

<span data-ttu-id="3f270-124">已将新字段 ImplementingAssembly 添加到了 ModuleInfo。</span><span class="sxs-lookup"><span data-stu-id="3f270-124">A new field, **ImplementingAssembly** , has been added to **ModuleInfo** .</span></span> <span data-ttu-id="3f270-125">如果脚本模块定义类，或者二进制模块的加载程序集，则会将此字段设置为为脚本模块创建的动态程序集。</span><span class="sxs-lookup"><span data-stu-id="3f270-125">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="3f270-126">当 ModuleType  为 Manifest  时，不会对该字段进行设置。</span><span class="sxs-lookup"><span data-stu-id="3f270-126">It is not set when **ModuleType** is **Manifest** .</span></span>

<span data-ttu-id="3f270-127">**ImplementingAssembly** 字段上的反射可发现模块中的资源。</span><span class="sxs-lookup"><span data-stu-id="3f270-127">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="3f270-128">这意味着你可以发现用 PowerShell 或其他托管语言编写的资源。</span><span class="sxs-lookup"><span data-stu-id="3f270-128">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

## <a name="further-reading"></a><span data-ttu-id="3f270-129">其他阅读材料</span><span class="sxs-lookup"><span data-stu-id="3f270-129">Further reading</span></span>

- [<span data-ttu-id="3f270-130">about_Classes</span><span class="sxs-lookup"><span data-stu-id="3f270-130">about_Classes</span></span>](/powershell/module/microsoft.powershell.core/about/about_classes)
- [<span data-ttu-id="3f270-131">about_Enum</span><span class="sxs-lookup"><span data-stu-id="3f270-131">about_Enum</span></span>](/powershell/module/microsoft.powershell.core/about/about_enum)
- [<span data-ttu-id="3f270-132">about_Classes_and_DSC</span><span class="sxs-lookup"><span data-stu-id="3f270-132">about_Classes_and_DSC</span></span>](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
