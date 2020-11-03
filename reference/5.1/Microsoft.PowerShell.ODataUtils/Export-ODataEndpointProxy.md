---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 7550e2df319e5f195e65609ae29ebb00830ec8d2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198003"
---
# <span data-ttu-id="da24d-103">Export-ODataEndpointProxy</span><span class="sxs-lookup"><span data-stu-id="da24d-103">Export-ODataEndpointProxy</span></span>

## <span data-ttu-id="da24d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="da24d-104">SYNOPSIS</span></span>
<span data-ttu-id="da24d-105">生成一个模块，其中包含用于管理 OData 终结点的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da24d-105">Generates a module that contains cmdlets to manage an OData endpoint.</span></span>

## <span data-ttu-id="da24d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da24d-106">SYNTAX</span></span>

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="da24d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="da24d-107">DESCRIPTION</span></span>

<span data-ttu-id="da24d-108">`Export-ODataEndpointProxy`Cmdlet 使用 OData 终结点的元数据生成一个模块，其中包含可用于管理该 OData 终结点的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da24d-108">The `Export-ODataEndpointProxy` cmdlet uses the metadata of an OData endpoint to generate a module that contains cmdlets you can use to manage that OData endpoint.</span></span> <span data-ttu-id="da24d-109">模块基于 CDXML。</span><span class="sxs-lookup"><span data-stu-id="da24d-109">The module is based on CDXML.</span></span> <span data-ttu-id="da24d-110">此 cmdlet 生成模块后，它会将该模块保存到 **OutputModule** 参数指定的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="da24d-110">After this cmdlet generates the module, it saves that module to the path and file name specified by the **OutputModule** parameter.</span></span>

<span data-ttu-id="da24d-111">`Export-ODataEndpointProxy` 生成用于创建、读取、更新和删除 (CRUD) 操作、非 CRUD 操作和关联操作的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da24d-111">`Export-ODataEndpointProxy` generates cmdlets for create, read, update, and delete (CRUD) operations, non-CRUD actions, and association manipulation.</span></span>

<span data-ttu-id="da24d-112">`Export-ODataEndpointProxy` 为每个终结点资源生成一个 CDXML 文件。</span><span class="sxs-lookup"><span data-stu-id="da24d-112">`Export-ODataEndpointProxy` generates one CDXML file per endpoint resource.</span></span> <span data-ttu-id="da24d-113">生成模块后，可以编辑这些 CDXML 文件。</span><span class="sxs-lookup"><span data-stu-id="da24d-113">You can edit these CDXML files after the module is generated.</span></span> <span data-ttu-id="da24d-114">例如，如果想要更改 cmdlet 的名词或 verb 名称，使其符合 Windows PowerShell cmdlet 命名准则，可以修改该文件。</span><span class="sxs-lookup"><span data-stu-id="da24d-114">For example, if you want to change the noun or verb names of the cmdlets to align with Windows PowerShell cmdlet naming guidelines, you can modify the file.</span></span>

<span data-ttu-id="da24d-115">生成的模块中的每个 cmdlet 都必须包含 **ConnectionURI** 参数，才能连接到模块管理的终结点。</span><span class="sxs-lookup"><span data-stu-id="da24d-115">Every cmdlet in a generated module must include a **ConnectionURI** parameter in order to connect to the endpoint that the module manages.</span></span>

## <span data-ttu-id="da24d-116">示例</span><span class="sxs-lookup"><span data-stu-id="da24d-116">EXAMPLES</span></span>

### <span data-ttu-id="da24d-117">示例1：生成模块以管理零售 web 服务终结点</span><span class="sxs-lookup"><span data-stu-id="da24d-117">Example 1: Generate a module to manage a retail web service endpoint</span></span>

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

