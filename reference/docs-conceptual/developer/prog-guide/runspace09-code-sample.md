---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace09 代码示例
description: RunSpace09 代码示例
ms.openlocfilehash: 52ebfa5dcfd6c12d2ded78a41a6090caa5087149
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654197"
---
# <a name="runspace09-code-sample"></a>RunSpace09 代码示例

下面是 [创建一个以异步方式调用管道的控制台应用程序](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)中所述的 Runspace09 示例的源代码。
此示例应用程序创建并打开运行空间，创建并异步调用管道，然后使用管道事件异步处理脚本。 此应用程序运行的脚本将以0.5 秒为间隔创建整数1到10， (500 ms) 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
