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
# <a name="events01-sample"></a>Events01 示例

此示例演示如何创建一个 cmdlet，该 cmdlet 允许用户注册 [FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)引发的事件。 使用此 cmdlet，用户可以注册在特定目录下创建文件时要执行的操作。 此示例是从 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基类派生的。

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>如何使用 Visual Studio 生成示例。

1. 安装 Windows PowerShell 2.0 SDK 后，导航到 Events01 文件夹。 默认位置为 `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`。

2. 双击解决方案的图标 ( .sln) 文件。 这会在 Microsoft Visual Studio 中打开示例项目。

3. 在“生成”菜单中选择“生成解决方案” 。 示例的库将在默认 `\bin` 或文件夹中生成 `\bin\debug` 。

### <a name="how-to-run-the-sample"></a>如何运行示例

1. 创建以下模块文件夹：

    `[user]/documents/windowspowershell/modules/events01`

2. 将示例的库文件复制到模块文件夹中。

3. 启动 Windows PowerShell。

4. 运行以下命令，将 cmdlet 加载到 Windows PowerShell：

    ```powershell
    import-module events01
    ```

5. 使用 Register-FileSystemEvent cmdlet 注册一个操作，该操作将在临时目录下创建文件时写入一条消息。

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. 在临时目录下创建文件，并注意 () 显示消息时执行操作。

这是通过执行以下步骤而产生的示例输出。

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

## <a name="requirements"></a>要求

此示例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>演示

此示例演示以下各项。

### <a name="how-to-write-a-cmdlet-for-event-registration"></a>如何为事件注册编写 cmdlet

该 cmdlet 派生自 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 类，该类提供对 cmdlet 的通用参数的支持 `Register-*Event` 。 派生自 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 的 cmdlet 只需定义其特定参数并重写 `GetSourceObject` 和 `GetSourceObjectEventName` 抽象方法。

## <a name="example"></a>示例

此示例演示如何注册 [FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)引发的事件。

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

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](writing-a-windows-powershell-cmdlet.md)