<span data-ttu-id="da24d-118">此命令生成一个模块来管理零售服务终结点。</span><span class="sxs-lookup"><span data-stu-id="da24d-118">This command generates a module to manage a retail service endpoint.</span></span> <span data-ttu-id="da24d-119">命令指定终结点的 URI 和终结点元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="da24d-119">The command specifies the URI of the endpoint and the URI of the endpoint metadata.</span></span> <span data-ttu-id="da24d-120">该命令还提供输出路径和脚本模块名称作为 **OutputModule** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="da24d-120">The command also provides an output path and script module name as the value of the **OutputModule** parameter.</span></span> <span data-ttu-id="da24d-121">对于 **ResourceNameMapping** 参数的值，该命令提供一个哈希表，该哈希表将资源集合名称映射到该 cmdlet 集的所需名词。</span><span class="sxs-lookup"><span data-stu-id="da24d-121">For the value of the **ResourceNameMapping** parameter, the command provides a hashtable that maps the resource collection name to the desired noun for the cmdlet set.</span></span> <span data-ttu-id="da24d-122">在此示例中，"产品" 为资源集合名称， **商品** 为名词。</span><span class="sxs-lookup"><span data-stu-id="da24d-122">In this example, Products is the resource collection name and **Merchandise** is the noun.</span></span> <span data-ttu-id="da24d-123">若要允许连接到非 SSL 站点（与 HTTPS 相对），请添加 **AllowUnsecureConnection** 参数。</span><span class="sxs-lookup"><span data-stu-id="da24d-123">To allow connections to non-SSL sites, HTTP, as opposed to HTTPS, add the **AllowUnsecureConnection** parameter.</span></span>

## <span data-ttu-id="da24d-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da24d-124">PARAMETERS</span></span>

### <span data-ttu-id="da24d-125">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="da24d-125">-AllowClobber</span></span>

<span data-ttu-id="da24d-126">指示此 cmdlet 替换现有模块。</span><span class="sxs-lookup"><span data-stu-id="da24d-126">Indicates that this cmdlet replaces an existing module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-127">-AllowUnsecureConnection</span><span class="sxs-lookup"><span data-stu-id="da24d-127">-AllowUnsecureConnection</span></span>

<span data-ttu-id="da24d-128">指示此模块可以连接到不受 SSL 保护的 Uri。</span><span class="sxs-lookup"><span data-stu-id="da24d-128">Indicates that this module can connect to URIs that are not SSL-secured.</span></span> <span data-ttu-id="da24d-129">该模块还可以管理 HTTP 站点以及 HTTPS 站点。</span><span class="sxs-lookup"><span data-stu-id="da24d-129">The module can manage HTTP sites in addition to HTTPS sites.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-130">-CmdletAdapter</span><span class="sxs-lookup"><span data-stu-id="da24d-130">-CmdletAdapter</span></span>

<span data-ttu-id="da24d-131">指定 cmdlet 适配器。</span><span class="sxs-lookup"><span data-stu-id="da24d-131">Specifies the cmdlet adapter.</span></span> <span data-ttu-id="da24d-132">此参数可接受的值包括： ODataAdapter 和 NetworkControllerAdapter。</span><span class="sxs-lookup"><span data-stu-id="da24d-132">The acceptable values for this parameter are: ODataAdapter and NetworkControllerAdapter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ODataAdapter, NetworkControllerAdapter, ODataV4Adapter

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-133">-CreateRequestMethod</span><span class="sxs-lookup"><span data-stu-id="da24d-133">-CreateRequestMethod</span></span>

<span data-ttu-id="da24d-134">指定请求方法。</span><span class="sxs-lookup"><span data-stu-id="da24d-134">Specifies the request method.</span></span> <span data-ttu-id="da24d-135">此参数可接受的值包括： PUT、POST 和 PATCH。</span><span class="sxs-lookup"><span data-stu-id="da24d-135">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="da24d-136">-Credential</span></span>

