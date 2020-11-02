---
ms.date: 07/17/2020
ms.topic: reference
title: TestConfiguration 方法
description: TestConfiguration 方法
ms.openlocfilehash: ed26fcad2286ca753fb4b1845b8c6ad0741d491b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648931"
---
# <a name="testconfiguration-method"></a>TestConfiguration 方法

将配置文档发送到托管节点并针对该文档验证当前配置。

## <a name="syntax"></a>语法

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a>参数

**configurationData** \[in\] 配置的环境数据。

InDesiredState  \[out\]：返回响应时，指定托管节点是否处于配置文档指定的状态。

ResourcesInDesiredState  \[out\]：返回响应时，包含 MSFT_ResourceInDesiredState  类的嵌入实例，此类指定处于所需状态的资源。

ResourcesNotInDesiredState  \[out\]：返回响应时，包含 MSFT_ResourceNotInDesiredState  类的嵌入实例，此类指定不处于所需状态的资源。

## <a name="return-value"></a>返回值

如果成功，则返回零；否则返回错误代码。

## <a name="remarks"></a>备注

这是一种静态方法。

## <a name="requirements"></a>要求

**MOF：** DscCore.mof

**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另请参阅

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
