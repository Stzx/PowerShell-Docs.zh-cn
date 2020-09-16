---
ms.date: 06/12/2017
keywords: wmf,powershell,安装程序
title: 卸载WMF 5.0
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236299"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="467bd-103">卸载说明</span><span class="sxs-lookup"><span data-stu-id="467bd-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="467bd-104">使用命令提示符</span><span class="sxs-lookup"><span data-stu-id="467bd-104">Using Command Prompt</span></span>

1. <span data-ttu-id="467bd-105">打开“命令提示符”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="467bd-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="467bd-106">运行 [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="467bd-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="467bd-107">在 Windows Server 2012 R2 和 Windows 8.1 上：</span><span class="sxs-lookup"><span data-stu-id="467bd-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="467bd-108">在 Windows Server 2012 上：</span><span class="sxs-lookup"><span data-stu-id="467bd-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="467bd-109">在 Windows Server 2008 R2 SP1 和 Windows 7 SP1 上：</span><span class="sxs-lookup"><span data-stu-id="467bd-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="467bd-110">使用控制面板。</span><span class="sxs-lookup"><span data-stu-id="467bd-110">Using Control Panel</span></span>

1. <span data-ttu-id="467bd-111">打开“控制面板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="467bd-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="467bd-112">打开“程序”\*\*\*\*，然后打开“卸载程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="467bd-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="467bd-113">单击“查看已安装的更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="467bd-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="467bd-114">从已安装的更新列表中选择“Windows Management Framework 5.0”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="467bd-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="467bd-115">这对应于 *KB3134758*、*KB3134759* 或 *KB3134760*。</span><span class="sxs-lookup"><span data-stu-id="467bd-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="467bd-116">单击“卸载”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="467bd-116">Click **Uninstall.**</span></span>
