---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 2dbbbfeac3810f79b976b6a68ab3089e91707fb3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198284"
---
# <span data-ttu-id="b052a-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="b052a-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="b052a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b052a-104">SYNOPSIS</span></span>
<span data-ttu-id="b052a-105">获取指定项的一个或多个属性的值。</span><span class="sxs-lookup"><span data-stu-id="b052a-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="b052a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b052a-106">SYNTAX</span></span>

### <span data-ttu-id="b052a-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="b052a-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b052a-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b052a-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="b052a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b052a-109">DESCRIPTION</span></span>

<span data-ttu-id="b052a-110">`Get-ItemPropertyValue`当你使用 *Name* 参数时，获取指定的属性的当前值，该属性位于你使用 *path* 或 *LiteralPath* 参数指定的路径中。</span><span class="sxs-lookup"><span data-stu-id="b052a-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="b052a-111">示例</span><span class="sxs-lookup"><span data-stu-id="b052a-111">EXAMPLES</span></span>

### <span data-ttu-id="b052a-112">示例 1：获取 ProductID 属性的值</span><span class="sxs-lookup"><span data-stu-id="b052a-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="b052a-113">此命令获取 Windows 注册表提供程序中 "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" 对象的 **ProductID** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b052a-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="b052a-114">示例 2：获取文件或文件夹的上次写入时间</span><span class="sxs-lookup"><span data-stu-id="b052a-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="b052a-115">此命令将获取 **LastWriteTime** 属性的值，或上次更改文件或文件夹的时间，从 "C:\Users\Test\Documents\ModuleToAssembly" 文件夹，在 FileSystem 提供程序中工作。</span><span class="sxs-lookup"><span data-stu-id="b052a-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="b052a-116">示例 3：获取文件或文件夹的多个属性的值</span><span class="sxs-lookup"><span data-stu-id="b052a-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="b052a-117">此命令用于获取文件夹的 **LastWriteTime** 、 **CreationTime** 和 **Root** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b052a-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span>
<span data-ttu-id="b052a-118">这些属性值按照属性名称的指定顺序返回。</span><span class="sxs-lookup"><span data-stu-id="b052a-118">The property values are returned in the order in which you specified the property names.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## <span data-ttu-id="b052a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b052a-119">PARAMETERS</span></span>

### <span data-ttu-id="b052a-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="b052a-120">-Credential</span></span>

<span data-ttu-id="b052a-121">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b052a-121">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b052a-122">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="b052a-122">The default is the current user.</span></span>

<span data-ttu-id="b052a-123">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="b052a-123">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="b052a-124">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="b052a-124">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="b052a-125">随同 Windows PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="b052a-125">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b052a-126">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b052a-126">-Exclude</span></span>

<span data-ttu-id="b052a-127">指定此 cmdlet 将从操作中排除的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="b052a-127">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="b052a-128">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b052a-128">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="b052a-129">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="b052a-129">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="b052a-130">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b052a-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b052a-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="b052a-131">-Filter</span></span>

<span data-ttu-id="b052a-132">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="b052a-132">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="b052a-133">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b052a-133">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="b052a-134">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="b052a-134">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="b052a-135">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b052a-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b052a-136">-Include</span><span class="sxs-lookup"><span data-stu-id="b052a-136">-Include</span></span>

<span data-ttu-id="b052a-137">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="b052a-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="b052a-138">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b052a-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="b052a-139">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="b052a-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="b052a-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b052a-140">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b052a-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b052a-141">-LiteralPath</span></span>

<span data-ttu-id="b052a-142">指定此属性的当前位置的路径。</span><span class="sxs-lookup"><span data-stu-id="b052a-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="b052a-143">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="b052a-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="b052a-144">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="b052a-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="b052a-145">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="b052a-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b052a-146">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="b052a-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b052a-147">-Name</span><span class="sxs-lookup"><span data-stu-id="b052a-147">-Name</span></span>

<span data-ttu-id="b052a-148">指定要检索的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="b052a-148">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b052a-149">-Path</span><span class="sxs-lookup"><span data-stu-id="b052a-149">-Path</span></span>

<span data-ttu-id="b052a-150">指定一个或多个项的路径。</span><span class="sxs-lookup"><span data-stu-id="b052a-150">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b052a-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b052a-151">-UseTransaction</span></span>

<span data-ttu-id="b052a-152">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="b052a-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b052a-153">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="b052a-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b052a-154">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="b052a-154">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b052a-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b052a-155">CommonParameters</span></span>

<span data-ttu-id="b052a-156">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="b052a-156">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b052a-157">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b052a-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b052a-158">输入</span><span class="sxs-lookup"><span data-stu-id="b052a-158">INPUTS</span></span>

### <span data-ttu-id="b052a-159">System.String</span><span class="sxs-lookup"><span data-stu-id="b052a-159">System.String</span></span>

<span data-ttu-id="b052a-160">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b052a-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="b052a-161">输出</span><span class="sxs-lookup"><span data-stu-id="b052a-161">OUTPUTS</span></span>

### <span data-ttu-id="b052a-162">System.Boolean、System.String、System.DateTime</span><span class="sxs-lookup"><span data-stu-id="b052a-162">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="b052a-163">此 cmdlet 为其所获取的每个项属性返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="b052a-163">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="b052a-164">对象类型取决于检索的属性值。</span><span class="sxs-lookup"><span data-stu-id="b052a-164">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="b052a-165">例如，在文件系统驱动器中，该 cmdlet 可能会返回一个文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="b052a-165">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="b052a-166">注释</span><span class="sxs-lookup"><span data-stu-id="b052a-166">NOTES</span></span>

<span data-ttu-id="b052a-167">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="b052a-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b052a-168">若要列出会话中可用的提供程序，请运行 `Get-PSProvider` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b052a-168">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="b052a-169">有关详细信息，请参阅 about_Providers。</span><span class="sxs-lookup"><span data-stu-id="b052a-169">For more information, see about_Providers.</span></span>

## <span data-ttu-id="b052a-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="b052a-170">RELATED LINKS</span></span>

[<span data-ttu-id="b052a-171">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-171">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="b052a-172">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-172">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="b052a-173">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-173">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="b052a-174">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-174">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="b052a-175">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-175">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="b052a-176">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-176">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="b052a-177">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-177">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b052a-178">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b052a-178">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="b052a-179">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="b052a-179">Get-PSProvider</span></span>](Get-PSProvider.md)
