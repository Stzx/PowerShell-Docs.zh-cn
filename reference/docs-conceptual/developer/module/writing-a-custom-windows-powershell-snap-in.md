---
title: 编写自定义 Windows PowerShell 管理单元 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], custom PSSnapin example
- cmdlets [PowerShell SDK], specified in snap-ins
ms.assetid: 55c8b5cb-8ee2-4080-afc4-3f09c9f20128
caps.latest.revision: 6
ms.openlocfilehash: 9cf4499ec2992c6cfea83fc5d0bf51d0bbfaa96a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811626"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="af61a-102">编写自定义 Windows PowerShell 管理单元</span><span class="sxs-lookup"><span data-stu-id="af61a-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="af61a-103">此示例演示如何编写用于注册特定 cmdlet 的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="af61a-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="af61a-104">利用这种类型的管理单元，你可以指定要注册的 cmdlet、提供程序、类型或格式。</span><span class="sxs-lookup"><span data-stu-id="af61a-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="af61a-105">有关如何编写用于在程序集中注册所有 cmdlet 和提供程序的管理单元的详细信息，请参阅[编写 Windows PowerShell 管理单元](./writing-a-windows-powershell-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="af61a-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="af61a-106">编写用于注册特定 cmdlet 的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="af61a-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="af61a-107">添加 RunInstallerAttribute 特性。</span><span class="sxs-lookup"><span data-stu-id="af61a-107">Add the RunInstallerAttribute attribute.</span></span>
2. <span data-ttu-id="af61a-108">创建一个派生自[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)类的公共类。</span><span class="sxs-lookup"><span data-stu-id="af61a-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="af61a-109">在此示例中，类名为 "CustomPSSnapinTest"。</span><span class="sxs-lookup"><span data-stu-id="af61a-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="af61a-110">为管理单元的名称添加一个公共属性（必需）。</span><span class="sxs-lookup"><span data-stu-id="af61a-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="af61a-111">命名管理单元时，请不要使用以下任何字符： `#` 、 `.` 、 `,` 、 `(` 、 `)` `{` `}` `[` `]` `&` `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` `` ` `` 、、、、、、、、、、、、、、、、、、、、、、、、、、、、`*`</span><span class="sxs-lookup"><span data-stu-id="af61a-111">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

   <span data-ttu-id="af61a-112">在此示例中，管理单元的名称为 "CustomPSSnapInTest"。</span><span class="sxs-lookup"><span data-stu-id="af61a-112">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="af61a-113">添加管理单元供应商的公共属性（必需）。</span><span class="sxs-lookup"><span data-stu-id="af61a-113">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="af61a-114">在此示例中，供应商为 "Microsoft"。</span><span class="sxs-lookup"><span data-stu-id="af61a-114">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="af61a-115">添加管理单元的供应商资源的公共属性（可选）。</span><span class="sxs-lookup"><span data-stu-id="af61a-115">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="af61a-116">在此示例中，供应商资源为 "CustomPSSnapInTest，Microsoft"。</span><span class="sxs-lookup"><span data-stu-id="af61a-116">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="af61a-117">添加管理单元说明的公共属性（必需）。</span><span class="sxs-lookup"><span data-stu-id="af61a-117">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="af61a-118">在此示例中，说明为： "这是一个包含和 cmdlet 的自定义 Windows PowerShell 管理 `Test-HelloWorld` 单元 `Test-CustomSnapinTest` 。</span><span class="sxs-lookup"><span data-stu-id="af61a-118">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets".</span></span>

7. <span data-ttu-id="af61a-119">为管理单元的 "说明" 资源添加公共属性（可选）。</span><span class="sxs-lookup"><span data-stu-id="af61a-119">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="af61a-120">在此示例中，供应商资源为：</span><span class="sxs-lookup"><span data-stu-id="af61a-120">In this example, the vendor resource is:</span></span>

   > <span data-ttu-id="af61a-121">CustomPSSnapInTest，这是一个自定义的 Windows PowerShell 管理单元，其中包括 HelloWorld 和 CustomSnapinTest cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af61a-121">CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="af61a-122">使用[Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry)类指定属于 "自定义管理单元" （可选）的 cmdlet （可选）。</span><span class="sxs-lookup"><span data-stu-id="af61a-122">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="af61a-123">此处添加的信息包括 cmdlet 的名称、其 .NET 类型和 cmdlet 帮助文件名（cmdlet 帮助文件名的格式应该为 `name.dll-help.xml` ）。</span><span class="sxs-lookup"><span data-stu-id="af61a-123">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be `name.dll-help.xml`).</span></span>

   <span data-ttu-id="af61a-124">此示例将添加 HelloWorld 和 TestCustomSnapinTest cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af61a-124">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="af61a-125">指定属于自定义管理单元的提供程序（可选）。</span><span class="sxs-lookup"><span data-stu-id="af61a-125">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="af61a-126">此示例未指定任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="af61a-126">This example does not specify any providers.</span></span>

10. <span data-ttu-id="af61a-127">指定属于自定义管理单元的类型（可选）。</span><span class="sxs-lookup"><span data-stu-id="af61a-127">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="af61a-128">此示例未指定任何类型。</span><span class="sxs-lookup"><span data-stu-id="af61a-128">This example does not specify any types.</span></span>

11. <span data-ttu-id="af61a-129">指定属于自定义管理单元的格式（可选）。</span><span class="sxs-lookup"><span data-stu-id="af61a-129">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="af61a-130">此示例未指定任何格式。</span><span class="sxs-lookup"><span data-stu-id="af61a-130">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="af61a-131">示例</span><span class="sxs-lookup"><span data-stu-id="af61a-131">Example</span></span>

<span data-ttu-id="af61a-132">此示例演示如何编写可用于注册和 cmdlet 的自定义 Windows PowerShell 管理单元 `Test-HelloWorld` `Test-CustomSnapinTest` 。</span><span class="sxs-lookup"><span data-stu-id="af61a-132">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets.</span></span> <span data-ttu-id="af61a-133">请注意，在此示例中，完整的程序集可能包含不会由此管理单元注册的其他 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="af61a-133">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="af61a-134">有关注册管理单元的详细信息，请参阅[Windows PowerShell 程序员指南](../prog-guide/windows-powershell-programmer-s-guide.md)中的[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="af61a-134">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="af61a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af61a-135">See Also</span></span>

<span data-ttu-id="af61a-136">[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="af61a-136">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="af61a-137">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="af61a-137">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
