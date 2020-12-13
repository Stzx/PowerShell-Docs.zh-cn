---
ms.date: 09/13/2016
ms.topic: reference
title: 编写项提供程序
description: 编写项提供程序
ms.openlocfilehash: f70c6ee50277988c4e3b7c255dc4548bc30319dd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355198"
---
# <a name="writing-an-item-provider"></a><span data-ttu-id="e0c95-103">编写项提供程序</span><span class="sxs-lookup"><span data-stu-id="e0c95-103">Writing an item provider</span></span>

<span data-ttu-id="e0c95-104">本主题介绍如何实现访问和操作数据存储区中的项的 Windows PowerShell 提供程序的方法。</span><span class="sxs-lookup"><span data-stu-id="e0c95-104">This topic describes how to implement the methods of a Windows PowerShell provider that access and manipulate items in the data store.</span></span> <span data-ttu-id="e0c95-105">若要能够访问项，提供程序必须从 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 类派生而来。</span><span class="sxs-lookup"><span data-stu-id="e0c95-105">To be able to access items, a provider must derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

<span data-ttu-id="e0c95-106">本主题中的示例中的提供程序使用 Access 数据库作为其数据存储。</span><span class="sxs-lookup"><span data-stu-id="e0c95-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="e0c95-107">有几个帮助器方法和用于与数据库进行交互的类。</span><span class="sxs-lookup"><span data-stu-id="e0c95-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="e0c95-108">有关包含帮助程序方法的完整示例，请参阅 [AccessDBProviderSample03](./accessdbprovidersample03.md)</span><span class="sxs-lookup"><span data-stu-id="e0c95-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample03](./accessdbprovidersample03.md)</span></span>

<span data-ttu-id="e0c95-109">有关 Windows PowerShell 提供程序的详细信息，请参阅 [Windows Powershell 提供程序概述](./windows-powershell-provider-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c95-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-item-methods"></a><span data-ttu-id="e0c95-110">实现项方法</span><span class="sxs-lookup"><span data-stu-id="e0c95-110">Implementing item methods</span></span>

<span data-ttu-id="e0c95-111">[Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)类公开了若干可用于访问和操作数据存储区中的项的方法。</span><span class="sxs-lookup"><span data-stu-id="e0c95-111">The [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class exposes several methods that can be used to access and manipulate the items in a data store.</span></span>
<span data-ttu-id="e0c95-112">有关这些方法的完整列表，请参阅 [ItemCmdletProvider 方法](/dotnet/api/system.management.automation.provider.itemcmdletprovider#methods)。</span><span class="sxs-lookup"><span data-stu-id="e0c95-112">For a complete list of these methods, see [ItemCmdletProvider Methods](/dotnet/api/system.management.automation.provider.itemcmdletprovider#methods).</span></span>
<span data-ttu-id="e0c95-113">在此示例中，我们将实现这四种方法。</span><span class="sxs-lookup"><span data-stu-id="e0c95-113">In this example, we will implement four of these methods.</span></span>
<span data-ttu-id="e0c95-114">[Itemcmdletprovider. Getitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) 将获取指定路径处的项。</span><span class="sxs-lookup"><span data-stu-id="e0c95-114">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) gets an item at a specified path.</span></span>
<span data-ttu-id="e0c95-115">Setitem \* 设置指定项的值。 [Itemcmdletprovider. \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)设置指定项的值。</span><span class="sxs-lookup"><span data-stu-id="e0c95-115">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) sets the value of the specified item.</span></span>
<span data-ttu-id="e0c95-116">[Itemcmdletprovider. Itemexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) 检查项是否存在于指定的路径。</span><span class="sxs-lookup"><span data-stu-id="e0c95-116">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) checks whether an item exists at the specified path.</span></span>
<span data-ttu-id="e0c95-117">[Itemcmdletprovider. Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) 检查路径，查看其是否映射到数据存储中的某个位置。</span><span class="sxs-lookup"><span data-stu-id="e0c95-117">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) checks a path to see if it maps to a location in the data store.</span></span>

> [!NOTE]
> <span data-ttu-id="e0c95-118">本主题以 [Windows PowerShell 提供程序快速入门](./windows-powershell-provider-quickstart.md)中的信息为基础。</span><span class="sxs-lookup"><span data-stu-id="e0c95-118">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="e0c95-119">本主题不包含有关如何设置提供程序项目的基本知识，或者如何实现从 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 类继承的方法，这些方法可创建和删除驱动器。</span><span class="sxs-lookup"><span data-stu-id="e0c95-119">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="e0c95-120">声明提供程序类</span><span class="sxs-lookup"><span data-stu-id="e0c95-120">Declaring the provider class</span></span>

