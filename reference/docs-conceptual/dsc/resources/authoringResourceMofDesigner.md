---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: 使用资源设计器工具
ms.openlocfilehash: 36eed0fc888380a03a3279e834748708f578d973
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500629"
---
# <a name="using-the-resource-designer-tool"></a><span data-ttu-id="999e4-103">使用资源设计器工具</span><span class="sxs-lookup"><span data-stu-id="999e4-103">Using the Resource Designer tool</span></span>

> <span data-ttu-id="999e4-104">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="999e4-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="999e4-105">资源设计器工具是一组由 **xDscResourceDesigner** 模块公开的 cmdlet，它使 Windows PowerShell Desired State Configuration (DSC) 的创建更加轻松简单。</span><span class="sxs-lookup"><span data-stu-id="999e4-105">The Resource Designer tool is a set of cmdlets exposed by the **xDscResourceDesigner** module that make creating Windows PowerShell Desired State Configuration (DSC) resources easier.</span></span> <span data-ttu-id="999e4-106">此资源中的 cmdlet 能帮助你创建新资源的 MOF 架构、脚本模块和目录结构。</span><span class="sxs-lookup"><span data-stu-id="999e4-106">The cmdlets in this resource help create the MOF schema, the script module, and the directory structure for your new resource.</span></span> <span data-ttu-id="999e4-107">有关 DSC 资源的详细信息，请参阅[构建自定义 Windows PowerShell Desired State Configuration 资源](authoringResource.md)。</span><span class="sxs-lookup"><span data-stu-id="999e4-107">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md).</span></span> <span data-ttu-id="999e4-108">在本主题中，我们将创建一个管理 Active Directory 用户的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="999e4-108">In this topic, we will create a DSC resource that manages Active Directory users.</span></span> <span data-ttu-id="999e4-109">使用 [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet 安装 **xDscResourceDesigner** 模块。</span><span class="sxs-lookup"><span data-stu-id="999e4-109">Use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xDscResourceDesigner** module.</span></span>

## <a name="creating-resource-properties"></a><span data-ttu-id="999e4-110">创建资源属性</span><span class="sxs-lookup"><span data-stu-id="999e4-110">Creating resource properties</span></span>
<span data-ttu-id="999e4-111">我们首先要确定资源将公开的属性。</span><span class="sxs-lookup"><span data-stu-id="999e4-111">The first thing we need to do is decide on properties that the resource will expose.</span></span> <span data-ttu-id="999e4-112">在此示例中，我们将通过以下属性来定义 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="999e4-112">For this example, we will define an Active Directory user with the following properties.</span></span>

<span data-ttu-id="999e4-113">参数名称  说明</span><span class="sxs-lookup"><span data-stu-id="999e4-113">Parameter name  Description</span></span>
* <span data-ttu-id="999e4-114">**UserName**：唯一标识用户的键属性。</span><span class="sxs-lookup"><span data-stu-id="999e4-114">**UserName**: Key property that uniquely identifies a user.</span></span>
* <span data-ttu-id="999e4-115">**Ensure**：指定用户帐户应该为 Present 还是 Absent。</span><span class="sxs-lookup"><span data-stu-id="999e4-115">**Ensure**: Specifies whether the user account should be Present or Absent.</span></span> <span data-ttu-id="999e4-116">此参数只有两个可能的值。</span><span class="sxs-lookup"><span data-stu-id="999e4-116">This parameter will have only two possible values.</span></span>
* <span data-ttu-id="999e4-117">**DomainCredential**：用户的域密码。</span><span class="sxs-lookup"><span data-stu-id="999e4-117">**DomainCredential**: The domain password for the user.</span></span>
* <span data-ttu-id="999e4-118">**密码**：允许必要时配置对用户密码进行更改所需的用户密码。</span><span class="sxs-lookup"><span data-stu-id="999e4-118">**Password**: The desired password for the user to allow a configuration to change the user password if necessary.</span></span>

<span data-ttu-id="999e4-119">我们使用 **New-xDscResourceProperty** cmdlet 来创建属性。</span><span class="sxs-lookup"><span data-stu-id="999e4-119">To create the properties, we use the **New-xDscResourceProperty** cmdlet.</span></span> <span data-ttu-id="999e4-120">下面的 PowerShell 命令可以创建上述属性。</span><span class="sxs-lookup"><span data-stu-id="999e4-120">The following PowerShell commands create the properties described above.</span></span>

