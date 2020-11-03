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
# Export-ODataEndpointProxy

## 摘要
生成一个模块，其中包含用于管理 OData 终结点的 cmdlet。

## SYNTAX

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Export-ODataEndpointProxy`Cmdlet 使用 OData 终结点的元数据生成一个模块，其中包含可用于管理该 OData 终结点的 cmdlet。 模块基于 CDXML。 此 cmdlet 生成模块后，它会将该模块保存到 **OutputModule** 参数指定的路径和文件名。

`Export-ODataEndpointProxy` 生成用于创建、读取、更新和删除 (CRUD) 操作、非 CRUD 操作和关联操作的 cmdlet。

`Export-ODataEndpointProxy` 为每个终结点资源生成一个 CDXML 文件。 生成模块后，可以编辑这些 CDXML 文件。 例如，如果想要更改 cmdlet 的名词或 verb 名称，使其符合 Windows PowerShell cmdlet 命名准则，可以修改该文件。

生成的模块中的每个 cmdlet 都必须包含 **ConnectionURI** 参数，才能连接到模块管理的终结点。

## 示例

### 示例1：生成模块以管理零售 web 服务终结点

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

此命令生成一个模块来管理零售服务终结点。 命令指定终结点的 URI 和终结点元数据的 URI。 该命令还提供输出路径和脚本模块名称作为 **OutputModule** 参数的值。 对于 **ResourceNameMapping** 参数的值，该命令提供一个哈希表，该哈希表将资源集合名称映射到该 cmdlet 集的所需名词。 在此示例中，"产品" 为资源集合名称， **商品** 为名词。 若要允许连接到非 SSL 站点（与 HTTPS 相对），请添加 **AllowUnsecureConnection** 参数。

## PARAMETERS

### -AllowClobber

指示此 cmdlet 替换现有模块。

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

### -AllowUnsecureConnection

指示此模块可以连接到不受 SSL 保护的 Uri。 该模块还可以管理 HTTP 站点以及 HTTPS 站点。

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

### -CmdletAdapter

指定 cmdlet 适配器。 此参数可接受的值包括： ODataAdapter 和 NetworkControllerAdapter。

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

### -CreateRequestMethod

指定请求方法。 此参数可接受的值包括： PUT、POST 和 PATCH。

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

### -Credential

指定有权访问 OData 终结点的用户帐户。 默认值为当前用户。 如果远程计算机运行 Windows Vista 或更高版本的 Windows 操作系统，则该 cmdlet 会提示你输入凭据。

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

### -CustomData

指定自定义数据的哈希表。

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

### -Force

指示此 cmdlet 覆盖现有文件夹中现有的同名生成模块 `Modules` 。

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

### -标头

指定 Web 请求的标头。 输入哈希表或字典。

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

### -MetadataUri

指定终结点的元数据的 URI。

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

### -OutputModule

指定此 cmdlet 将生成的代理命令的模块保存到的路径和模块名称。

此 cmdlet 将二进制模块、模块清单和格式化文件（如果适用）复制到指定的文件夹。 如果只指定模块的名称，则会将 `Export-ODataEndpointProxy` 模块保存在文件夹中 `$home\Documents\WindowsPowerShell\Modules` 。 如果指定路径，则该 cmdlet 将在该路径中创建模块文件夹。

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

### -ResourceNameMapping

指定一个哈希表，其中包含允许自定义生成的 cmdlet 的映射。 在此哈希表中，资源集合名称是密钥。 所需的 cmdlet 为值。

例如，在哈希表中 `@{Products = 'Merchandise'}` ， **Products** 是用作键的资源集合名称。 **货品** 是产生的 cmdlet 名词。 生成的 cmdlet 名称可能与 Windows PowerShell cmdlet 命名准则不符。 可以修改资源 CDXML 文件，以便在此 cmdlet 创建模块后更改 cmdlet 名称。 有关详细信息，请参阅 [强烈建议开发指南](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines)。

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

### -UpdateRequestMethod

指定更新请求方法。 此参数可接受的值包括： PUT、POST 和 PATCH。

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

### -Uri

指定终结点的 URI。

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

### -Confirm

提示你在运行 cmdlet 之前进行确认。

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

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。
此 cmdlet 未运行。

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

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

## 输出

## 注释

## 相关链接

[OData 库](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)

[OData 协议是什么？](https://www.odata.org/)

[Invoke-RestMethod](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
