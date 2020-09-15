---
ms.date: 07/14/2020
keywords: dsc,powershell,配置,安装程序
title: DisableDebugConfiguration 方法
ms.openlocfilehash: 52d55ff6b1fd126482bbaa9480efc131ab2f100c
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463748"
---
# <a name="disabledebugconfiguration-method"></a>DisableDebugConfiguration 方法

禁用 DSC 资源调试。

## <a name="syntax"></a>语法

```mof
uint32 DisableDebugConfiguration();
```

## <a name="parameters"></a>parameters

此方法没有任何参数。

## <a name="return-value"></a>返回值

如果成功，则返回零；否则返回错误代码。

## <a name="remarks"></a>备注

这是一种静态方法。

## <a name="requirements"></a>要求

**MOF：** DscCore.mof

**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另请参阅

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
