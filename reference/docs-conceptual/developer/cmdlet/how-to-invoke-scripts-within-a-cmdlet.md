---
title: 如何在 Cmdlet 中调用脚本 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 248ad7e2e35fe53682836d094a391023007fa0b7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784123"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="60df6-102">如何调用 Cmdlet 中的脚本</span><span class="sxs-lookup"><span data-stu-id="60df6-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="60df6-103">此示例演示如何调用提供给 cmdlet 的脚本。</span><span class="sxs-lookup"><span data-stu-id="60df6-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="60df6-104">此脚本由 cmdlet 执行，并将其结果作为[system.object](/dotnet/api/System.Management.Automation.PSObject)对象的集合返回给 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60df6-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="60df6-105">调用脚本块</span><span class="sxs-lookup"><span data-stu-id="60df6-105">To invoke a script block</span></span>

1. <span data-ttu-id="60df6-106">命令验证是否向 cmdlet 提供了脚本块。</span><span class="sxs-lookup"><span data-stu-id="60df6-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="60df6-107">如果提供了脚本块，则该命令将使用其所需的参数调用脚本块。</span><span class="sxs-lookup"><span data-stu-id="60df6-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. <span data-ttu-id="60df6-108">然后，该脚本将循环访问返回的[system.object](/dotnet/api/System.Management.Automation.PSObject)对象集合，并执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="60df6-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a><span data-ttu-id="60df6-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60df6-109">See Also</span></span>

[<span data-ttu-id="60df6-110">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="60df6-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
