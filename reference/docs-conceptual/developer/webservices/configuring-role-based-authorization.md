---
title: 配置基于角色的授权 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2933a6ca-fe92-4ba2-97ee-ef0f0d5fdfcf
caps.latest.revision: 8
ms.openlocfilehash: 2c9d6040b7a9c17dc5204c8eb835fd69780f62c5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564251"
---
# <a name="configuring-role-based-authorization"></a>配置基于角色的授权

本主题演示如何为[实现管理 ODATA IIS 扩展的自定义授权](./implementing-custom-authorization-for-a-management-odata-web-service.md)中所述的[Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization)接口的示例实现配置基于角色的授权策略。

在此示例中，你将配置一个 XML 文件，该文件由示例管理 OData 应用程序用来定义授权策略。 你将创建两个角色，并将包含工作流的不同 Windows PowerShell 模块与这些角色关联。 用于定义 XML 文件的架构在[基于角色的授权配置架构](./role-based-authorization-configuration-schema.md)中列出。

## <a name="modifying-the-rbacconfigurationxml-file"></a>修改 RBacConfiguration 文件

此文件定义了应用程序的授权策略。 使用节点定义角色 `Group` 。 `Group`节点定义分配给该组的用户可以运行的 Windows PowerShell 命令。 使用节点将用户分配到组 `User` 。

在这些示例中，你将向管理员节点添加一个模块 `Group` ，并向每个组添加一个用户。

#### <a name="adding-a-module-to-a-group-node"></a>向组节点添加模块

1. 在文本编辑器中，创建一个名为**RBacConfiguration**的文件。 应将此文件保存到 web 服务的主应用程序目录中。 在文件中插入以下文本。

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <RbacConfiguration>
     <Groups>
       <!--Group consists of the following:
         Name:  Name of the group
         UserName (Optional): Windows Identity user name
         Password (Optional): Password of the Windows user name
         DomainName (Optional): Domain for the user. For local machine account either do not include them or give the machine name. Do not give empty string
         MapIncomingUser (Optional): Boolean value indicating whether to execute cmdlet in the context of network client.

         User credentials and MapIncomingUser=true are exclusive.
       -->
       <Group Name="NonAdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Set-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
       </Group>
       <Group Name="AdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
         <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
       </Group>
     </Groups>
     <Users>
       <!-- User consists of the following :
         Name: Name of the user. If a user is from a cer
         AuthenticationType: Authentication type used.
         DomainName (Optional): Domain for the user
       -->
       <User Name="localNonAdmin" AuthenticationType="Basic" GroupName="NonAdminGroup" />
       <User Name="localAdmin" AuthenticationType="Basic" GroupName="AdminGroup" />
     </Users>
   </RbacConfiguration>
   ```

2. 此文件包含两个 `Group` 节点。 这些表示在此示例中使用的两个角色： `NonAdminGroup` 和 `AdminGroup` 角色。

   `Cmdlets`在第一个节点中的结束标记后 `Group` ，添加以下 XML：

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a>将用户添加到组节点

1. 在文本编辑器中打开**RBacConfiguration**文件。 \\如果在安装之前未更改终结点名称，则此文件位于文件夹 C： \inetpub\wwwroot\Modata 中。

2. 在节点中的结束标记后 `Users` ，添加以下 XML：

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. 直接在上一步添加的 XML 后面添加以下 XML：

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```
