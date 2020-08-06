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
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>如何调用 Cmdlet 中的脚本

此示例演示如何调用提供给 cmdlet 的脚本。 此脚本由 cmdlet 执行，并将其结果作为[system.object](/dotnet/api/System.Management.Automation.PSObject)对象的集合返回给 cmdlet。

## <a name="to-invoke-a-script-block"></a>调用脚本块

1. 命令验证是否向 cmdlet 提供了脚本块。 如果提供了脚本块，则该命令将使用其所需的参数调用脚本块。

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

2. 然后，该脚本将循环访问返回的[system.object](/dotnet/api/System.Management.Automation.PSObject)对象集合，并执行所需的操作。

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

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
