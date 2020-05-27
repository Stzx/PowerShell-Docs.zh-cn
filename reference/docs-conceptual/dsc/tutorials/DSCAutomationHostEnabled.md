---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: DSCAutomationHostEnabled 注册表项
ms.openlocfilehash: 0f35a798e5b7d51fdfb66e4e79ceab0e36ccea5b
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808327"
---
# <a name="dscautomationhostenabled-registry-key"></a>DSCAutomationHostEnabled 注册表项

> 适用对象：Windows PowerShell 5.0

DSC 使用 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System 下的 DSCAutomationHostEnabled 注册表项，以便在初始启动时配置计算机。
DSCAutomationHostEnabled 支持三种模式：

|  DSCAutomationHostEnabled 值  |  说明   |
|---|---|
0 | 禁用对启动状态计算机的配置。 |
1 | 启用对启动状态计算机的配置。 |
2 | 仅在 DSC 处于挂起或当前状态时，启用对计算机的配置。 这是默认值。 |

## <a name="see-also"></a>另请参阅

有关如何使用此功能在初始启动时运行配置的示例，请参阅[初始启动时使用 DSC 配置虚拟机](bootstrapDsc.md)。