<span data-ttu-id="e0c95-121">将提供程序声明为派生自 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 类，并将其与 [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)的修饰进行对其修饰。</span><span class="sxs-lookup"><span data-stu-id="e0c95-121">Declare the provider to derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a><span data-ttu-id="e0c95-122">实现 GetItem</span><span class="sxs-lookup"><span data-stu-id="e0c95-122">Implementing GetItem</span></span>

<span data-ttu-id="e0c95-123">当用户在提供程序上调用[GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) cmdlet 时，PowerShell 引擎将调用[Itemcmdletprovider. Getitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) .. e x \* \*。</span><span class="sxs-lookup"><span data-stu-id="e0c95-123">The [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) cmdlet on your provider.</span></span> <span data-ttu-id="e0c95-124">方法返回指定路径处的项。</span><span class="sxs-lookup"><span data-stu-id="e0c95-124">The method returns the item at the specified path.</span></span> <span data-ttu-id="e0c95-125">在 Access 数据库示例中，方法检查项是否为驱动器本身、数据库中的表或数据库中的行。</span><span class="sxs-lookup"><span data-stu-id="e0c95-125">In the Access database example, the method checks whether the item is the drive itself, a table in the database, or a row in the database.</span></span> <span data-ttu-id="e0c95-126">此方法通过调用 [Cmdletprovider. Writeitemobject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) 方法将该项发送到 PowerShell 引擎中。</span><span class="sxs-lookup"><span data-stu-id="e0c95-126">The method sends the item to the PowerShell engine by calling the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

```csharp
protected override void GetItem(string path)
      {
          // check if the path represented is a drive
          if (PathIsDrive(path))
          {
              WriteItemObject(this.PSDriveInfo, path, true);
              return;
          }// if (PathIsDrive...

           // Get table name and row information from the path and do
           // necessary actions
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               DatabaseTableInfo table = GetTable(tableName);
               WriteItemObject(table, path, true);
           }
           else if (type == PathType.Row)
           {
               DatabaseRowInfo row = GetRow(tableName, rowNumber);
               WriteItemObject(row, path, false);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

### <a name="implementing-setitem"></a><span data-ttu-id="e0c95-127">实现 SetItem</span><span class="sxs-lookup"><span data-stu-id="e0c95-127">Implementing SetItem</span></span>

<span data-ttu-id="e0c95-128">当用户调用[SetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) cmdlet 时，PowerShell 引擎调用会调用[Itemcmdletprovider. Setitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)方法。 "\*" 方法。</span><span class="sxs-lookup"><span data-stu-id="e0c95-128">The [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method is called by the PowerShell engine calls when a user calls the [Microsoft.PowerShell.Commands.SetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) cmdlet.</span></span> <span data-ttu-id="e0c95-129">它设置指定路径处的项的值。</span><span class="sxs-lookup"><span data-stu-id="e0c95-129">It sets the value of the item at the specified path.</span></span>

<span data-ttu-id="e0c95-130">在 Access 数据库示例中，只有当项是行时才设置该项的值是有意义的，因此，当项不是行时，方法将引发 [NotSupportedException](/dotnet/api/system.notsupportedexception) 。</span><span class="sxs-lookup"><span data-stu-id="e0c95-130">In the Access database example, it makes sense to set the value of an item only if that item is a row, so the method throws [NotSupportedException](/dotnet/api/system.notsupportedexception) when the item is not a row.</span></span>

```csharp
protected override void SetItem(string path, object values)
       {
           // Get type, table name and row number from the path specified
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type != PathType.Row)
           {
               WriteError(new ErrorRecord(new NotSupportedException(
                     "SetNotSupported"), "",
                  ErrorCategory.InvalidOperation, path));

               return;
           }

           // Get in-memory representation of table
           OdbcDataAdapter da = GetAdapterForTable(tableName);

           if (da == null)
           {
               return;
           }
           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           if (rowNumber >= table.Rows.Count)
           {
               // The specified row number has to be available. If not
               // NewItem has to be used to add a new row
               throw new ArgumentException("Row specified is not available");
           } // if (rowNum...

           string[] colValues = (values as string).Split(',');

           // set the specified row
           DataRow row = table.Rows[rowNumber];

           for (int i = 0; i < colValues.Length; i++)
           {
               row[i] = colValues[i];
           }

           // Update the table
           if (ShouldProcess(path, "SetItem"))
           {
               da.Update(ds, tableName);
           }

       }
