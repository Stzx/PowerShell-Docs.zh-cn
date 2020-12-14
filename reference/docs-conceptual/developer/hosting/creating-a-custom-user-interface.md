---
ms.date: 09/13/2016
ms.topic: reference
title: 创建自定义用户界面
description: 创建自定义用户界面
ms.openlocfilehash: 411165f868cd524c0cef0ba9cce3188c60a7dbdf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645401"
---
# <a name="creating-a-custom-user-interface"></a>创建自定义用户界面

Windows PowerShell 提供抽象类和接口，这些类和接口使你能够创建一个托管 Windows PowerShell 引擎的自定义交互 UI。 若要创建自定义 UI，你必须实现 [PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) 类。 （可选）还可以实现 [Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)和 [Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) 类，以及和 [Ihostsupportsinteractivesession 和](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) 和 [Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) 接口中的类的类和类的类的接口的接口的类和接口。
