---
ms.date: 09/13/2016
ms.topic: reference
title: RemoteRunspace01 示例
description: RemoteRunspace01 示例
ms.openlocfilehash: 13c6213089700e779eb185fe48a67c1616fad437
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658024"
---
# <a name="remoterunspace01-sample"></a><span data-ttu-id="08c5b-103">RemoteRunspace01 示例</span><span class="sxs-lookup"><span data-stu-id="08c5b-103">RemoteRunspace01 Sample</span></span>

<span data-ttu-id="08c5b-104">此示例演示如何创建用于建立远程连接的远程运行空间。</span><span class="sxs-lookup"><span data-stu-id="08c5b-104">This sample shows how to create a remote runspace that is used to establish a remote connection.</span></span>

## <a name="requirements"></a><span data-ttu-id="08c5b-105">要求</span><span class="sxs-lookup"><span data-stu-id="08c5b-105">Requirements</span></span>

 <span data-ttu-id="08c5b-106">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="08c5b-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="08c5b-107">演示</span><span class="sxs-lookup"><span data-stu-id="08c5b-107">Demonstrates</span></span>

- <span data-ttu-id="08c5b-108">正在创建一个 [Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="08c5b-108">Creating a [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object.</span></span>

- <span data-ttu-id="08c5b-109">设置 Runspaceconnectioninfo 对象的 [Operationtimeout \* 和 \*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OperationTimeout) 和 [Runspaceconnectioninfo.. Opentimeout \*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OpenTimeout) 属性的其他 [对象的属性](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) 的对象的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="08c5b-109">Setting the [System.Management.Automation.Runspaces.Runspaceconnectioninfo.Operationtimeout\*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OperationTimeout) and [System.Management.Automation.Runspaces.Runspaceconnectioninfo.Opentimeout\*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OpenTimeout) properties of the [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object.</span></span>

- <span data-ttu-id="08c5b-110">创建一个使用 [Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) 对象的远程运行空间来建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="08c5b-110">Creating a remote runspace that uses the [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object to establish the remote connection.</span></span>

- <span data-ttu-id="08c5b-111">关闭远程运行空间以释放远程连接。</span><span class="sxs-lookup"><span data-stu-id="08c5b-111">Closing the remote runspace to release the remote connection.</span></span>

## <a name="example"></a><span data-ttu-id="08c5b-112">示例</span><span class="sxs-lookup"><span data-stu-id="08c5b-112">Example</span></span>

<span data-ttu-id="08c5b-113">此示例定义了一个远程连接，然后使用该连接信息建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="08c5b-113">This sample defines a remote connection and then uses that connection information to establish a remote connection.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;             // Windows PowerShell namespace.
  using System.Management.Automation.Runspaces;   // Windows PowerShell namespace.

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class RemoteRunspace01
  {
    /// <summary>
    /// This sample shows how to use a WSManConnectionInfo object to set
    /// various timeouts and how to establish a remote connection.
    /// </summary>
    /// <param name="args">This parameter is not used.</param>
    public static void Main(string[] args)
    {
      // Create a WSManConnectionInfo object using the default constructor
      // to connect to the "localHost". The WSManConnectionInfo object can
      // also specify connections to remote computers.
      WSManConnectionInfo connectionInfo = new WSManConnectionInfo();

      // Set the OperationTimeout property. The OperationTimeout is used to tell
      // Windows PowerShell how long to wait (in milliseconds) before timing out
      // for any operation. This includes sending input data to the remote computer,
      // receiving output data from the remote computer, and more. The user can
      // change this timeout depending on whether the connection is to a computer
      // in the data center or across a slow WAN.
      connectionInfo.OperationTimeout = 4 * 60 * 1000; // 4 minutes.

      // Set the OpenTimeout property. OpenTimeout is used to tell Windows PowerShell
      // how long to wait (in milliseconds) before timing out while establishing a
      // remote connection. The user can change this timeout depending on whether the
      // connection is to a computer in the data center or across a slow WAN.
      connectionInfo.OpenTimeout = 1 * 60 * 1000; // 1 minute.

      // Create a remote runspace using the connection information.
      using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace(connectionInfo))
      {
        // Establish the connection by calling the Open() method to open the runspace.
        // The OpenTimeout value set previously will be applied while establishing
        // the connection. Establishing a remote connection involves sending and
        // receiving some data, so the OperationTimeout will also play a role in this process.
        remoteRunspace.Open();

        // Add the code to run commands in the remote runspace here. The
        // OperationTimeout value set previously will play a role here because
        // running commands involves sending and receiving data.

        // Close the connection. Call the Close() method to close the remote
        // runspace. The Dispose() method (called by using primitive) will call
        // the Close() method if it is not already called.
        remoteRunspace.Close();
      }
    }
  }
}
```
