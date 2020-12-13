---
ms.date: 09/13/2016
ms.topic: reference
title: 提供程序 cmdlet 动态参数
description: 提供程序 cmdlet 动态参数
ms.openlocfilehash: ac05a847afb0729c34d733fa4ba8da11f46746fe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662977"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>提供程序 cmdlet 动态参数

当用户为 cmdlet 的一个静态参数指定特定值时，提供程序可以定义添加到提供程序 cmdlet 的动态参数。 例如，提供程序可以根据用户在调用 `Get-Item` 或提供程序 cmdlet 时指定的路径来添加不同的动态参数 `Set-Item` 。

## <a name="dynamic-parameter-methods"></a>动态参数方法

动态参数是通过实现某个动态参数方法（例如 [Itemcmdletprovider. Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) 和 [Itemcmdletprovider. Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s 方法）来定义的，该方法是。 这些方法返回一个对象，该对象具有使用类似于独立 cmdlet 的特性修饰的公共属性。 下面是从证书提供程序中获取的 [Itemcmdletprovider. Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) 方法的实现示例：

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

与提供程序 cmdlet 的静态参数不同，可以指定这些参数的特征，方法与在独立 cmdlet 中定义参数的方式相同。 下面是从证书提供程序获取的动态参数类的示例：

```csharp
internal sealed class CertificateProviderDynamicParameters
{
  /// <summary>
  /// Dynamic parameter the controls whether we only return
  /// code signing certs.
  /// </summary>
  [Parameter()]
  public SwitchParameter CodeSigningCert
  {
    get
    {
      {
        return codeSigningCert;
      }
    }

    set
    {
      {
        codeSigningCert = value;
      }
    }
  }

    private SwitchParameter codeSigningCert = new SwitchParameter();
}
```

## <a name="dynamic-parameters"></a>动态参数

下面是可用于添加动态参数的静态参数的列表。

`Clear-Content` cmdlet 可以 `Path` 通过实现 Icontentcmdletprovider，通过实现 [Clearcontentdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) 方法来定义由 Clear-Clear cmdlet 的参数触发的动态参数。

`Clear-Item` cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Clear-Item` 方法是实现 [Clearitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) 方法。

`Clear-ItemProperty` cmdlet 可以通过实现 Ipropertycmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Clear-ItemProperty` 方法是实现 [Clearpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) 方法。

`Copy-Item` cmdlet 可以 `Path` `Destination` `Recurse` `Copy-Item` 通过实现 [Containercmdletprovider. Copyitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) 方法来定义由 cmdlet 的、和参数触发的动态参数。）。

Get-ChildItems cmdlet，可以 `Path` `Recurse` `Get-ChildItem` 通过实现 [Getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) 和 [Containercmdletprovider. Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) 方法，定义由 cmdlet 的和参数触发的动态参数。 Containercmdletprovider * 方法的参数的参数。

`Get-Content` cmdlet 可以通过实现 Icontentcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Get-Content` 方法是实现 [Getcontentreaderdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) 方法。

`Get-Item` cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Get-Item` 方法是实现 [Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) 方法。

`Get-ItemProperty` cmdlet 可以 `Path` `Name` `Get-ItemProperty` 通过实现 [Ipropertycmdletprovider. Getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) 方法来定义由 cmdlet 的和参数触发的动态参数。 "

`Invoke-Item` cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Invoke-Item` 方法是实现 [Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) 方法。

`Move-Item` cmdlet 可以 `Path` `Destination` `Move-Item` 通过实现 [Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) 方法来定义由 cmdlet 的和参数触发的动态参数。 "

`New-Item` cmdlet 可以 `Path` `ItemType` `Value` `New-Item` 通过实现 [Containercmdletprovider. Newitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) 方法来定义由 cmdlet 的、和参数触发的动态参数。）。

`New-ItemProperty` cmdlet 可以 `Path` 通过实现 Newpropertydynamicparameters * 方法来定义由 cmdlet 的、、和参数触发的动态参数。 `Name` `PropertyType` `Value` `New-ItemProperty` [Idynamicpropertycmdletprovider. *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) 方法。

`New-PSDrive` cmdlet 可以定义由 cmdlet 返回的 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) 对象触发的动态参数，方法是 `New-PSDrive` 实现 [Drivecmdletprovider. Newdrivedynamicparameters *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) 方法。

`Remove-Item` 通过实现 Removeitemdynamicparameters * 方法，你可以定义由 cmdlet 的和参数触发的动态参数。 `Path` `Recurse` `Remove-Item` [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) 方法。

`Remove-ItemProperty` 通过实现 Removepropertydynamicparameters * 方法，你可以定义由 cmdlet 的和参数触发的动态参数。 `Path` `Name` `Remove-ItemProperty` [Idynamicpropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) 方法。

`Rename-Item` cmdlet 可以 `Path` `NewName` `Rename-Item` 通过实现 [Containercmdletprovider. Renameitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) 方法来定义由 cmdlet 的和参数触发的动态参数。 "

`Rename-ItemProperty` 你可以 `Path` `Name` `NewName` `Rename-ItemProperty` 通过实现 [Idynamicpropertycmdletprovider. Renamepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) 方法，定义由 cmdlet 的、和参数触发的动态参数。 "

`Set-Content` cmdlet 可以通过实现 Icontentcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Set-Content` 方法是实现 [Getcontentwriterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) 方法。

`Set-Item` cmdlet 可以 `Path` `Value` `Set-Item` 通过实现 [Itemcmdletprovider. Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) 方法来定义由 cmdlet 的和参数触发的动态参数。 "

`Set-ItemProperty` cmdlet 可以 `Path` `Value` `Set-Item` 通过实现 [Ipropertycmdletprovider. Setpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) 方法来定义由 cmdlet 的和参数触发的动态参数。 "

`Test-Path` cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Test-Path` 方法是实现 [Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) 方法。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 提供程序](./writing-a-windows-powershell-provider.md)
