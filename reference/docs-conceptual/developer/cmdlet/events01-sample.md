---
ms.date: 09/13/2016
ms.topic: reference
title: Events01 示例
description: Events01 示例
ms.openlocfilehash: ed8b7903537504609602e27693351847d322f904
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390399"
---
# <a name="events01-sample"></a><span data-ttu-id="aad0b-103">Events01 示例</span><span class="sxs-lookup"><span data-stu-id="aad0b-103">Events01 Sample</span></span>

<span data-ttu-id="aad0b-104">此示例演示如何创建一个 cmdlet，该 cmdlet 允许用户注册 [FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)引发的事件。</span><span class="sxs-lookup"><span data-stu-id="aad0b-104">This sample shows how to create a cmdlet that allows the user to register for events that are raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="aad0b-105">使用此 cmdlet，用户可以注册在特定目录下创建文件时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="aad0b-105">With this cmdlet, users can register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="aad0b-106">此示例是从 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基类派生的。</span><span class="sxs-lookup"><span data-stu-id="aad0b-106">This sample derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="aad0b-107">如何使用 Visual Studio 生成示例。</span><span class="sxs-lookup"><span data-stu-id="aad0b-107">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="aad0b-108">安装 Windows PowerShell 2.0 SDK 后，导航到 Events01 文件夹。</span><span class="sxs-lookup"><span data-stu-id="aad0b-108">With the Windows PowerShell 2.0 SDK installed, navigate to the Events01 folder.</span></span> <span data-ttu-id="aad0b-109">默认位置为 `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`。</span><span class="sxs-lookup"><span data-stu-id="aad0b-109">The default location is `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`.</span></span>

2. <span data-ttu-id="aad0b-110">双击解决方案的图标 ( .sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="aad0b-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="aad0b-111">这会在 Microsoft Visual Studio 中打开示例项目。</span><span class="sxs-lookup"><span data-stu-id="aad0b-111">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="aad0b-112">在“生成”菜单中选择“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="aad0b-112">In the **Build** menu, select **Build Solution**.</span></span> <span data-ttu-id="aad0b-113">示例的库将在默认 `\bin` 或文件夹中生成 `\bin\debug` 。</span><span class="sxs-lookup"><span data-stu-id="aad0b-113">The library for the sample will be built in the default `\bin` or `\bin\debug` folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="aad0b-114">如何运行示例</span><span class="sxs-lookup"><span data-stu-id="aad0b-114">How to run the sample</span></span>

1. <span data-ttu-id="aad0b-115">创建以下模块文件夹：</span><span class="sxs-lookup"><span data-stu-id="aad0b-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/events01`

2. <span data-ttu-id="aad0b-116">将示例的库文件复制到模块文件夹中。</span><span class="sxs-lookup"><span data-stu-id="aad0b-116">Copy the library file for the sample to the module folder.</span></span>

3. <span data-ttu-id="aad0b-117">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="aad0b-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="aad0b-118">运行以下命令，将 cmdlet 加载到 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="aad0b-118">Run the following command to load the cmdlet into Windows PowerShell:</span></span>

    ```powershell
    import-module events01
    ```

5. <span data-ttu-id="aad0b-119">使用 Register-FileSystemEvent cmdlet 注册一个操作，该操作将在临时目录下创建文件时写入一条消息。</span><span class="sxs-lookup"><span data-stu-id="aad0b-119">Use the Register-FileSystemEvent cmdlet to register an action that will write a message when a file is created under the TEMP directory.</span></span>

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. <span data-ttu-id="aad0b-120">在临时目录下创建文件，并注意 () 显示消息时执行操作。</span><span class="sxs-lookup"><span data-stu-id="aad0b-120">Create a file under the TEMP directory and note that the action is executed (the message is displayed).</span></span>

<span data-ttu-id="aad0b-121">这是通过执行以下步骤而产生的示例输出。</span><span class="sxs-lookup"><span data-stu-id="aad0b-121">This is a sample output that results by following these steps.</span></span>

```output
Id              Name            State      HasMoreData     Location             Command
--              ----            -----      -----------     --------             -------
1               26932870-d3b... NotStarted False                                 Write-Host "A f...

```

```powershell
Set-Content $env:temp\test.txt "This is a test file"
```

```output
A file was created in the TEMP directory
```

## <a name="requirements"></a><span data-ttu-id="aad0b-122">要求</span><span class="sxs-lookup"><span data-stu-id="aad0b-122">Requirements</span></span>

<span data-ttu-id="aad0b-123">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="aad0b-123">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="aad0b-124">演示</span><span class="sxs-lookup"><span data-stu-id="aad0b-124">Demonstrates</span></span>

<span data-ttu-id="aad0b-125">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="aad0b-125">This sample demonstrates the following.</span></span>

### <a name="how-to-write-a-cmdlet-for-event-registration"></a><span data-ttu-id="aad0b-126">如何为事件注册编写 cmdlet</span><span class="sxs-lookup"><span data-stu-id="aad0b-126">How to write a cmdlet for event registration</span></span>

<span data-ttu-id="aad0b-127">该 cmdlet 派生自 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 类，该类提供对 cmdlet 的通用参数的支持 `Register-*Event` 。</span><span class="sxs-lookup"><span data-stu-id="aad0b-127">The cmdlet derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) class, which provides support for parameters common to the `Register-*Event` cmdlets.</span></span> <span data-ttu-id="aad0b-128">派生自 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 的 cmdlet 只需定义其特定参数并重写 `GetSourceObject` 和 `GetSourceObjectEventName` 抽象方法。</span><span class="sxs-lookup"><span data-stu-id="aad0b-128">Cmdlets that are derived from [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) need only to define their particular parameters and override the `GetSourceObject` and `GetSourceObjectEventName` abstract methods.</span></span>

## <a name="example"></a><span data-ttu-id="aad0b-129">示例</span><span class="sxs-lookup"><span data-stu-id="aad0b-129">Example</span></span>

<span data-ttu-id="aad0b-130">此示例演示如何注册 [FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)引发的事件。</span><span class="sxs-lookup"><span data-stu-id="aad0b-130">This sample shows how to register for events raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span>

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="aad0b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aad0b-131">See Also</span></span>

[<span data-ttu-id="aad0b-132">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aad0b-132">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
