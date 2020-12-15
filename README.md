---
ms.openlocfilehash: 61a70db9ae7a38d6731f1cefb011072c12d1e39a
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514912"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Microsoft 开放源代码行为准则

> 更新时间：2020/11/02

此项目采用了 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。 有关详细信息，请参阅[行为准则常见问题](https://opensource.microsoft.com/codeofconduct/faq/)，或如果有任何其他问题或意见，请与 [opencode@microsoft.com](mailto:opencode@microsoft.com) 联系。

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>生成状态

|          活动分支          |           临时分支            |
| :---------------------------- | :---------------------------------- |
| [![live-badge][]][live-badge] | [![staging-badge][]][staging-badge] |

## <a name="powershell-documentation"></a>PowerShell 文档

欢迎使用 PowerShell 文档存储库，其中包含官方 PowerShell 文档。

## <a name="repository-structure"></a>存储库结构

以下列表列出了此存储库中的主文件夹。

- `.github` -包含 GitHub 用于此存储库的配置设置
- `.vscode` - 包含 Visual Studio Code (VS Code) 的配置设置和建议扩展
- `assets` - 包含文档中链接的可下载文件
- `reference` - 包含发布到 [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/) 的文档。 这包括引用和概念内容。
  - `5.1` - 包含 PowerShell 5.1 的 cmdlet 参考和“关于”主题
  - `7.0` - 包含 PowerShell 7.0 的 cmdlet 参考和“关于”主题
  - `7.1` - 包含 PowerShell 7.1 的 cmdlet 参考和“关于”主题
  - `7.2` - 包含 PowerShell 7.2 的 cmdlet 参考和“关于”主题（预览版）
  - `bread` - 包含用于痕迹导航的 TOC
  - `docs-conceptual` - 包含发布到 Docs 站点的概念文章。 通常，文件夹结构会建立目录 (TOC) 镜像。
  - `mapping` - 包含生成系统使用的版本映射配置
  - `media` - 包含文档中使用的图像文件。 `docs-conceptual` 内容中有媒体文件夹。 有关在文档中使用图像的信息，请参阅“参与者指南”。
  - `module` - 包含“模块浏览器”页面的 markdown 源
- `tests` - 包含生成系统使用的 Pester 测试
- `tools` - 包含生成系统使用的其他工具

> 注意：参考内容（在编号文件夹中）用于在 Docs 站点上创建网页，也可用作针对 PowerShell 的可更新帮助。
> `docs-conceptual` 文件夹中的文章仅发布到 Docs 网站。

## <a name="contributing"></a>供稿

通过[拉取请求](https://help.github.com/articles/using-pull-requests/)到临时分支，我们欢迎将贡献的公共文档并入此存储库。
请注意，必须签署我们的[贡献许可协议](https://cla.microsoft.com/)，我们才会接受你的拉取请求。 只需执行此操作一次。

若要详细了解如何参与，请阅读[参与者指南](https://aka.ms/PSDocsContributor)。 参与者指南详细介绍了如何参与撰写文档、推荐的工具以及样式和格式设置要求。 请使用“问题和提取请求”模板来帮助文档在各版本之间保持一致性。

## <a name="licenses"></a>许可证

此项目有两个许可证文件。 MIT 许可证适用于包含在此存储库中的代码。 Creative Commons 许可证适用于文档。
