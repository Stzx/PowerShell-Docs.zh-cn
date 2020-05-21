---
title: 提供程序 cmdlet 动态参数 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f1069f7-8fa8-4622-9e2c-af29b0b961c2
caps.latest.revision: 6
ms.openlocfilehash: 9e70fbeaef61d04e66f16d06519742ff2f679df6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564234"
---
# <a name="provider-cmdlet-dynamic-parameters"></a><span data-ttu-id="2aa5a-102">提供程序 cmdlet 动态参数</span><span class="sxs-lookup"><span data-stu-id="2aa5a-102">Provider cmdlet dynamic parameters</span></span>

<span data-ttu-id="2aa5a-103">当用户为 cmdlet 的一个静态参数指定特定值时，提供程序可以定义添加到提供程序 cmdlet 的动态参数。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-103">Providers can define dynamic parameters that are added to a provider cmdlet when the user specifies a certain value for one of the static parameters of the cmdlet.</span></span> <span data-ttu-id="2aa5a-104">例如，提供程序可以根据用户在调用 `Get-Item` 或提供程序 cmdlet 时指定的路径来添加不同的动态参数 `Set-Item` 。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-104">For example, a provider can add different dynamic parameters based on what path the user specifies when they call the `Get-Item` or `Set-Item` provider cmdlets.</span></span>

## <a name="dynamic-parameter-methods"></a><span data-ttu-id="2aa5a-105">动态参数方法</span><span class="sxs-lookup"><span data-stu-id="2aa5a-105">Dynamic Parameter Methods</span></span>

<span data-ttu-id="2aa5a-106">动态参数是通过实现某个动态参数方法（例如[Itemcmdletprovider. Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)和[Itemcmdletprovider. Setitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s 方法）来定义的，该方法是。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-106">Dynamic parameters are defined by implementing one of the dynamic parameter methods, such as the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s methods.</span></span> <span data-ttu-id="2aa5a-107">这些方法返回一个对象，该对象具有使用类似于独立 cmdlet 的特性修饰的公共属性。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-107">These methods return an object that has public properties that are decorated with attributes similar to those of stand-alone cmdlets.</span></span> <span data-ttu-id="2aa5a-108">下面是从证书提供程序中获取的[Itemcmdletprovider. Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)方法的实现示例：</span><span class="sxs-lookup"><span data-stu-id="2aa5a-108">Here is an example of an implementation of the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) method taken from the Certificate provider:</span></span>

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

<span data-ttu-id="2aa5a-109">与提供程序 cmdlet 的静态参数不同，可以指定这些参数的特征，方法与在独立 cmdlet 中定义参数的方式相同。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-109">Unlike the static parameters of provider cmdlets, you can specify the characteristics of these parameters in the same way that parameters are defined in stand-alone cmdlets.</span></span> <span data-ttu-id="2aa5a-110">下面是从证书提供程序获取的动态参数类的示例：</span><span class="sxs-lookup"><span data-stu-id="2aa5a-110">Here is an example of a dynamic parameter class taken from the Certificate provider:</span></span>

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

## <a name="dynamic-parameters"></a><span data-ttu-id="2aa5a-111">动态参数</span><span class="sxs-lookup"><span data-stu-id="2aa5a-111">Dynamic Parameters</span></span>

<span data-ttu-id="2aa5a-112">下面是可用于添加动态参数的静态参数的列表。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-112">Here is a list of the static parameters that can be used to add dynamic parameters.</span></span>

<span data-ttu-id="2aa5a-113">`Clear-Content`cmdlet 可以 `Path` 通过实现[Icontentcmdletprovider. Clearcontentdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)方法来定义由 clear 明文 cmdlet 的参数触发的动态参数（& a）。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-113">`Clear-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the Clear-Clear cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-114">`Clear-Item`cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Clear-Item` 方法是实现[Clearitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-114">`Clear-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Clear-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-115">`Clear-ItemProperty`cmdlet 可以通过实现 Ipropertycmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Clear-ItemProperty` 方法是实现[Clearpropertydynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-115">`Clear-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Clear-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-116">`Copy-Item`cmdlet 可以 `Path` `Destination` `Recurse` `Copy-Item` 通过实现[Containercmdletprovider. Copyitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)方法来定义由 cmdlet 的、和参数触发的动态参数。）。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-116">`Copy-Item` cmdlet You can define dynamic parameters that are triggered by the `Path`, `Destination`, and `Recurse` parameters of the `Copy-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-117">ChildItems cmdlet 可通过实现 Containercmdletprovider 和 Getchilditemsdynamicparameters \* 方法来定义由 cmdlet 的和参数触发的动态参数。 `Path` `Recurse` `Get-ChildItem` [\* 和](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) [\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)方法的，可由 cmdlet 来定义。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-117">Get-ChildItems cmdlet You can define dynamic parameters that are triggered by the `Path` and `Recurse` parameters of the `Get-ChildItem` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) and [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) methods.</span></span>