<span data-ttu-id="da24d-137">指定有权访问 OData 终结点的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="da24d-137">Specifies a user account that has access to the OData endpoint.</span></span> <span data-ttu-id="da24d-138">默认值为当前用户。</span><span class="sxs-lookup"><span data-stu-id="da24d-138">The default value is the current user.</span></span> <span data-ttu-id="da24d-139">如果远程计算机运行 Windows Vista 或更高版本的 Windows 操作系统，则该 cmdlet 会提示你输入凭据。</span><span class="sxs-lookup"><span data-stu-id="da24d-139">If a remote computer runs Windows Vista or a later release of the Windows operating system, the cmdlet prompts you for credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-140">-CustomData</span><span class="sxs-lookup"><span data-stu-id="da24d-140">-CustomData</span></span>

<span data-ttu-id="da24d-141">指定自定义数据的哈希表。</span><span class="sxs-lookup"><span data-stu-id="da24d-141">Specifies a hash table of custom data.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-142">-Force</span><span class="sxs-lookup"><span data-stu-id="da24d-142">-Force</span></span>

<span data-ttu-id="da24d-143">指示此 cmdlet 覆盖现有文件夹中现有的同名生成模块 `Modules` 。</span><span class="sxs-lookup"><span data-stu-id="da24d-143">Indicates that this cmdlet overwrites an existing generated module of the same name in an existing `Modules` folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-144">-标头</span><span class="sxs-lookup"><span data-stu-id="da24d-144">-Headers</span></span>

<span data-ttu-id="da24d-145">指定 Web 请求的标头。</span><span class="sxs-lookup"><span data-stu-id="da24d-145">Specifies the headers of the web request.</span></span> <span data-ttu-id="da24d-146">输入哈希表或字典。</span><span class="sxs-lookup"><span data-stu-id="da24d-146">Enter a hash table or dictionary.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-147">-MetadataUri</span><span class="sxs-lookup"><span data-stu-id="da24d-147">-MetadataUri</span></span>

<span data-ttu-id="da24d-148">指定终结点的元数据的 URI。</span><span class="sxs-lookup"><span data-stu-id="da24d-148">Specifies the URI of the metadata of the endpoint.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-149">-OutputModule</span><span class="sxs-lookup"><span data-stu-id="da24d-149">-OutputModule</span></span>

<span data-ttu-id="da24d-150">指定此 cmdlet 将生成的代理命令的模块保存到的路径和模块名称。</span><span class="sxs-lookup"><span data-stu-id="da24d-150">Specifies the path and module name to which this cmdlet saves the generated module of proxy commands.</span></span>

