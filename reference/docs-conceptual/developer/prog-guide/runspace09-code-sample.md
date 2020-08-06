---
title: RunSpace09 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fc5d8d4d182cca6bfc42d63c68a14a7a5e5f9c97
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784667"
---
# <a name="runspace09-code-sample"></a>RunSpace09 代码示例

下面是[创建一个以异步方式调用管道的控制台应用程序](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)中所述的 Runspace09 示例的源代码。
此示例应用程序创建并打开运行空间，创建并异步调用管道，然后使用管道事件异步处理脚本。 此应用程序运行的脚本将以0.5 秒为间隔创建整数1到10， (500 ms) 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