```

### <a name="implementing-itemexists"></a><span data-ttu-id="e0c95-131">实现 ItemExists</span><span class="sxs-lookup"><span data-stu-id="e0c95-131">Implementing ItemExists</span></span>

<span data-ttu-id="e0c95-132">当用户调用[TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) cmdlet 时，PowerShell 引擎将调用[Itemcmdletprovider. Itemexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)方法，这是由 PowerShell 引擎调用的。</span><span class="sxs-lookup"><span data-stu-id="e0c95-132">The [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) cmdlet.</span></span> <span data-ttu-id="e0c95-133">方法确定指定路径是否存在项。</span><span class="sxs-lookup"><span data-stu-id="e0c95-133">The method determines whether there is an item at the specified path.</span></span> <span data-ttu-id="e0c95-134">如果该项存在，则方法会通过调用 Cmdletprovider 将其传递回 PowerShell 引擎。 [Writeitemobject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)。</span><span class="sxs-lookup"><span data-stu-id="e0c95-134">If the item does exist, the method passes it back to the PowerShell engine by calling [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span></span>

```csharp
protected override bool ItemExists(string path)
       {
           // check if the path represented is a drive
           if (PathIsDrive(path))
           {
               return true;
           }

           // Obtain type, table name and row number from path
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           DatabaseTableInfo table = GetTable(tableName);

           if (type == PathType.Table)
           {
               // if specified path represents a table then DatabaseTableInfo
               // object for the same should exist
               if (table != null)
               {
                   return true;
               }
           }
           else if (type == PathType.Row)
           {
               // if specified path represents a row then DatabaseTableInfo should
               // exist for the table and then specified row number must be within
               // the maximum row count in the table
               if (table != null && rowNumber < table.RowCount)
               {
                   return true;
               }
           }

           return false;

       }
```

### <a name="implementing-isvalidpath"></a><span data-ttu-id="e0c95-135">实现 IsValidPath</span><span class="sxs-lookup"><span data-stu-id="e0c95-135">Implementing IsValidPath</span></span>

<span data-ttu-id="e0c95-136">[Itemcmdletprovider. Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)方法用于检查指定路径对于当前提供程序是否语法是否有效。</span><span class="sxs-lookup"><span data-stu-id="e0c95-136">The [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method checks whether the specified path is syntactically valid for the current provider.</span></span> <span data-ttu-id="e0c95-137">它不检查项是否存在于路径中。</span><span class="sxs-lookup"><span data-stu-id="e0c95-137">It does not check whether an item exists at the path.</span></span>

```csharp
protected override bool IsValidPath(string path)
       {
           bool result = true;

           // check if the path is null or empty
           if (String.IsNullOrEmpty(path))
           {
               result = false;
           }

           // convert all separators in the path to a uniform one
           path = NormalizePath(path);

           // split the path into individual chunks
           string[] pathChunks = path.Split(pathSeparator.ToCharArray());

           foreach (string pathChunk in pathChunks)
           {
               if (pathChunk.Length == 0)
               {
                   result = false;
               }
           }
           return result;
       }
```

## <a name="next-steps"></a><span data-ttu-id="e0c95-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e0c95-138">Next steps</span></span>

<span data-ttu-id="e0c95-139">典型的实际提供商可以支持包含其他项目的项目，还可以将项目从驱动器中的某个路径移动到另一个路径。</span><span class="sxs-lookup"><span data-stu-id="e0c95-139">A typical real-world provider is capable of supporting items that contain other items, and of moving items from one path to another within the drive.</span></span> <span data-ttu-id="e0c95-140">有关支持容器的提供程序的示例，请参阅 [编写容器提供程序](./writing-a-container-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c95-140">For an example of a provider that supports containers, see [Writing a container provider](./writing-a-container-provider.md).</span></span> <span data-ttu-id="e0c95-141">有关支持移动项的提供程序的示例，请参阅 [编写导航提供程序](./writing-a-navigation-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c95-141">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0c95-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0c95-142">See Also</span></span>

[<span data-ttu-id="e0c95-143">编写容器提供程序</span><span class="sxs-lookup"><span data-stu-id="e0c95-143">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="e0c95-144">编写导航提供程序</span><span class="sxs-lookup"><span data-stu-id="e0c95-144">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="e0c95-145">Windows PowerShell 提供程序概述</span><span class="sxs-lookup"><span data-stu-id="e0c95-145">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
