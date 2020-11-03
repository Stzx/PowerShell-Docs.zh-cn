---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198280"
---
# <span data-ttu-id="0f87f-103">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="0f87f-103">Get-PSProvider</span></span>

## <span data-ttu-id="0f87f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0f87f-104">SYNOPSIS</span></span>
<span data-ttu-id="0f87f-105">获取有关指定的 Windows PowerShell 提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="0f87f-105">Gets information about the specified Windows PowerShell provider.</span></span>

## <span data-ttu-id="0f87f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f87f-106">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0f87f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f87f-107">DESCRIPTION</span></span>
<span data-ttu-id="0f87f-108">**PSProvider** cmdlet 获取当前会话中的 Windows PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0f87f-108">The **Get-PSProvider** cmdlet gets the Windows PowerShell providers in the current session.</span></span>
<span data-ttu-id="0f87f-109">可以获取会话中的特定驱动器或所有驱动器。</span><span class="sxs-lookup"><span data-stu-id="0f87f-109">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="0f87f-110">通过 Windows PowerShell 提供程序，可以访问各种数据存储，就好像它们是文件系统驱动器一样。</span><span class="sxs-lookup"><span data-stu-id="0f87f-110">Windows PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="0f87f-111">有关 Windows PowerShell 提供程序的信息，请参阅 about_Providers。</span><span class="sxs-lookup"><span data-stu-id="0f87f-111">For information about Windows PowerShell providers, see about_Providers.</span></span>

## <span data-ttu-id="0f87f-112">示例</span><span class="sxs-lookup"><span data-stu-id="0f87f-112">EXAMPLES</span></span>

### <span data-ttu-id="0f87f-113">示例1：显示所有可用提供程序的列表</span><span class="sxs-lookup"><span data-stu-id="0f87f-113">Example 1: Display a list of all available providers</span></span>

```
PS C:\> Get-PSProvider
```

<span data-ttu-id="0f87f-114">此命令显示所有可用 Windows PowerShell 提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="0f87f-114">This command displays a list of all available Windows PowerShell providers.</span></span>

### <span data-ttu-id="0f87f-115">示例2：显示以指定字母开头的所有 Windows PowerShell 提供程序的列表</span><span class="sxs-lookup"><span data-stu-id="0f87f-115">Example 2: Display a list of all Windows PowerShell providers that begin with specified letters</span></span>

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="0f87f-116">此命令显示其名称以字母 "f" 或 "r" 开头的所有 Windows PowerShell 提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="0f87f-116">This command displays a list of all Windows PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="0f87f-117">示例3：查找将提供程序添加到会话的管理单元或模块</span><span class="sxs-lookup"><span data-stu-id="0f87f-117">Example 3: Find snap-ins or module that added providers to your session</span></span>

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="0f87f-118">这些命令查找将提供程序添加到会话中的 Windows PowerShell 管理单元或模块。</span><span class="sxs-lookup"><span data-stu-id="0f87f-118">These commands find the Windows PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="0f87f-119">所有 Windows PowerShell 元素（包括提供程序）均源自于管理单元或模块。</span><span class="sxs-lookup"><span data-stu-id="0f87f-119">All Windows PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="0f87f-120">这些命令使用 **PSProvider** 返回的 **ProviderInfo** 对象的 add-pssnapin 和 Module 属性。</span><span class="sxs-lookup"><span data-stu-id="0f87f-120">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that **Get-PSProvider** returns.</span></span>
<span data-ttu-id="0f87f-121">这些属性的值包含添加提供程序的管理单元或模块的名称。</span><span class="sxs-lookup"><span data-stu-id="0f87f-121">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="0f87f-122">第一个命令获取会话中的所有提供程序，并将它们的格式设置为表，其中显示其 Name、Module 和 PSSnapin 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0f87f-122">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="0f87f-123">第二个命令使用 Where-Object cmdlet 获取来自 **Microsoft. Security** 管理单元的提供程序。</span><span class="sxs-lookup"><span data-stu-id="0f87f-123">The second command uses the Where-Object cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="0f87f-124">示例4：解析文件系统提供程序的 Home 属性的路径</span><span class="sxs-lookup"><span data-stu-id="0f87f-124">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

<span data-ttu-id="0f87f-125">此示例展示波形符 (~) 表示 FileSystem 提供程序的 Home 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0f87f-125">This example shows that the tilde symbol (~) represents the value of the Home property of the FileSystem provider.</span></span>
<span data-ttu-id="0f87f-126">Home 属性值是可选的，但对于 FileSystem 提供程序，它定义为 $env： homedrive \$ env： homepath 或 $home。</span><span class="sxs-lookup"><span data-stu-id="0f87f-126">The Home property value is optional, but for the FileSystem provider, it is defined as $env:homedrive\$env:homepath or $home.</span></span>

## <span data-ttu-id="0f87f-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f87f-127">PARAMETERS</span></span>

### <span data-ttu-id="0f87f-128">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="0f87f-128">-PSProvider</span></span>
<span data-ttu-id="0f87f-129">指定此 cmdlet 为其获取信息的 Windows PowerShell 提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="0f87f-129">Specifies the name or names of the Windows PowerShell providers about which this cmdlet gets information.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0f87f-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f87f-130">CommonParameters</span></span>
<span data-ttu-id="0f87f-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0f87f-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f87f-132">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0f87f-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f87f-133">输入</span><span class="sxs-lookup"><span data-stu-id="0f87f-133">INPUTS</span></span>

### <span data-ttu-id="0f87f-134">string[]</span><span class="sxs-lookup"><span data-stu-id="0f87f-134">String[]</span></span>

<span data-ttu-id="0f87f-135">可以通过管道将一个或多个提供程序名称字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f87f-135">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="0f87f-136">输出</span><span class="sxs-lookup"><span data-stu-id="0f87f-136">OUTPUTS</span></span>

### <span data-ttu-id="0f87f-137">System.web. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="0f87f-137">System.Management.Automation.ProviderInfo</span></span>
<span data-ttu-id="0f87f-138">此 cmdlet 将返回表示会话中的 Windows PowerShell 提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="0f87f-138">This cmdlet returns objects that represent the Windows PowerShell providers in the session.</span></span>

## <span data-ttu-id="0f87f-139">注释</span><span class="sxs-lookup"><span data-stu-id="0f87f-139">NOTES</span></span>

## <span data-ttu-id="0f87f-140">相关链接</span><span class="sxs-lookup"><span data-stu-id="0f87f-140">RELATED LINKS</span></span>

## <span data-ttu-id="0f87f-141">相关链接</span><span class="sxs-lookup"><span data-stu-id="0f87f-141">RELATED LINKS</span></span>
