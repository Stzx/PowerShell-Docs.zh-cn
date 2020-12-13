---
ms.date: 09/13/2016
ms.topic: reference
title: 定义对象的默认方法
description: 定义对象的默认方法
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355521"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="64802-103">定义对象的默认方法</span><span class="sxs-lookup"><span data-stu-id="64802-103">Defining Default Methods for Objects</span></span>

<span data-ttu-id="64802-104">扩展 .NET Framework 对象时，可以将代码方法和脚本方法添加到对象。</span><span class="sxs-lookup"><span data-stu-id="64802-104">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="64802-105">以下各节介绍了用于定义这些方法的 XML。</span><span class="sxs-lookup"><span data-stu-id="64802-105">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="64802-106">以下部分中的示例来自 `Types.ps1xml` Windows PowerShell 安装目录中的类型文件 (`$PSHOME`) 。</span><span class="sxs-lookup"><span data-stu-id="64802-106">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="64802-107">有关详细信息，请参阅 [关于 Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)。</span><span class="sxs-lookup"><span data-stu-id="64802-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="64802-108">代码方法</span><span class="sxs-lookup"><span data-stu-id="64802-108">Code methods</span></span>

<span data-ttu-id="64802-109">代码方法引用 .NET Framework 对象的静态方法。</span><span class="sxs-lookup"><span data-stu-id="64802-109">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="64802-110">在下面的示例中，将 **ToString** 方法添加到 [System.Xml.Xml节点](/dotnet/api/System.Xml.XmlNode) 类型。</span><span class="sxs-lookup"><span data-stu-id="64802-110">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="64802-111">[PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)元素将扩展方法定义为代码方法。</span><span class="sxs-lookup"><span data-stu-id="64802-111">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="64802-112">[Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name)元素指定扩展方法的名称。</span><span class="sxs-lookup"><span data-stu-id="64802-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="64802-113">[CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference)元素指定静态方法。</span><span class="sxs-lookup"><span data-stu-id="64802-113">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="64802-114">还可以将 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) 元素添加到 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) 元素的成员。</span><span class="sxs-lookup"><span data-stu-id="64802-114">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a><span data-ttu-id="64802-115">脚本方法</span><span class="sxs-lookup"><span data-stu-id="64802-115">Script methods</span></span>

<span data-ttu-id="64802-116">脚本方法定义一个方法，其值为脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="64802-116">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="64802-117">在下面的示例中，将 **ConvertToDateTime** 方法添加到 [system.management.managementobject](/dotnet/api/System.Management.ManagementObject) 类型。</span><span class="sxs-lookup"><span data-stu-id="64802-117">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="64802-118">[PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod)元素将扩展方法定义为脚本方法。</span><span class="sxs-lookup"><span data-stu-id="64802-118">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element defines the extended method as a script method.</span></span> <span data-ttu-id="64802-119">[Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name)元素指定扩展方法的名称。</span><span class="sxs-lookup"><span data-stu-id="64802-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="64802-120">[脚本](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script)元素指定生成方法值的脚本。</span><span class="sxs-lookup"><span data-stu-id="64802-120">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="64802-121">还可以将 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) 元素添加到 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) 元素的成员。</span><span class="sxs-lookup"><span data-stu-id="64802-121">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="64802-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="64802-122">See also</span></span>

[<span data-ttu-id="64802-123">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="64802-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
