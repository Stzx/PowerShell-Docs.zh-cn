---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: e24bb117b4d4277adc359c130789cf7ee03b1fd6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198354"
---
# <span data-ttu-id="6821c-103">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="6821c-103">Get-PSRepository</span></span>

## <span data-ttu-id="6821c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6821c-104">SYNOPSIS</span></span>
<span data-ttu-id="6821c-105">获取 PowerShell 存储库。</span><span class="sxs-lookup"><span data-stu-id="6821c-105">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="6821c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6821c-106">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6821c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6821c-107">DESCRIPTION</span></span>

<span data-ttu-id="6821c-108">**Get-PSRepository** cmdlet 可获取为当前用户注册的 PowerShell 模块存储库。</span><span class="sxs-lookup"><span data-stu-id="6821c-108">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="6821c-109">示例</span><span class="sxs-lookup"><span data-stu-id="6821c-109">EXAMPLES</span></span>

### <span data-ttu-id="6821c-110">示例 1：获取所有模块存储库</span><span class="sxs-lookup"><span data-stu-id="6821c-110">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="6821c-111">此命令将获取为当前用户注册的所有模块存储库。</span><span class="sxs-lookup"><span data-stu-id="6821c-111">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="6821c-112">示例 2：按名称获取模块存储库</span><span class="sxs-lookup"><span data-stu-id="6821c-112">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="6821c-113">此命令将获取名称中含有 NuGet 的所有模块存储库。</span><span class="sxs-lookup"><span data-stu-id="6821c-113">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="6821c-114">示例 3：获取模块存储库并设置输出格式</span><span class="sxs-lookup"><span data-stu-id="6821c-114">Example 3: Get a module repository and format the output</span></span>

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

<span data-ttu-id="6821c-115">此命令将获取名为 Local01 的存储库，并使用管道运算符将该对象传递给 Format-List cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6821c-115">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="6821c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6821c-116">PARAMETERS</span></span>

### <span data-ttu-id="6821c-117">-Name</span><span class="sxs-lookup"><span data-stu-id="6821c-117">-Name</span></span>

<span data-ttu-id="6821c-118">指定要获取的存储库名称。</span><span class="sxs-lookup"><span data-stu-id="6821c-118">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="6821c-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6821c-119">CommonParameters</span></span>

<span data-ttu-id="6821c-120">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6821c-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6821c-121">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6821c-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6821c-122">输入</span><span class="sxs-lookup"><span data-stu-id="6821c-122">INPUTS</span></span>

### <span data-ttu-id="6821c-123">System.String[]</span><span class="sxs-lookup"><span data-stu-id="6821c-123">System.String[]</span></span>

## <span data-ttu-id="6821c-124">输出</span><span class="sxs-lookup"><span data-stu-id="6821c-124">OUTPUTS</span></span>

### <span data-ttu-id="6821c-125">System.Object</span><span class="sxs-lookup"><span data-stu-id="6821c-125">System.Object</span></span>

## <span data-ttu-id="6821c-126">注释</span><span class="sxs-lookup"><span data-stu-id="6821c-126">NOTES</span></span>

## <span data-ttu-id="6821c-127">相关链接</span><span class="sxs-lookup"><span data-stu-id="6821c-127">RELATED LINKS</span></span>

[<span data-ttu-id="6821c-128">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="6821c-128">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="6821c-129">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="6821c-129">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="6821c-130">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="6821c-130">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

