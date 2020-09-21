---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: ResourceTest 方法
ms.openlocfilehash: 7ef65227342091cb2a5063aaf95a2780d217f85a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463799"
---
# <a name="resourcetest-method"></a>ResourceTest 方法

直接调用 DSC 资源的 **Test** 方法。

## <a name="syntax"></a>语法

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a>参数

ResourceType  \[in\]：要调用的资源的名称。

ModuleName  \[in\]：包含要调用资源的模块名称。

***resourceProperty** \[in\] 在哈希表中分别将资源属性名及其值指定为键和值。 使用 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet 可以发现资源属性及其类型。

*InDesiredState** \[out\] 返回响应时，如果目标节点处于所需状态，便会将此属性设置为 true。

## <a name="return-value"></a>返回值

如果成功，则返回零；否则返回错误代码。

## <a name="remarks"></a>备注

这是一种静态方法。

## <a name="requirements"></a>要求

**MOF：** DscCore.mof

**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另请参阅

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
