---
ms.date: 07/17/2020
ms.topic: reference
title: SendConfigurationApply 方法
description: SendConfigurationApply 方法
ms.openlocfilehash: 9bd63220644e096b348f71ee9d4ac216af6a7ccc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648969"
---
# <a name="sendconfigurationapply-method"></a>SendConfigurationApply 方法

将配置文档发送到托管节点，并使用配置代理应用配置。

## <a name="syntax"></a>语法

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a>参数

ConfigurationData  \[in\]：配置的环境数据。

force  \[in\]：若为 true  ，则强制停止配置。

## <a name="return-value"></a>返回值

如果成功，则返回零；否则返回错误代码。

## <a name="remarks"></a>备注

这是一种静态方法。

## <a name="requirements"></a>要求

**MOF：** DscCore.mof

**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另请参阅

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