<span data-ttu-id="da24d-151">此 cmdlet 将二进制模块、模块清单和格式化文件（如果适用）复制到指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="da24d-151">This cmdlet copies a binary module, module manifest, and formatting file, if applicable, to the specified folder.</span></span> <span data-ttu-id="da24d-152">如果只指定模块的名称，则会将 `Export-ODataEndpointProxy` 模块保存在文件夹中 `$home\Documents\WindowsPowerShell\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="da24d-152">If you specify only the name of the module, `Export-ODataEndpointProxy` saves the module in the `$home\Documents\WindowsPowerShell\Modules` folder.</span></span> <span data-ttu-id="da24d-153">如果指定路径，则该 cmdlet 将在该路径中创建模块文件夹。</span><span class="sxs-lookup"><span data-stu-id="da24d-153">If you specify a path, the cmdlet creates the module folder in that path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-154">-ResourceNameMapping</span><span class="sxs-lookup"><span data-stu-id="da24d-154">-ResourceNameMapping</span></span>

<span data-ttu-id="da24d-155">指定一个哈希表，其中包含允许自定义生成的 cmdlet 的映射。</span><span class="sxs-lookup"><span data-stu-id="da24d-155">Specifies a hashtable that contains mappings that let you customize the generated cmdlets.</span></span> <span data-ttu-id="da24d-156">在此哈希表中，资源集合名称是密钥。</span><span class="sxs-lookup"><span data-stu-id="da24d-156">In this hashtable, the resource collection name is the key.</span></span> <span data-ttu-id="da24d-157">所需的 cmdlet 为值。</span><span class="sxs-lookup"><span data-stu-id="da24d-157">The desired cmdlet noun is the value.</span></span>

<span data-ttu-id="da24d-158">例如，在哈希表中 `@{Products = 'Merchandise'}` ， **Products** 是用作键的资源集合名称。</span><span class="sxs-lookup"><span data-stu-id="da24d-158">For example, in the hash table `@{Products = 'Merchandise'}`, **Products** is the resource collection name that serves as the key.</span></span> <span data-ttu-id="da24d-159">**货品** 是产生的 cmdlet 名词。</span><span class="sxs-lookup"><span data-stu-id="da24d-159">**Merchandise** is the resulting cmdlet noun.</span></span> <span data-ttu-id="da24d-160">生成的 cmdlet 名称可能与 Windows PowerShell cmdlet 命名准则不符。</span><span class="sxs-lookup"><span data-stu-id="da24d-160">The generated cmdlet names might not align to Windows PowerShell cmdlet naming guidelines.</span></span> <span data-ttu-id="da24d-161">可以修改资源 CDXML 文件，以便在此 cmdlet 创建模块后更改 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="da24d-161">You can modify the resource CDXML file to change the cmdlet names after this cmdlet creates the module.</span></span> <span data-ttu-id="da24d-162">有关详细信息，请参阅 [强烈建议开发指南](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines)。</span><span class="sxs-lookup"><span data-stu-id="da24d-162">For more information, see [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-163">-UpdateRequestMethod</span><span class="sxs-lookup"><span data-stu-id="da24d-163">-UpdateRequestMethod</span></span>

<span data-ttu-id="da24d-164">指定更新请求方法。</span><span class="sxs-lookup"><span data-stu-id="da24d-164">Specifies the update request method.</span></span> <span data-ttu-id="da24d-165">此参数可接受的值包括： PUT、POST 和 PATCH。</span><span class="sxs-lookup"><span data-stu-id="da24d-165">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-166">-Uri</span><span class="sxs-lookup"><span data-stu-id="da24d-166">-Uri</span></span>

<span data-ttu-id="da24d-167">指定终结点的 URI。</span><span class="sxs-lookup"><span data-stu-id="da24d-167">Specifies the URI of the endpoint.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="da24d-168">-Confirm</span></span>

<span data-ttu-id="da24d-169">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="da24d-169">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="da24d-170">-WhatIf</span></span>

<span data-ttu-id="da24d-171">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="da24d-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="da24d-172">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="da24d-172">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da24d-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="da24d-173">CommonParameters</span></span>

<span data-ttu-id="da24d-174">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="da24d-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da24d-175">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="da24d-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da24d-176">输入</span><span class="sxs-lookup"><span data-stu-id="da24d-176">INPUTS</span></span>

## <span data-ttu-id="da24d-177">输出</span><span class="sxs-lookup"><span data-stu-id="da24d-177">OUTPUTS</span></span>

## <span data-ttu-id="da24d-178">注释</span><span class="sxs-lookup"><span data-stu-id="da24d-178">NOTES</span></span>

## <span data-ttu-id="da24d-179">相关链接</span><span class="sxs-lookup"><span data-stu-id="da24d-179">RELATED LINKS</span></span>

<span data-ttu-id="da24d-180">[OData 库](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span><span class="sxs-lookup"><span data-stu-id="da24d-180">[OData Library](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span></span>

[<span data-ttu-id="da24d-181">OData 协议是什么？</span><span class="sxs-lookup"><span data-stu-id="da24d-181">What is the OData Protocol?</span></span>](https://www.odata.org/)

[<span data-ttu-id="da24d-182">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="da24d-182">Invoke-RestMethod</span></span>](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
