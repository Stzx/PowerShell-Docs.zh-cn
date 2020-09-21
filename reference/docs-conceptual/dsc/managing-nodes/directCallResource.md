---
ms.date: 08/11/2020
keywords: dsc,powershell,配置,安装程序
title: 直接调用 DSC 资源方法
ms.openlocfilehash: 029a278c938e414820e172b85fac3cb3ad4b4afa
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162488"
---
# <a name="calling-dsc-resource-methods-directly"></a>直接调用 DSC 资源方法

>适用于：Windows PowerShell 5.0

可以使用 [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet 直接调用 DSC 资源的函数或方法（基于 MOF 资源的 `Get-TargetResource`、`Set-TargetResource` 和 `Test-TargetResource` 函数，或基于类的资源的 Get、Set 和 Test 方法）  。 这可为想要使用 DSC 资源的第三方所用，也可以作为开发资源时非常有用的工具。

> [!NOTE]
> 在 PowerShell 7.0+ 中，`Invoke-DscResource` 不再支持调用 WMI DSC 资源。 这包括 PSDesiredStateConfiguration 中的文件和日志资源  。

此 cmdlet 通常与元配置属性 `refreshMode = 'Disabled'` 组合使用，但无论 **refreshMode** 设置为何值，都可以使用它。

在调用 `Invoke-DscResource` cmdlet 时，可以通过使用 Method 参数来指定要调用的方法和函数。 你可以将哈希表作为 **Property** 参数的值进行传递，从而指定资源的属性。

直接调用资源方法的示例如下：

## <a name="ensure-a-file-is-present"></a>确保文件存在

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a>测试文件存在

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a>获取文件内容

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

>[!NOTE]
> 不支持直接调用复合资源方法。 请改为调用构成复合资源的基础资源的方法。

## <a name="see-also"></a>另请参阅

- [使用 MOF 编写自定义 DSC 资源](../resources/authoringResourceMOF.md)
- [使用 PowerShell 类编写自定义 DSC 资源](../resources/authoringResourceClass.md)
- [调试 DSC 资源](../troubleshooting/debugResource.md)
