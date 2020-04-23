---
ms.date: 06/12/2017
keywords: wmf,powershell,安装程序
title: 卸载WMF 5.0
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147857"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="4077e-103">卸载说明</span><span class="sxs-lookup"><span data-stu-id="4077e-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="4077e-104">使用命令提示符</span><span class="sxs-lookup"><span data-stu-id="4077e-104">Using Command Prompt</span></span>

1. <span data-ttu-id="4077e-105">打开  “命令提示符”。</span><span class="sxs-lookup"><span data-stu-id="4077e-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="4077e-106">运行 [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4077e-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="4077e-107">在 Windows Server 2012 R2 和 Windows 8.1 上：</span><span class="sxs-lookup"><span data-stu-id="4077e-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="4077e-108">在 Windows Server 2012 上：</span><span class="sxs-lookup"><span data-stu-id="4077e-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="4077e-109">在 Windows Server 2008 R2 SP1 和 Windows 7 SP1 上：</span><span class="sxs-lookup"><span data-stu-id="4077e-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="4077e-110">使用控制面板。</span><span class="sxs-lookup"><span data-stu-id="4077e-110">Using Control Panel</span></span>

1. <span data-ttu-id="4077e-111">打开  “控制面板”。</span><span class="sxs-lookup"><span data-stu-id="4077e-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="4077e-112">打开“程序”  ，然后打开  “卸载程序”。</span><span class="sxs-lookup"><span data-stu-id="4077e-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="4077e-113">单击  “查看已安装的更新”。</span><span class="sxs-lookup"><span data-stu-id="4077e-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="4077e-114">从已安装的更新列表中选择“Windows Management Framework 5.0”  。</span><span class="sxs-lookup"><span data-stu-id="4077e-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="4077e-115">这对应于 *KB3134758*、*KB3134759* 或 *KB3134760*。</span><span class="sxs-lookup"><span data-stu-id="4077e-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="4077e-116">单击  “卸载”。</span><span class="sxs-lookup"><span data-stu-id="4077e-116">Click **Uninstall.**</span></span>
