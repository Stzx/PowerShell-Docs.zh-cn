---
ms.date: 07/17/2020
ms.topic: reference
title: StopConfiguration 方法
description: StopConfiguration 方法
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644621"
---
# <a name="stopconfiguration-method"></a>StopConfiguration 方法

停止正在进行的配置更改。

## <a name="syntax"></a>语法

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>参数

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
