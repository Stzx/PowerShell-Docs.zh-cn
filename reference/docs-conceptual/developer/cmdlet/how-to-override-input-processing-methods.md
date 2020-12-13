---
ms.date: 09/13/2016
ms.topic: reference
title: 如何替代输入处理方法
description: 如何替代输入处理方法
ms.openlocfilehash: 4e8d71a34a1480ce63435ac6cc5dce60d4219c03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667005"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="c8abe-103">如何替代输入处理方法</span><span class="sxs-lookup"><span data-stu-id="c8abe-103">How to Override Input Processing Methods</span></span>

<span data-ttu-id="c8abe-104">这些示例演示如何在 cmdlet 中覆盖输入处理方法。</span><span class="sxs-lookup"><span data-stu-id="c8abe-104">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="c8abe-105">这些方法用于执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c8abe-105">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="c8abe-106">[BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)方法用于执行对 Cmdlet 所处理的所有对象均有效的一次启动操作的启动操作。</span><span class="sxs-lookup"><span data-stu-id="c8abe-106">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="c8abe-107">Windows PowerShell 运行时只调用一次此方法。</span><span class="sxs-lookup"><span data-stu-id="c8abe-107">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="c8abe-108">[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法用来处理传递给 Cmdlet 的对象。）。</span><span class="sxs-lookup"><span data-stu-id="c8abe-108">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="c8abe-109">Windows PowerShell 运行时为传递到 cmdlet 的每个对象调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c8abe-109">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="c8abe-110">使用的是一次后处理操作的 " [系统管理](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 程序" 方法。</span><span class="sxs-lookup"><span data-stu-id="c8abe-110">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="c8abe-111">Windows PowerShell 运行时只调用一次此方法。</span><span class="sxs-lookup"><span data-stu-id="c8abe-111">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="c8abe-112">重写 BeginProcessing 方法</span><span class="sxs-lookup"><span data-stu-id="c8abe-112">To override the BeginProcessing method</span></span>

- <span data-ttu-id="c8abe-113">声明一个受保护的 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 方法重写。</span><span class="sxs-lookup"><span data-stu-id="c8abe-113">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="c8abe-114">下面的类打印示例消息。</span><span class="sxs-lookup"><span data-stu-id="c8abe-114">The following class prints a sample message.</span></span> <span data-ttu-id="c8abe-115">若要使用此类，请更改 Cmdlet 属性中的动词和名词，更改类的名称以反映新的动词和名词，然后将所需的功能添加到 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 方法的重写。</span><span class="sxs-lookup"><span data-stu-id="c8abe-115">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="c8abe-116">重写 ProcessRecord 方法</span><span class="sxs-lookup"><span data-stu-id="c8abe-116">To override the ProcessRecord method</span></span>

- <span data-ttu-id="c8abe-117">声明一个受保护的 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法重写。</span><span class="sxs-lookup"><span data-stu-id="c8abe-117">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="c8abe-118">下面的类打印示例消息。</span><span class="sxs-lookup"><span data-stu-id="c8abe-118">The following class prints a sample message.</span></span> <span data-ttu-id="c8abe-119">若要使用此类，请更改 Cmdlet 属性中的动词和名词，更改类的名称以反映新的动词和名词，然后将所需的功能添加到 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法的重写。</span><span class="sxs-lookup"><span data-stu-id="c8abe-119">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="c8abe-120">重写 EndProcessing 方法</span><span class="sxs-lookup"><span data-stu-id="c8abe-120">To override the EndProcessing method</span></span>

- <span data-ttu-id="c8abe-121">声明一个受保护的 [system.web](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 方法重写。</span><span class="sxs-lookup"><span data-stu-id="c8abe-121">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="c8abe-122">下面的类输出示例。</span><span class="sxs-lookup"><span data-stu-id="c8abe-122">The following class prints a sample.</span></span> <span data-ttu-id="c8abe-123">若要使用此类，请更改 Cmdlet 特性中的谓词和名词，更改类的名称以反映新的动词和名词，然后将所需的功能添加到重[写的](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)</span><span class="sxs-lookup"><span data-stu-id="c8abe-123">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a><span data-ttu-id="c8abe-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8abe-124">See Also</span></span>

[<span data-ttu-id="c8abe-125">"BeginProcessing"。</span><span class="sxs-lookup"><span data-stu-id="c8abe-125">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="c8abe-126">System.web. EndProcessing. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="c8abe-126">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="c8abe-127">"ProcessRecord"。</span><span class="sxs-lookup"><span data-stu-id="c8abe-127">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="c8abe-128">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c8abe-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
