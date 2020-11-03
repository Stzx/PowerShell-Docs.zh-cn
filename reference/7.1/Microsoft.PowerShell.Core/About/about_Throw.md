---
description: 介绍 Throw 关键字，用于生成终止错误。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: d4bf0ea00145c03522d4db952be201c877c9d50c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200148"
---
# <a name="about-throw"></a><span data-ttu-id="8cf74-104">关于 Throw</span><span class="sxs-lookup"><span data-stu-id="8cf74-104">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="8cf74-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="8cf74-105">Short description</span></span>
<span data-ttu-id="8cf74-106">介绍 Throw 关键字，用于生成终止错误。</span><span class="sxs-lookup"><span data-stu-id="8cf74-106">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="8cf74-107">长说明</span><span class="sxs-lookup"><span data-stu-id="8cf74-107">Long description</span></span>

<span data-ttu-id="8cf74-108">Throw 关键字导致终止错误。</span><span class="sxs-lookup"><span data-stu-id="8cf74-108">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="8cf74-109">可以使用 Throw 关键字停止对命令、函数或脚本的处理。</span><span class="sxs-lookup"><span data-stu-id="8cf74-109">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="8cf74-110">例如，可以在 If 语句的脚本块中使用 Throw 关键字来响应某个条件，或在 try-catch Finally 语句的 Catch 块中使用 Throw 关键字。</span><span class="sxs-lookup"><span data-stu-id="8cf74-110">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="8cf74-111">还可以在参数声明中使用 Throw 关键字，使函数参数成为必需的。</span><span class="sxs-lookup"><span data-stu-id="8cf74-111">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="8cf74-112">Throw 关键字可以引发任何对象，例如用户消息字符串或导致错误的对象。</span><span class="sxs-lookup"><span data-stu-id="8cf74-112">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="8cf74-113">语法</span><span class="sxs-lookup"><span data-stu-id="8cf74-113">Syntax</span></span>

<span data-ttu-id="8cf74-114">Throw 关键字的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="8cf74-114">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="8cf74-115">Throw 语法中的表达式是可选的。</span><span class="sxs-lookup"><span data-stu-id="8cf74-115">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="8cf74-116">如果 Throw 语句未出现在 Catch 块中，并且它不包含表达式，则会生成一个 ScriptHalted 错误。</span><span class="sxs-lookup"><span data-stu-id="8cf74-116">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

Exception: ScriptHalted
```

<span data-ttu-id="8cf74-117">如果在没有表达式的 Catch 块中使用 Throw 关键字，将再次引发当前的 RuntimeException。</span><span class="sxs-lookup"><span data-stu-id="8cf74-117">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="8cf74-118">有关详细信息，请参阅 about_Try_Catch_Finally。</span><span class="sxs-lookup"><span data-stu-id="8cf74-118">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="8cf74-119">引发字符串</span><span class="sxs-lookup"><span data-stu-id="8cf74-119">Throwing a string</span></span>

<span data-ttu-id="8cf74-120">Throw 语句中的可选表达式可以是字符串，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8cf74-120">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="8cf74-121">引发其他对象</span><span class="sxs-lookup"><span data-stu-id="8cf74-121">Throwing other objects</span></span>

<span data-ttu-id="8cf74-122">表达式还可以是一个对象，该对象引发表示 PowerShell 进程的对象，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8cf74-122">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

<span data-ttu-id="8cf74-123">您可以使用 $error 自动变量中 ErrorRecord 对象的 TargetObject 属性来检查错误。</span><span class="sxs-lookup"><span data-stu-id="8cf74-123">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

<span data-ttu-id="8cf74-124">还可以引发 ErrorRecord 对象或 .NET 异常。</span><span class="sxs-lookup"><span data-stu-id="8cf74-124">You can also throw an ErrorRecord object or a .NET exception.</span></span> <span data-ttu-id="8cf74-125">下面的示例使用 Throw 关键字来引发 FormatException 对象。</span><span class="sxs-lookup"><span data-stu-id="8cf74-125">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a><span data-ttu-id="8cf74-126">产生的错误</span><span class="sxs-lookup"><span data-stu-id="8cf74-126">The resulting error</span></span>

<span data-ttu-id="8cf74-127">Throw 关键字可以生成 ErrorRecord 对象。</span><span class="sxs-lookup"><span data-stu-id="8cf74-127">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="8cf74-128">ErrorRecord 对象的 Exception 属性包含 RuntimeException 对象。</span><span class="sxs-lookup"><span data-stu-id="8cf74-128">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="8cf74-129">ErrorRecord 对象和 RuntimeException 对象的其余部分将与 Throw 关键字引发的对象不同。</span><span class="sxs-lookup"><span data-stu-id="8cf74-129">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="8cf74-130">RunTimeException 对象包装在 ErrorRecord 对象中，ErrorRecord 对象自动保存在 $Error 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="8cf74-130">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="8cf74-131">使用 Throw 创建强制参数</span><span class="sxs-lookup"><span data-stu-id="8cf74-131">Using Throw to create a mandatory parameter</span></span>

<span data-ttu-id="8cf74-132">不同于以前版本的 PowerShell，不要将 Throw 关键字用于参数验证。</span><span class="sxs-lookup"><span data-stu-id="8cf74-132">Unlike past versions of PowerShell, do not use the Throw keyword for parameter validation.</span></span> <span data-ttu-id="8cf74-133">请参阅 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) 。</span><span class="sxs-lookup"><span data-stu-id="8cf74-133">See [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) for the correct way.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cf74-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf74-134">See also</span></span>

- [<span data-ttu-id="8cf74-135">about_Break</span><span class="sxs-lookup"><span data-stu-id="8cf74-135">about_Break</span></span>](about_Break.md)
- [<span data-ttu-id="8cf74-136">about_Continue</span><span class="sxs-lookup"><span data-stu-id="8cf74-136">about_Continue</span></span>](about_Continue.md)
- [<span data-ttu-id="8cf74-137">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="8cf74-137">about_Scopes</span></span>](about_Scopes.md)
- [<span data-ttu-id="8cf74-138">about_Trap</span><span class="sxs-lookup"><span data-stu-id="8cf74-138">about_Trap</span></span>](about_Trap.md)
- [<span data-ttu-id="8cf74-139">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="8cf74-139">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
