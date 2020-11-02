---
ms.date: 07/17/2020
ms.topic: reference
title: RemoveConfiguration 方法
description: RemoveConfiguration 方法
ms.openlocfilehash: d5988ac014c457407c56a097c9a376427376eb3f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650730"
---
# <a name="removeconfiguration-method"></a>RemoveConfiguration 方法

删除配置文件。

## <a name="syntax"></a>语法

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a>参数

Stage  \[in\]：指定要删除的配置文档。 以下为有效值：

|值 |说明 |
|:--- |:---|
|**1** | **当前** 配置文档 (current.mof)。 |
|**2** | **挂起的** 配置文档 (pending.mof)。  |
|**4** | **以前的** 配置文档 (previous.mof)。 |

Force  \[in\]：若为 true  ，则强制删除配置。

## <a name="return-value"></a>返回值

如果成功，则返回零；否则返回错误代码。

## <a name="remarks"></a>备注

这是一种静态方法。

## <a name="requirements"></a>要求

**MOF：** DscCore.mof

**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另请参阅

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