```powershell
$UserName = New-xDscResourceProperty –Name UserName -Type String -Attribute Key
$Ensure = New-xDscResourceProperty –Name Ensure -Type String -Attribute Write –ValidateSet "Present", "Absent"
$DomainCredential = New-xDscResourceProperty –Name DomainCredential -Type PSCredential -Attribute Write
$Password = New-xDscResourceProperty –Name Password -Type PSCredential -Attribute Write
```

## <a name="create-the-resource"></a><span data-ttu-id="999e4-121">创建资源</span><span class="sxs-lookup"><span data-stu-id="999e4-121">Create the resource</span></span>

<span data-ttu-id="999e4-122">创建好资源属性后，我们就可以调用 **New-xDscResource** cmdlet 来创建资源。</span><span class="sxs-lookup"><span data-stu-id="999e4-122">Now that the resource properties have been created, we can call the **New-xDscResource** cmdlet to create the resource.</span></span> <span data-ttu-id="999e4-123">**New-xDscResource** cmdlet 采用了属性列表作为参数。</span><span class="sxs-lookup"><span data-stu-id="999e4-123">The **New-xDscResource** cmdlet takes the list of properties as parameters.</span></span> <span data-ttu-id="999e4-124">它还采用了应将模块创建于的路径、新资源的名称以及包含它的模块名称。</span><span class="sxs-lookup"><span data-stu-id="999e4-124">It also takes the path where the module should be created, the name of the new resource, and the name of the module in which it is contained.</span></span> <span data-ttu-id="999e4-125">下面的 PowerShell 命令可以创建资源。</span><span class="sxs-lookup"><span data-stu-id="999e4-125">The following PowerShell command creates the resource.</span></span>

```powershell
New-xDscResource –Name Demo_ADUser –Property $UserName, $Ensure, $DomainCredential, $Password –Path 'C:\Program Files\WindowsPowerShell\Modules' –ModuleName Demo_DSCModule
```

<span data-ttu-id="999e4-126">**New-xDscResource** cmdlet 创建 MOF 架构、主干资源脚本、新资源所需目录结构以及公开新资源的模块清单。</span><span class="sxs-lookup"><span data-stu-id="999e4-126">The **New-xDscResource** cmdlet creates the MOF schema, a skeleton resource script, the required directory structure for your new resource, and a manifest for the module that exposes the new resource.</span></span>

<span data-ttu-id="999e4-127">MOF 架构文件位于 **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof**，其内容如下。</span><span class="sxs-lookup"><span data-stu-id="999e4-127">The MOF schema file is at **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof**, and its contents are as follows.</span></span>

```
[ClassVersion("1.0.0.0"), FriendlyName("Demo_ADUser")]
class Demo_ADUser : OMI_BaseResource
{
  [Key] string UserName;
  [Write, ValueMap{"Present","Absent"}, Values{"Present","Absent"}] string Ensure;
  [Write, EmbeddedInstance("MSFT_Credential")] String DomainCredential;
  [Write, EmbeddedInstance("MSFT_Credential")] String Password;
};
```

<span data-ttu-id="999e4-128">资源脚本位于 **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1**。</span><span class="sxs-lookup"><span data-stu-id="999e4-128">The resource script is at **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1**.</span></span>
<span data-ttu-id="999e4-129">资源脚本不包含实现资源的实际逻辑，你必须自己添加。</span><span class="sxs-lookup"><span data-stu-id="999e4-129">It does not include the actual logic to implement the resource, which you must add yourself.</span></span> <span data-ttu-id="999e4-130">主干脚本的内容如下。</span><span class="sxs-lookup"><span data-stu-id="999e4-130">The contents of the skeleton script are as follows.</span></span>

