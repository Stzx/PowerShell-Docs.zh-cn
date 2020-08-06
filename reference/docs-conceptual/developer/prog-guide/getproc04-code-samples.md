---
title: GetProc04 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771951"
---
# <a name="getproc04-code-samples"></a>GetProc04 代码示例

下面是 GetProc04 cmdlet 的代码示例。 这是 `Get-Process` [将非终止错误报告添加到 cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)中所述的 cmdlet 示例。 `Get-Process`当检索进程信息时引发无效操作异常时，此 cmdlet 将调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法。

> [!NOTE]
> 你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件 (getprov04.cs cmdlet 下载 c # 源文件) 。 有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
>
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

有关完整的示例代码，请参阅以下主题。

|语言|主题|
|--------------|-----------|
|C#|[GetProc04 (C#) 示例代码](./getproc04-csharp-sample-code.md)|
|VB.NET|[GetProc04 (VB.NET) 示例代码](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
