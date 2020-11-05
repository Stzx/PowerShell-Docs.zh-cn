---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: DSCAutomationHostEnabled 注册表项
description: 本文定义了可在 DSCAutomationHostEnabled 注册表项中设置的值
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656188"
---
# <a name="dscautomationhostenabled-registry-key"></a>DSCAutomationHostEnabled 注册表项

> 适用对象：Windows PowerShell 5.0

DSC 使用 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System 下的 DSCAutomationHostEnabled 注册表项，以便在初始启动时配置计算机。 DSCAutomationHostEnabled 支持三种模式：

| DSCAutomationHostEnabled 值 |                                              说明                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| 0                              | 禁用对启动状态计算机的配置。                                                           |
| 1                              | 启用对启动状态计算机的配置。                                                            |
| 2                              | 仅在 DSC 处于挂起或当前状态时，启用对计算机的配置。 这是默认值。 |

## <a name="see-also"></a>另请参阅

有关如何使用此功能在初始启动时运行配置的示例，请参阅[初始启动时使用 DSC 配置虚拟机](bootstrapDsc.md)。
