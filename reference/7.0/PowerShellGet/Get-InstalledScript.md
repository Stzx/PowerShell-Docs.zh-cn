---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: a90ece844d5a271402537f17c601bf2e36b5ed8c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196989"
---
# <span data-ttu-id="7c0aa-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="7c0aa-103">Get-InstalledScript</span></span>

## <span data-ttu-id="7c0aa-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7c0aa-104">SYNOPSIS</span></span>
<span data-ttu-id="7c0aa-105">获取已安装的脚本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-105">Gets an installed script.</span></span>

## <span data-ttu-id="7c0aa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7c0aa-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="7c0aa-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c0aa-107">DESCRIPTION</span></span>

<span data-ttu-id="7c0aa-108">**Get-installedscript** cmdlet 将获取 CurrentUser 和 AllUsers 作用域的安装脚本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="7c0aa-109">示例</span><span class="sxs-lookup"><span data-stu-id="7c0aa-109">EXAMPLES</span></span>

### <span data-ttu-id="7c0aa-110">示例1：获取所有已安装的脚本</span><span class="sxs-lookup"><span data-stu-id="7c0aa-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="7c0aa-111">此命令将获取所有已安装的脚本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="7c0aa-112">示例2：按名称获取安装的脚本</span><span class="sxs-lookup"><span data-stu-id="7c0aa-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="7c0aa-113">此命令将获取名称以编写开头的脚本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="7c0aa-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c0aa-114">PARAMETERS</span></span>

### <span data-ttu-id="7c0aa-115">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="7c0aa-115">-AllowPrerelease</span></span>

<span data-ttu-id="7c0aa-116">包括标记为预发行的结果脚本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-116">Includes in the results scripts marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c0aa-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="7c0aa-117">-MaximumVersion</span></span>

<span data-ttu-id="7c0aa-118">指定要获取的最大或最新版本的脚本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="7c0aa-119">MaximumVersion  和 RequiredVersion  参数互斥，不能在同一命令中使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c0aa-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="7c0aa-120">-MinimumVersion</span></span>

<span data-ttu-id="7c0aa-121">指定要获取的脚本的最低版本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="7c0aa-122">MinimumVersion  和 RequiredVersion  参数互斥，不能在同一命令中使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c0aa-123">-Name</span><span class="sxs-lookup"><span data-stu-id="7c0aa-123">-Name</span></span>

<span data-ttu-id="7c0aa-124">指定要获取的脚本的名称数组。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="7c0aa-125">可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-125">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7c0aa-126">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="7c0aa-126">-RequiredVersion</span></span>

<span data-ttu-id="7c0aa-127">指定要获取的脚本的确切版本。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-127">Specifies the exact version of a script to get.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c0aa-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7c0aa-128">CommonParameters</span></span>

<span data-ttu-id="7c0aa-129">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7c0aa-130">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7c0aa-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7c0aa-131">输入</span><span class="sxs-lookup"><span data-stu-id="7c0aa-131">INPUTS</span></span>

### <span data-ttu-id="7c0aa-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="7c0aa-132">System.String[]</span></span>

### <span data-ttu-id="7c0aa-133">System.String</span><span class="sxs-lookup"><span data-stu-id="7c0aa-133">System.String</span></span>

## <span data-ttu-id="7c0aa-134">输出</span><span class="sxs-lookup"><span data-stu-id="7c0aa-134">OUTPUTS</span></span>

### <span data-ttu-id="7c0aa-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="7c0aa-135">System.Object</span></span>

## <span data-ttu-id="7c0aa-136">注释</span><span class="sxs-lookup"><span data-stu-id="7c0aa-136">NOTES</span></span>

## <span data-ttu-id="7c0aa-137">相关链接</span><span class="sxs-lookup"><span data-stu-id="7c0aa-137">RELATED LINKS</span></span>

[<span data-ttu-id="7c0aa-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="7c0aa-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="7c0aa-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="7c0aa-139">Uninstall-Script</span></span>](Uninstall-Script.md)
