---
ms.date: 09/13/2016
ms.topic: reference
title: 如何支持事务
description: 如何支持事务
ms.openlocfilehash: 5691c246830dab9f4808801c04353ebfb2c3e981
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666954"
---
# <a name="how-to-support-transactions"></a>如何支持事务

此示例显示了向 cmdlet 添加对事务的支持的基本代码元素。

> [!IMPORTANT]
> 有关 Windows PowerShell 如何处理事务的详细信息，请参阅 [关于事务][about_Transactions]。

## <a name="to-support-transactions"></a>支持事务

1. 声明 Cmdlet 属性时，指定该 cmdlet 支持事务。
   当 cmdlet 支持事务时，Windows PowerShell 会在 `UseTransaction` 运行时将参数添加到 cmdlet。

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. 在其中一个输入处理方法中，添加一个 `if` 块来确定事务是否可用。
   如果 `if` 语句解析为 `true` ，则可以在当前事务的上下文中执行此语句内的操作。

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