```powershell
function Get-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Collections.Hashtable])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."


  <#
  $returnValue = @{
  UserName = [System.String]
  Ensure = [System.String]
  DomainAdminCredential = [System.Management.Automation.PSCredential]
  Password = [System.Management.Automation.PSCredential]
  }

  $returnValue
  #>
}


function Set-TargetResource
{
  [CmdletBinding()]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  #Include this line if the resource requires a system reboot.
  #$global:DSCMachineStatus = 1


}


function Test-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Boolean])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."


  <#
  $result = [System.Boolean]

  $result
  #>
}


Export-ModuleMember -Function *-TargetResource
```

## <a name="updating-the-resource"></a><span data-ttu-id="999e4-131">更新资源</span><span class="sxs-lookup"><span data-stu-id="999e4-131">Updating the resource</span></span>

<span data-ttu-id="999e4-132">如果需要添加或修改资源的参数列表，可以调用 **Update-xDscResource** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="999e4-132">If you need to add or modify the parameter list of the resource, you can call the **Update-xDscResource** cmdlet.</span></span> <span data-ttu-id="999e4-133">该 cmdlet 将使用新参数列表更新资源。</span><span class="sxs-lookup"><span data-stu-id="999e4-133">The cmdlet updates the resource with a new parameter list.</span></span> <span data-ttu-id="999e4-134">如果你已在资源脚本中添加逻辑，它将保持不变。</span><span class="sxs-lookup"><span data-stu-id="999e4-134">If you have already added logic in your resource script, it is left intact.</span></span>

<span data-ttu-id="999e4-135">例如，假如你想为用户将最新日志包含在资源中。</span><span class="sxs-lookup"><span data-stu-id="999e4-135">For example, suppose you want to include the last log in time for the user in our resource.</span></span> <span data-ttu-id="999e4-136">你可以调用 **New-xDscResourceProperty** 创建新属性，然后调用 **Update-xDscResource** 并将新属性添加到属性列表，而不用重新编写资源。</span><span class="sxs-lookup"><span data-stu-id="999e4-136">Rather than writing the resource again completely, you can call the **New-xDscResourceProperty** to create the new property, and then call **Update-xDscResource** and add your new property to the properties list.</span></span>

```powershell
$lastLogon = New-xDscResourceProperty –Name LastLogon –Type Hashtable –Attribute Write –Description "For mapping users to their last log on time"
Update-xDscResource –Name 'Demo_ADUser' –Property $UserName, $Ensure, $DomainCredential, $Password, $lastLogon -Force
```

## <a name="testing-a-resource-schema"></a><span data-ttu-id="999e4-137">测试资源架构</span><span class="sxs-lookup"><span data-stu-id="999e4-137">Testing a resource schema</span></span>

<span data-ttu-id="999e4-138">资源设计器工具还公开了一个 cmdlet，可用于测试手动编写的 MOF 架构的有效性。</span><span class="sxs-lookup"><span data-stu-id="999e4-138">The Resource Designer tool exposes one more cmdlet that can be used to test the validity of a MOF schema that you have written manually.</span></span> <span data-ttu-id="999e4-139">调用 **Test-xDscSchema** cmdlet，将 MOF 资源架构的路径作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="999e4-139">Call the **Test-xDscSchema** cmdlet, passing the path of a MOF resource schema as a parameter.</span></span> <span data-ttu-id="999e4-140">该 cmdlet 将输出架构中的任何错误。</span><span class="sxs-lookup"><span data-stu-id="999e4-140">The cmdlet will output any errors in the schema.</span></span>

### <a name="see-also"></a><span data-ttu-id="999e4-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="999e4-141">See Also</span></span>

#### <a name="concepts"></a><span data-ttu-id="999e4-142">概念</span><span class="sxs-lookup"><span data-stu-id="999e4-142">Concepts</span></span>
[<span data-ttu-id="999e4-143">构建自定义 Windows PowerShell Desired State Configuration 资源</span><span class="sxs-lookup"><span data-stu-id="999e4-143">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)

#### <a name="other-resources"></a><span data-ttu-id="999e4-144">其他资源</span><span class="sxs-lookup"><span data-stu-id="999e4-144">Other Resources</span></span>
[<span data-ttu-id="999e4-145">xDscResourceDesigner 模块</span><span class="sxs-lookup"><span data-stu-id="999e4-145">xDscResourceDesigner Module</span></span>](https://www.powershellgallery.com/packages/xDscResourceDesigner/1.12.0.0)
