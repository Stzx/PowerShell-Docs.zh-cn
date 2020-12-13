---
ms.date: 09/13/2016
ms.topic: reference
title: 编写导航提供程序
description: 编写导航提供程序
ms.openlocfilehash: 3123672d3365c97714557bd0e72a6e444ac228a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355215"
---
# <a name="writing-a-navigation-provider"></a><span data-ttu-id="41162-103">编写导航提供程序</span><span class="sxs-lookup"><span data-stu-id="41162-103">Writing a navigation provider</span></span>

<span data-ttu-id="41162-104">本主题介绍如何实现支持嵌套容器 (多级别数据存储) 、移动项和相对路径）的 Windows PowerShell 提供程序的方法。</span><span class="sxs-lookup"><span data-stu-id="41162-104">This topic describes how to implement the methods of a Windows PowerShell provider that support nested containers (multi-level data stores), moving items, and relative paths.</span></span> <span data-ttu-id="41162-105">导航提供程序必须从 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类中派生。</span><span class="sxs-lookup"><span data-stu-id="41162-105">A navigation provider must derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="41162-106">本主题中的示例中的提供程序使用 Access 数据库作为其数据存储。</span><span class="sxs-lookup"><span data-stu-id="41162-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="41162-107">有几个帮助器方法和用于与数据库进行交互的类。</span><span class="sxs-lookup"><span data-stu-id="41162-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="41162-108">有关包含帮助程序方法的完整示例，请参阅 [AccessDBProviderSample05](./accessdbprovidersample05.md)。</span><span class="sxs-lookup"><span data-stu-id="41162-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>

