---
title: RunSpace08 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784684"
---
# <a name="runspace08-code-sample"></a>RunSpace08 代码示例

下面是[创建将参数添加到命令的控制台应用程序](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)中所述的 Runspace08 示例的源代码。
此示例应用程序创建一个运行空间，创建一个管道，将两个命令添加到管道，将两个参数添加到第二个命令，然后执行管道。 添加到管道中的命令是 `Get-Process` 和 `Sort-Object` cmdlet。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
