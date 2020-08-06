---
title: 如何支持事务 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6fda27394091195b589afef5ee53c6d3bec4efc0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786605"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="7a8f0-102">如何支持事务</span><span class="sxs-lookup"><span data-stu-id="7a8f0-102">How to Support Transactions</span></span>

<span data-ttu-id="7a8f0-103">此示例显示了向 cmdlet 添加对事务的支持的基本代码元素。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a8f0-104">有关 Windows PowerShell 如何处理事务的详细信息，请参阅[关于事务][about_Transactions]。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="7a8f0-105">支持事务</span><span class="sxs-lookup"><span data-stu-id="7a8f0-105">To support transactions</span></span>

1. <span data-ttu-id="7a8f0-106">声明 Cmdlet 属性时，指定该 cmdlet 支持事务。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="7a8f0-107">当 cmdlet 支持事务时，Windows PowerShell 会在 `UseTransaction` 运行时将参数添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="7a8f0-108">在其中一个输入处理方法中，添加一个 `if` 块来确定事务是否可用。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="7a8f0-109">如果 `if` 语句解析为 `true` ，则可以在当前事务的上下文中执行此语句内的操作。</span><span class="sxs-lookup"><span data-stu-id="7a8f0-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="7a8f0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a8f0-110">See Also</span></span>

[<span data-ttu-id="7a8f0-111">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7a8f0-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
