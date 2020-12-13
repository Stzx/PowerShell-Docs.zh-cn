---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 提供程序快速入门
description: Windows PowerShell 提供程序快速入门
ms.openlocfilehash: f0fe0ad60e9d10efd505cda60af995c597226b92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664351"
---
# <a name="windows-powershell-provider-quickstart"></a><span data-ttu-id="8e0d1-103">Windows PowerShell 提供程序快速入门</span><span class="sxs-lookup"><span data-stu-id="8e0d1-103">Windows PowerShell Provider Quickstart</span></span>

<span data-ttu-id="8e0d1-104">本主题说明如何创建具有创建新驱动器的基本功能的 Windows PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-104">This topic explains how to create a Windows PowerShell provider that has basic functionality of creating a new drive.</span></span> <span data-ttu-id="8e0d1-105">有关提供程序的一般信息，请参阅 [Windows PowerShell 提供程序概述](./windows-powershell-provider-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-105">For general information about providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="8e0d1-106">有关具有更完整功能的提供程序的示例，请参阅 [提供程序示例](./provider-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-106">For examples of providers with more complete functionality, see [Provider Samples](./provider-samples.md).</span></span>

## <a name="writing-a-basic-provider"></a><span data-ttu-id="8e0d1-107">编写基本提供程序</span><span class="sxs-lookup"><span data-stu-id="8e0d1-107">Writing a basic provider</span></span>

<span data-ttu-id="8e0d1-108">Windows PowerShell 提供程序的最基本功能是创建和删除驱动器。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-108">The most basic functionality of a Windows PowerShell provider is to create and remove drives.</span></span> <span data-ttu-id="8e0d1-109">在此示例中，我们[实现了 Drivecmdletprovider 类的](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)Newdrive \* 和[Drivecmdletprovider.. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法的实例的[\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)和管理器类的方法。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-109">In this example, we implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="8e0d1-110">你还将了解如何声明提供程序类。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-110">You will also see how to declare a provider class.</span></span>

<span data-ttu-id="8e0d1-111">当你编写提供程序时，可以指定默认驱动器-在提供程序可用时自动创建的驱动器。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-111">When you write a provider, you can specify default drives-drives that are created automatically when the provider is available.</span></span> <span data-ttu-id="8e0d1-112">还定义了一个方法来创建使用该提供程序的新驱动器。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-112">You also define a method to create new drives that use that provider.</span></span>

<span data-ttu-id="8e0d1-113">本主题中提供的示例基于 [AccessDBProviderSample02](./accessdbprovidersample02.md) 示例，该示例是将 Access 数据库表示为 Windows PowerShell 驱动器的更大示例的一部分。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-113">The examples provided in this topic are based on the [AccessDBProviderSample02](./accessdbprovidersample02.md) sample, which is part of a larger sample that represents an Access database as a Windows PowerShell drive.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="8e0d1-114">设置项目</span><span class="sxs-lookup"><span data-stu-id="8e0d1-114">Setting up the project</span></span>

<span data-ttu-id="8e0d1-115">在 Visual Studio 中，创建一个名为 AccessDBProviderSample 的类库项目。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-115">In Visual Studio, create a Class Library project named AccessDBProviderSample.</span></span> <span data-ttu-id="8e0d1-116">完成以下步骤以配置你的项目，以便在生成和启动项目时，将启动 Windows PowerShell 并将该提供程序加载到会话中。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-116">Complete the following steps to configure your project so that Windows PowerShell will start, and the provider will be loaded into the session, when you build and start your project.</span></span>

##### <a name="configure-the-provider-project"></a><span data-ttu-id="8e0d1-117">配置提供程序项目</span><span class="sxs-lookup"><span data-stu-id="8e0d1-117">Configure the provider project</span></span>

1. <span data-ttu-id="8e0d1-118">添加 System.web 程序集作为对项目的引用。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-118">Add the System.Management.Automation assembly as a reference to your project.</span></span>

2. <span data-ttu-id="8e0d1-119">单击 " **项目 > AccessDBProviderSample Properties > 调试**"。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-119">Click **Project > AccessDBProviderSample Properties > Debug**.</span></span> <span data-ttu-id="8e0d1-120">在 " **启动项目**" 中，单击 " **启动外部程序**"，并导航到 Windows PowerShell 可执行文件 (通常为 c:\Windows\System32\WindowsPowerShell\v1.0 \\.powershell.exe) 。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-120">In **Start project**, click **Start external program**, and navigate to the Windows PowerShell executable (typically c:\Windows\System32\WindowsPowerShell\v1.0\\.powershell.exe).</span></span>

3. <span data-ttu-id="8e0d1-121">在 " **启动选项**" 下的 " **命令行参数** " 框中输入以下内容： `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span><span class="sxs-lookup"><span data-stu-id="8e0d1-121">Under **Start Options**, enter the following into the **Command line arguments** box: `-noexit -command "[reflection.assembly]::loadFrom(AccessDBProviderSample.dll' ) | import-module"`</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="8e0d1-122">声明提供程序类</span><span class="sxs-lookup"><span data-stu-id="8e0d1-122">Declaring the provider class</span></span>

<span data-ttu-id="8e0d1-123">我们的提供程序派生自 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 类。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-123">Our provider derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class.</span></span> <span data-ttu-id="8e0d1-124">大多数提供实际功能 (提供程序的提供程序，可用于访问和操作项、导航数据存储区，以及) 派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类的项的内容。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-124">Most providers that provide real functionality (accessing and manipulating items, navigating the data store, and getting and setting content of items) derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="8e0d1-125">除了指定类派生自[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)以外，你还必须将其与 Cmdletproviderattribute 中所示的[](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)修饰，如示例中所示。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-125">In addition to specifying that the class derives from [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider), you must decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) as shown in the example.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System;
  using System.Data;
  using System.Data.Odbc;
  using System.IO;
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  #region AccessDBProvider

  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : DriveCmdletProvider
  {

}
}
```

### <a name="implementing-newdrive"></a><span data-ttu-id="8e0d1-126">实现 NewDrive</span><span class="sxs-lookup"><span data-stu-id="8e0d1-126">Implementing NewDrive</span></span>

<span data-ttu-id="8e0d1-127">当用户调用[NewPSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand) cmdlet 指定提供程序的名称时，Windows PowerShell 引擎将调用[Drivecmdletprovider. Newdrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)方法，此方法由 Windows PowerShell 引擎调用。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-127">The [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.NewPSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.Newpsdrivecommand) cmdlet specifying the name of your provider.</span></span> <span data-ttu-id="8e0d1-128">即 system.management.automation.psdriveinfo 参数由 Windows PowerShell 引擎传递，方法会将新驱动器返回给 Windows PowerShell 引擎。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-128">The PSDriveInfo parameter is passed by the Windows PowerShell engine, and the method returns the new drive to the Windows PowerShell engine.</span></span> <span data-ttu-id="8e0d1-129">此方法必须在上面创建的类中声明。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-129">This method must be declared within the class created above.</span></span>

<span data-ttu-id="8e0d1-130">此方法首先检查以确保传入的驱动器对象和驱动器根都存在，如果不存在，则返回 `null` 。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-130">The method first checks to make sure both the drive object and the drive root that were passed in exist, returning `null` if either of them do not.</span></span> <span data-ttu-id="8e0d1-131">然后，它使用内部类 AccessDBPSDriveInfo 的构造函数来创建新的驱动器以及与该驱动器表示的 Access 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-131">It then uses a constructor of the internal class AccessDBPSDriveInfo to create a new drive and a connection to the Access database the drive represents.</span></span>

```csharp
protected override PSDriveInfo NewDrive(PSDriveInfo drive)
    {
      // Check if the drive object is null.
      if (drive == null)
      {
        WriteError(new ErrorRecord(
                   new ArgumentNullException("drive"),
                   "NullDrive",
                   ErrorCategory.InvalidArgument,
                   null));

        return null;
      }

      // Check if the drive root is not null or empty
      // and if it is an existing file.
      if (String.IsNullOrEmpty(drive.Root) || (File.Exists(drive.Root) == false))
      {
        WriteError(new ErrorRecord(
                   new ArgumentException("drive.Root"),
                   "NoRoot",
                   ErrorCategory.InvalidArgument,
                   drive));

        return null;
      }

      // Create a new drive and create an ODBC connection to the new drive.
      AccessDBPSDriveInfo accessDBPSDriveInfo = new AccessDBPSDriveInfo(drive);
      OdbcConnectionStringBuilder builder = new OdbcConnectionStringBuilder();

      builder.Driver = "Microsoft Access Driver (*.mdb)";
      builder.Add("DBQ", drive.Root);

      OdbcConnection conn = new OdbcConnection(builder.ConnectionString);
      conn.Open();
      accessDBPSDriveInfo.Connection = conn;

      return accessDBPSDriveInfo;
    }
```

<span data-ttu-id="8e0d1-132">下面是 AccessDBPSDriveInfo 内部类，其中包含用于创建新驱动器的构造函数，并包含驱动器的状态信息。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-132">The following is the AccessDBPSDriveInfo internal class that includes the constructor used to create a new drive, and contains the state information for the drive.</span></span>

```csharp
internal class AccessDBPSDriveInfo : PSDriveInfo
  {
    /// <summary>
    /// A reference to the connection to the database.
    /// </summary>
    private OdbcConnection connection;

    /// <summary>
    /// Initializes a new instance of the AccessDBPSDriveInfo class.
    /// The constructor takes a single argument.
    /// </summary>
    /// <param name="driveInfo">Drive defined by this provider</param>
    public AccessDBPSDriveInfo(PSDriveInfo driveInfo)
           : base(driveInfo)
    {
    }

    /// <summary>
    /// Gets or sets the ODBC connection information.
    /// </summary>
    public OdbcConnection Connection
    {
        get { return this.connection; }
        set { this.connection = value; }
    }
  }
```

### <a name="implementing-removedrive"></a><span data-ttu-id="8e0d1-133">实现 RemoveDrive</span><span class="sxs-lookup"><span data-stu-id="8e0d1-133">Implementing RemoveDrive</span></span>

<span data-ttu-id="8e0d1-134">当用户调用[RemovePSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand) cmdlet 时，Windows PowerShell 引擎将调用[Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法，这是由 Windows PowerShell 引擎调用的。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-134">The [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method is called by the Windows PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.RemovePSDriveCommand](/dotnet/api/Microsoft.PowerShell.Commands.removepsdrivecommand) cmdlet.</span></span> <span data-ttu-id="8e0d1-135">此提供程序中的方法关闭了到 Access 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="8e0d1-135">The method in this provider closes the connection to the Access database.</span></span>

```csharp
protected override PSDriveInfo RemoveDrive(PSDriveInfo drive)
    {
      // Check if drive object is null.
      if (drive == null)
      {
        WriteError(new ErrorRecord(
                   new ArgumentNullException("drive"),
                   "NullDrive",
                   ErrorCategory.InvalidArgument,
                   drive));

        return null;
      }

      // Close the ODBC connection to the drive.
      AccessDBPSDriveInfo accessDBPSDriveInfo = drive as AccessDBPSDriveInfo;

      if (accessDBPSDriveInfo == null)
      {
         return null;
      }

      accessDBPSDriveInfo.Connection.Close();

      return accessDBPSDriveInfo;
    }
```
