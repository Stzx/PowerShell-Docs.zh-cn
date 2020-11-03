---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: c5e3cb677a736595d1acd98c6f4be4d43b2151ba
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198547"
---
# <span data-ttu-id="95b4a-103">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="95b4a-103">Get-PSSessionCapability</span></span>

## <span data-ttu-id="95b4a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="95b4a-104">SYNOPSIS</span></span>
<span data-ttu-id="95b4a-105">获取受约束的会话配置上的特定用户的功能。</span><span class="sxs-lookup"><span data-stu-id="95b4a-105">Gets the capabilities of a specific user on a constrained session configuration.</span></span>

## <span data-ttu-id="95b4a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95b4a-106">SYNTAX</span></span>

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## <span data-ttu-id="95b4a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95b4a-107">DESCRIPTION</span></span>

<span data-ttu-id="95b4a-108">**PSSessionCapability** cmdlet 获取特定用户对受约束会话配置的功能。</span><span class="sxs-lookup"><span data-stu-id="95b4a-108">The **Get-PSSessionCapability** cmdlet gets the capabilities of a specific user on a constrained session configuration.</span></span>
<span data-ttu-id="95b4a-109">使用此 cmdlet 审核用户的自定义会话配置。</span><span class="sxs-lookup"><span data-stu-id="95b4a-109">Use this cmdlet to audit customized session configurations for users.</span></span>

<span data-ttu-id="95b4a-110">从 Windows PowerShell 5.0 开始，你可以使用会话配置中的 **RoleDefinitions** 属性) 文件 (。</span><span class="sxs-lookup"><span data-stu-id="95b4a-110">Starting in Windows PowerShell 5.0, you can use the **RoleDefinitions** property in a session configuration (.pssc) file.</span></span>
<span data-ttu-id="95b4a-111">使用此属性，你可以基于组成员身份向用户授予针对单个受约束的终结点的不同功能。</span><span class="sxs-lookup"><span data-stu-id="95b4a-111">Using this property lets you grant users different capabilities on a single constrained endpoint based on group membership.</span></span>
<span data-ttu-id="95b4a-112">通过让你确定授予用户的确切功能， **PSSessionCapability** cmdlet 可降低审核这些终结点时的复杂性。</span><span class="sxs-lookup"><span data-stu-id="95b4a-112">The **Get-PSSessionCapability** cmdlet reduces complexity when auditing these endpoints by letting you determine the exact capabilities granted to a user.</span></span>

<span data-ttu-id="95b4a-113">默认情况下， **PSSessionCapability** cmdlet 返回指定用户可在指定终结点中运行的命令的列表。</span><span class="sxs-lookup"><span data-stu-id="95b4a-113">By default, the **Get-PSSessionCapability** cmdlet returns a list of commands the specified user can run in the specified endpoint.</span></span>
<span data-ttu-id="95b4a-114">这等效于指定终结点中运行 **Get 命令** 的用户。</span><span class="sxs-lookup"><span data-stu-id="95b4a-114">This is equivalent to the user running **Get-Command** in the specified endpoint.</span></span>
<span data-ttu-id="95b4a-115">当使用 *Full* 参数运行时，此 cmdlet 将返回 **InitialSessionState** 对象。</span><span class="sxs-lookup"><span data-stu-id="95b4a-115">When run with the *Full* parameter, this cmdlet returns an **InitialSessionState** object.</span></span>
<span data-ttu-id="95b4a-116">此对象包含有关指定的用户将与指定的终结点交互的 PowerShell 运行空间的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95b4a-116">This object contains details about the PowerShell runspace the specified user would interact with for the specified endpoint.</span></span>
<span data-ttu-id="95b4a-117">它包括语言模式、执行策略和环境变量等信息。</span><span class="sxs-lookup"><span data-stu-id="95b4a-117">It includes information such as Language Mode, Execution Policy, and Environmental Variables.</span></span>

## <span data-ttu-id="95b4a-118">示例</span><span class="sxs-lookup"><span data-stu-id="95b4a-118">EXAMPLES</span></span>

### <span data-ttu-id="95b4a-119">示例1：获取可用于用户的命令</span><span class="sxs-lookup"><span data-stu-id="95b4a-119">Example 1: Get commands available for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

<span data-ttu-id="95b4a-120">当连接到本地计算机上的 Endpoint1 约束终结点时，此示例将返回可供用户 CONTOSO\User 使用的命令。</span><span class="sxs-lookup"><span data-stu-id="95b4a-120">This example returns the commands available to the user CONTOSO\User when connecting to the Endpoint1 constrained endpoint on the local computer.</span></span>

### <span data-ttu-id="95b4a-121">示例2：获取有关用户的运行空间的详细信息</span><span class="sxs-lookup"><span data-stu-id="95b4a-121">Example 2: Get details about a runspace for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

<span data-ttu-id="95b4a-122">此示例返回有关用户 CONTOSO\User 连接到 Endpoint1 约束终结点时将与之交互的运行空间的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95b4a-122">This example returns details about the runspace the user CONTOSO\User would interact with when connecting to the Endpoint1 constrained endpoint.</span></span>

## <span data-ttu-id="95b4a-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95b4a-123">PARAMETERS</span></span>

### <span data-ttu-id="95b4a-124">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="95b4a-124">-ConfigurationName</span></span>

<span data-ttu-id="95b4a-125">指定正在检查)  (终结点的受约束的会话配置。</span><span class="sxs-lookup"><span data-stu-id="95b4a-125">Specifies the constrained session configuration (endpoint) that you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95b4a-126">-Full</span><span class="sxs-lookup"><span data-stu-id="95b4a-126">-Full</span></span>

<span data-ttu-id="95b4a-127">指示此 cmdlet 返回指定的约束终结点上指定用户的整个初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="95b4a-127">Indicates that this cmdlet returns the entire initial session state for the specified user at the specified constrained endpoint.</span></span>

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

### <span data-ttu-id="95b4a-128">-Username</span><span class="sxs-lookup"><span data-stu-id="95b4a-128">-Username</span></span>

<span data-ttu-id="95b4a-129">指定正在检查其功能的用户。</span><span class="sxs-lookup"><span data-stu-id="95b4a-129">Specifies the user whose capabilities you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95b4a-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="95b4a-130">CommonParameters</span></span>

<span data-ttu-id="95b4a-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="95b4a-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95b4a-132">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="95b4a-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95b4a-133">输入</span><span class="sxs-lookup"><span data-stu-id="95b4a-133">INPUTS</span></span>

## <span data-ttu-id="95b4a-134">输出</span><span class="sxs-lookup"><span data-stu-id="95b4a-134">OUTPUTS</span></span>

### <span data-ttu-id="95b4a-135">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="95b4a-135">System.Management.Automation.AliasInfo</span></span>

### <span data-ttu-id="95b4a-136">System.web. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="95b4a-136">System.Management.Automation.FunctionInfo</span></span>

### <span data-ttu-id="95b4a-137">System.Management.Automation.Runspaces.InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="95b4a-137">System.Management.Automation.Runspaces.InitialSessionState</span></span>

## <span data-ttu-id="95b4a-138">注释</span><span class="sxs-lookup"><span data-stu-id="95b4a-138">NOTES</span></span>

## <span data-ttu-id="95b4a-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="95b4a-139">RELATED LINKS</span></span>

[<span data-ttu-id="95b4a-140">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="95b4a-140">New-PSRoleCapabilityFile</span></span>](New-PSRoleCapabilityFile.md)