<span data-ttu-id="2aa5a-118">`Get-Content`cmdlet 可以通过实现 Icontentcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Get-Content` 方法是实现[Getcontentreaderdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-118">`Get-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Get-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-119">`Get-Item`cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Get-Item` 方法是实现[Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-119">`Get-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Get-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-120">`Get-ItemProperty`cmdlet 可以 `Path` `Name` `Get-ItemProperty` 通过实现[Ipropertycmdletprovider. Getpropertydynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)方法来定义由 cmdlet 的和参数触发的动态参数。 "</span><span class="sxs-lookup"><span data-stu-id="2aa5a-120">`Get-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Name` parameters of the `Get-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-121">`Invoke-Item`cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Invoke-Item` 方法是实现[Invokedefaultactiondynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-121">`Invoke-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Invoke-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-122">`Move-Item`cmdlet 可以 `Path` `Destination` `Move-Item` 通过实现[Navigationcmdletprovider. Moveitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)方法来定义由 cmdlet 的和参数触发的动态参数。 "</span><span class="sxs-lookup"><span data-stu-id="2aa5a-122">`Move-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Destination` parameters of the `Move-Item` cmdlet by implementing the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-123">`New-Item`cmdlet 可以 `Path` `ItemType` `Value` `New-Item` 通过实现[Containercmdletprovider. Newitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)方法来定义由 cmdlet 的、和参数触发的动态参数。）。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-123">`New-Item` cmdlet You can define dynamic parameters that are triggered by the `Path`, `ItemType`, and `Value` parameters of the `New-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-124">`New-ItemProperty`cmdlet 可以 `Path` 通过实现 Newpropertydynamicparameters \* 方法来定义由 cmdlet 的、、和参数触发的动态参数。 `Name` `PropertyType` `Value` `New-ItemProperty` [Idynamicpropertycmdletprovider. \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-124">`New-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path`, `Name`, `PropertyType`, and `Value` parameters of the `New-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-125">`New-PSDrive`cmdlet 可以通过实现 Drivecmdletprovider，定义由 cmdlet 返回的[即 system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)对象所触发的动态参数。 `New-PSDrive` [. Newdrivedynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)方法，可定义这些参数。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-125">`New-PSDrive` cmdlet You can define dynamic parameters that are triggered by the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object returned by the `New-PSDrive` cmdlet by implementing the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-126">`Remove-Item`通过实现 Removeitemdynamicparameters \* 方法，你可以定义由 cmdlet 的和参数触发的动态参数。 `Path` `Recurse` `Remove-Item` [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-126">`Remove-Item` You can define dynamic parameters that are triggered by the `Path` and `Recurse` parameters of the `Remove-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-127">`Remove-ItemProperty`通过实现 Removepropertydynamicparameters \* 方法，你可以定义由 cmdlet 的和参数触发的动态参数。 `Path` `Name` `Remove-ItemProperty` [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-127">`Remove-ItemProperty` You can define dynamic parameters that are triggered by the `Path` and `Name` parameters of the `Remove-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-128">`Rename-Item`cmdlet 可以 `Path` `NewName` `Rename-Item` 通过实现[Containercmdletprovider. Renameitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)方法来定义由 cmdlet 的和参数触发的动态参数。 "</span><span class="sxs-lookup"><span data-stu-id="2aa5a-128">`Rename-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `NewName` parameters of the `Rename-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-129">`Rename-ItemProperty`你可以 `Path` `Name` `NewName` `Rename-ItemProperty` 通过实现[Idynamicpropertycmdletprovider. Renamepropertydynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)方法，定义由 cmdlet 的、和参数触发的动态参数。 "</span><span class="sxs-lookup"><span data-stu-id="2aa5a-129">`Rename-ItemProperty` You can define dynamic parameters that are triggered by the `Path`, `Name`, and `NewName` parameters of the `Rename-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-130">`Set-Content`cmdlet 可以通过实现 Icontentcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Set-Content` 方法是实现[Getcontentwriterdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-130">`Set-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Set-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-131">`Set-Item`cmdlet 可以 `Path` `Value` `Set-Item` 通过实现[Itemcmdletprovider. Setitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)方法来定义由 cmdlet 的和参数触发的动态参数。 "</span><span class="sxs-lookup"><span data-stu-id="2aa5a-131">`Set-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-132">`Set-ItemProperty`cmdlet 可以 `Path` `Value` `Set-Item` 通过实现[Ipropertycmdletprovider. Setpropertydynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)方法来定义由 cmdlet 的和参数触发的动态参数。 "</span><span class="sxs-lookup"><span data-stu-id="2aa5a-132">`Set-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="2aa5a-133">`Test-Path`cmdlet 可以通过实现 Itemcmdletprovider 来定义由 cmdlet 的参数触发的动态参数， `Path` `Test-Path` 方法是实现[Invokedefaultactiondynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="2aa5a-133">`Test-Path` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Test-Path` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) method.</span></span>

## <a name="see-also"></a><span data-ttu-id="2aa5a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2aa5a-134">See Also</span></span>

[<span data-ttu-id="2aa5a-135">编写 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="2aa5a-135">Writing a Windows PowerShell Provider</span></span>](./writing-a-windows-powershell-provider.md)
