---
ms.date: 06/12/2017
title: 需要接受许可证
description: 如何在“项目详细信息”页上查看包许可证
ms.openlocfilehash: 0d8a9ed671f7993726bc3fa41d11159b366e5a28
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662295"
---
# <a name="require-license-acceptance"></a>需要接受许可证

对于需要接受许可证的模块，会在项目详细信息页上显示“需要接受许可证”文本。 可以通过单击“View License.txt”链接查看模块的许可证。

![需要接受许可证](media/packages-that-require-license-acceptance/RequireLicenseAcceptance.png)

通过 PowerShellGet 安装、保存或更新模块或部署到 Azure 自动化时，用户将收到接受许可证的提示。

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>在部署到 Azure 自动化时需要接受许可证

如果正在部署到 Azure 自动化的模块需要接受许可证，则门户 UI 将会显示内容为“此模块需要接受许可证。 单击“确定”接受许可证条款。”的声明

![部署到 Azure 自动化需要接受许可证](media/packages-that-require-license-acceptance/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>更多详细信息

[需要在 PowerShellGet 中接受许可证](../../concepts/module-license-acceptance.md)
[Azure 自动化网站](/azure/automation)