<span data-ttu-id="41162-109">有关 Windows PowerShell 提供程序的详细信息，请参阅 [Windows Powershell 提供程序概述](./windows-powershell-provider-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="41162-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-navigation-methods"></a><span data-ttu-id="41162-110">实现导航方法</span><span class="sxs-lookup"><span data-stu-id="41162-110">Implementing navigation methods</span></span>

<span data-ttu-id="41162-111">[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类实现支持嵌套的容器、相对路径和移动项的方法。</span><span class="sxs-lookup"><span data-stu-id="41162-111">The [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class implements methods that support nested containers, relative paths, and moving items.</span></span> <span data-ttu-id="41162-112">有关这些方法的完整列表，请参阅 [NavigationCmdletProvider 方法](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods)。</span><span class="sxs-lookup"><span data-stu-id="41162-112">For a complete list of these methods, see [NavigationCmdletProvider Methods](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span></span>

> [!NOTE]
> <span data-ttu-id="41162-113">本主题以 [Windows PowerShell 提供程序快速入门](./windows-powershell-provider-quickstart.md)中的信息为基础。</span><span class="sxs-lookup"><span data-stu-id="41162-113">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="41162-114">本主题不包含有关如何设置提供程序项目的基本知识，或者如何实现从 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 类继承的方法，这些方法可创建和删除驱动器。</span><span class="sxs-lookup"><span data-stu-id="41162-114">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="41162-115">本主题还不介绍如何实现由 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 或 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) 类公开的方法的实现方法的实现方法的方法。</span><span class="sxs-lookup"><span data-stu-id="41162-115">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) or [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) classes.</span></span> <span data-ttu-id="41162-116">有关演示如何实现项 cmdlet 的示例，请参阅 [编写项提供程序](./writing-an-item-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="41162-116">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span> <span data-ttu-id="41162-117">有关演示如何实现容器 cmdlet 的示例，请参阅 [编写容器提供程序](./writing-a-container-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="41162-117">For an example that shows how to implement container cmdlets, see [Writing a container provider](./writing-a-container-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="41162-118">声明提供程序类</span><span class="sxs-lookup"><span data-stu-id="41162-118">Declaring the provider class</span></span>

<span data-ttu-id="41162-119">将提供程序声明为派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类，并将其与 [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)的修饰进行对其修饰。</span><span class="sxs-lookup"><span data-stu-id="41162-119">Declare the provider to derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a><span data-ttu-id="41162-120">实现 IsItemContainer</span><span class="sxs-lookup"><span data-stu-id="41162-120">Implementing IsItemContainer</span></span>

<span data-ttu-id="41162-121">[Navigationcmdletprovider. Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)方法用于检查指定路径处的项是否是一个容器。</span><span class="sxs-lookup"><span data-stu-id="41162-121">The [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method checks whether the item at the specified path is a container.</span></span>

```csharp
protected override bool IsItemContainer(string path)
      {
         if (PathIsDrive(path))
         {
             return true;
         }

         string[] pathChunks = ChunkPath(path);
         string tableName;
         int rowNumber;

         PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

         if (type == PathType.Table)
         {
            foreach (DatabaseTableInfo ti in GetTables())
            {
                if (string.Equals(ti.Name, tableName, StringComparison.OrdinalIgnoreCase))
                {
                    return true;
                }
            } // foreach (DatabaseTableInfo...
         } // if (pathChunks...

         return false;
      }
```

### <a name="implementing-getchildname"></a><span data-ttu-id="41162-122">实现 GetChildName</span><span class="sxs-lookup"><span data-stu-id="41162-122">Implementing GetChildName</span></span>

<span data-ttu-id="41162-123">[Navigationcmdletprovider. Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)方法获取指定路径处的子项的 name 属性的名称。</span><span class="sxs-lookup"><span data-stu-id="41162-123">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method gets the name property of the child item at the specified path.</span></span> <span data-ttu-id="41162-124">如果指定路径处的项不是容器的子级，则此方法应返回路径。</span><span class="sxs-lookup"><span data-stu-id="41162-124">If the item at the specified path is not a child of a container, then this method should return the path.</span></span>

```csharp
protected override string GetChildName(string path)
       {
           if (PathIsDrive(path))
           {
               return path;
           }

           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               return tableName;
           }
           else if (type == PathType.Row)
           {
               return rowNumber.ToString(CultureInfo.CurrentCulture);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

           return null;
       }
```

### <a name="implementing-getparentpath"></a><span data-ttu-id="41162-125">实现 GetParentPath</span><span class="sxs-lookup"><span data-stu-id="41162-125">Implementing GetParentPath</span></span>

<span data-ttu-id="41162-126">[Navigationcmdletprovider. Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)方法获取指定路径处的项的父项的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="41162-126">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method gets the path of the parent of the item at the specified path.</span></span> <span data-ttu-id="41162-127">如果指定路径中的项是数据存储区的根 (因此它没有父) ，则此方法应返回根路径。</span><span class="sxs-lookup"><span data-stu-id="41162-127">If the item at the specified path is the root of the data store (so it has no parent), then this method should return the root path.</span></span>

```csharp
protected override string GetParentPath(string path, string root)
       {
           // If root is specified then the path has to contain
           // the root. If not nothing should be returned
           if (!String.IsNullOrEmpty(root))
           {
               if (!path.Contains(root))
               {
                   return null;
               }
           }

           return path.Substring(0, path.LastIndexOf(pathSeparator, StringComparison.OrdinalIgnoreCase));
       }
```

### <a name="implementing-makepath"></a><span data-ttu-id="41162-128">实现 MakePath</span><span class="sxs-lookup"><span data-stu-id="41162-128">Implementing MakePath</span></span>

<span data-ttu-id="41162-129">[Navigationcmdletprovider. Makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法联接指定的父路径和指定的子路径以创建提供程序内部路径 (有关提供程序可以支持的路径类型的信息，请参阅[Windows PowerShell 提供程序概述](./windows-powershell-provider-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="41162-129">The [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method joins a specified parent path and a specified child path to create a provider-internal path (for information about path types that providers can support, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="41162-130">当用户调用 [JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) cmdlet 时，PowerShell 引擎将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="41162-130">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) cmdlet.</span></span>

```csharp
protected override string MakePath(string parent, string child)
       {
           string result;

           string normalParent = NormalizePath(parent);
           normalParent = RemoveDriveFromPath(normalParent);
           string normalChild = NormalizePath(child);
           normalChild = RemoveDriveFromPath(normalChild);

           if (String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               result = String.Empty;
           }
           else if (String.IsNullOrEmpty(normalParent) && !String.IsNullOrEmpty(normalChild))
           {
               result = normalChild;
           }
           else if (!String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               if (normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent;
               }
               else
               {
                   result = normalParent + pathSeparator;
               }
           } // else if (!String...
           else
           {
               if (!normalParent.Equals(String.Empty) &&
                   !normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent + pathSeparator;
               }
               else
               {
                   result = normalParent;
               }

               if (normalChild.StartsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result += normalChild.Substring(1);
               }
               else
               {
                   result += normalChild;
               }
           } // else

           return result;
       }
```

### <a name="implementing-normalizerelativepath"></a><span data-ttu-id="41162-131">实现 NormalizeRelativePath</span><span class="sxs-lookup"><span data-stu-id="41162-131">Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="41162-132">[Navigationcmdletprovider. Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)方法采用 `path` 和 `basepath` 参数，并返回一个与参数相对应的规范化路径，与 `path` `basepath` 参数相关。</span><span class="sxs-lookup"><span data-stu-id="41162-132">The [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method takes `path` and `basepath` parameters, and returns a normalized path that is equivalent to the `path` parameter and relative to the `basepath` parameter.</span></span>

```csharp
protected override string NormalizeRelativePath(string path,
                                                            string basepath)
       {
           // Normalize the paths first
           string normalPath = NormalizePath(path);
           normalPath = RemoveDriveFromPath(normalPath);
           string normalBasePath = NormalizePath(basepath);
           normalBasePath = RemoveDriveFromPath(normalBasePath);

           if (String.IsNullOrEmpty(normalBasePath))
           {
               return normalPath;
           }
           else
           {
               if (!normalPath.Contains(normalBasePath))
               {
                   return null;
               }

               return normalPath.Substring(normalBasePath.Length + pathSeparator.Length);
           }
       }
```

### <a name="implementing-moveitem"></a><span data-ttu-id="41162-133">实现 MoveItem</span><span class="sxs-lookup"><span data-stu-id="41162-133">Implementing MoveItem</span></span>

<span data-ttu-id="41162-134">[Navigationcmdletprovider. Moveitem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)方法将项从指定的路径移动到指定的目标路径。</span><span class="sxs-lookup"><span data-stu-id="41162-134">The [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method moves an item from the specified path to the specified destination path.</span></span> <span data-ttu-id="41162-135">当用户调用 [MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) cmdlet 时，PowerShell 引擎将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="41162-135">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) cmdlet.</span></span>

```csharp
protected override void MoveItem(string path, string destination)
       {
           // Get type, table name and rowNumber from the path
           string tableName, destTableName;
           int rowNumber, destRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           PathType destType = GetNamesFromPath(destination, out destTableName,
                                    out destRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (destType == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(destination);
           }

           if (type == PathType.Table)
           {
               ArgumentException e = new ArgumentException("Move not supported for tables");

               WriteError(new ErrorRecord(e, "MoveNotSupported",
                   ErrorCategory.InvalidArgument, path));

               throw e;
           }
           else
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               OdbcDataAdapter dda = GetAdapterForTable(destTableName);
               if (dda == null)
               {
                   return;
               }

               DataSet dds = GetDataSetForTable(dda, destTableName);
               DataTable destTable = GetDataTable(dds, destTableName);
               DataRow row = table.Rows[rowNumber];

               if (destType == PathType.Table)
               {
                   DataRow destRow = destTable.NewRow();

                   destRow.ItemArray = row.ItemArray;
               }
               else
               {
                   DataRow destRow = destTable.Rows[destRowNumber];

                   destRow.ItemArray = row.ItemArray;
               }

               // Update the changes
               if (ShouldProcess(path, "MoveItem"))
               {
                   WriteItemObject(row, path, false);
                   dda.Update(dds, destTableName);
               }
           }
       }
```

## <a name="see-also"></a><span data-ttu-id="41162-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41162-136">See Also</span></span>

[<span data-ttu-id="41162-137">编写容器提供程序</span><span class="sxs-lookup"><span data-stu-id="41162-137">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="41162-138">Windows PowerShell 提供程序概述</span><span class="sxs-lookup"><span data-stu-id="41162-138">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
