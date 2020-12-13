---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建和上传 CAB 文件
description: 如何创建和上传 CAB 文件
ms.openlocfilehash: bdcf534f48cff27b403d82440ad4ec6a3212b67d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653885"
---
# <a name="how-to-create-and-upload-cab-files"></a>如何创建和上传 CAB 文件

本主题说明如何创建可更新的帮助 CAB 文件，并将其上载到可更新的帮助 cmdlet 可以找到它们的位置。

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a>如何创建和上传可更新的帮助 CAB 文件

您可以使用 "可更新的帮助" 功能，为多语言和区域性中的模块提供新的或更新的帮助文件。 模块的可更新帮助包包括一个 HelpInfo XML 文件和一个或多个 cabinet (`.CAB`) 文件。 每个 CAB 文件都包含一个 UI 区域性中的模块的帮助文件。 使用以下过程来创建可更新帮助的 CAB 文件。

1. 按 UI 区域性组织模块的帮助文件。 每个可更新帮助 CAB 文件都包含一个 UI 区域性中某个模块的帮助文件。 可以为模块提供多个帮助 CAB 文件，每个文件都适用于不同的 UI 区域性。

1. 验证 "帮助" 文件只包含可更新帮助所允许的文件类型，并根据帮助文件架构对其进行验证。 如果此 `Update-Help` cmdlet 遇到无效的文件或不是允许的类型，则它不会安装无效文件，也不会停止从 CAB 安装文件。 有关允许的文件类型的列表，请参阅 [可更新的帮助 CAB 文件中允许的文件类型](./file-types-permitted-in-an-updatable-help-cab-file.md)。

1. 对帮助文件进行数字签名。 不需要数字签名，但这是最佳做法。

1. 包括 UI 区域性中的模块的所有帮助文件，而不仅是新的或已更改的文件。 如果 CAB 文件不完整，则首次下载帮助文件或不下载每个更新的用户将不会获得所有的模块帮助文件。

1. 使用创建 cabinet 文件的实用工具，如 `MakeCab.exe` 。 PowerShell 不包含用于创建 CAB 文件的 cmdlet。

1. 将 CAB 文件命名为。 有关详细信息，请参阅 [如何命名可更新的帮助 CAB 文件](./how-to-name-an-updatable-help-cab-file.md)。

1. 将模块的 CAB 文件上传到模块的 HelpInfo XML 文件中的 **HelpContentUri** 元素指定的位置。 然后，将 HelpInfo XML 文件上传到模块清单的 **HelpInfoUri** 键指定的位置。 **HelpContentUri** 和 **HelpInfoUri** 可以指向相同的位置。

> [!CAUTION]
> **HelpInfoUri** 键和 **HelpContentUri** 元素的值必须以 `http` 或开头 `https` 。 该值必须指示 Internet 位置，并且不能包含文件名。
