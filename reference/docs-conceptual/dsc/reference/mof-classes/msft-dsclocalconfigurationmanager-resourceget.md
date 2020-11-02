---
ms.date: 07/17/2020
ms.topic: reference
title: ResourceGet 方法
description: ResourceGet 方法
ms.openlocfilehash: bff737f04e02740fa09fd82d7b27c75b11303dad
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650767"
---
# <a name="resourceget-method"></a>ResourceGet 方法

直接调用 DSC 资源的 **Get** 方法。

## <a name="syntax"></a>语法

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a>参数

ResourceType  \[in\]：要调用的资源的名称。

ModuleName  \[in\]：包含要调用资源的模块名称。

resourceProperty  \[in\]：在哈希表中分别将资源属性名及其值指定为键和值。 使用 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet 可以发现资源属性及其类型。

configurations  \[out\]：返回响应时，包含配置的嵌入实例。

## <a name="return-value"></a>返回值

如果成功，则返回零；否则返回错误代码。

## <a name="remarks"></a>备注

这是一种静态方法。

## <a name="requirements"></a>要求

**MOF：** DscCore.mof

**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另请参阅

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
