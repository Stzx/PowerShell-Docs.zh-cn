---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: e2e2166bbe65256c67937be8da1a3e82944840e8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343226"
---
# <span data-ttu-id="8abc1-103">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="8abc1-103">Set-Acl</span></span>

## <span data-ttu-id="8abc1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8abc1-104">SYNOPSIS</span></span>
<span data-ttu-id="8abc1-105">更改指定项（如文件或注册表项）的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-105">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="8abc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8abc1-106">SYNTAX</span></span>

### <span data-ttu-id="8abc1-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="8abc1-107">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>] [-ClearCentralAccessPolicy]
 [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="8abc1-108">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="8abc1-108">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="8abc1-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="8abc1-109">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>]
 [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="8abc1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8abc1-110">DESCRIPTION</span></span>

<span data-ttu-id="8abc1-111">`Set-Acl`Cmdlet 更改指定项（如文件或注册表项）的安全描述符，以与你提供的安全描述符中的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="8abc1-111">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="8abc1-112">若要使用 `Set-Acl` ，请使用 **Path** 或 **InputObject** 参数来识别要更改其安全描述符的项。</span><span class="sxs-lookup"><span data-stu-id="8abc1-112">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="8abc1-113">然后，使用 **AclObject** 或 **SecurityDescriptor** 参数来提供具有要应用的值的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-113">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="8abc1-114">`Set-Acl` 应用提供的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-114">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="8abc1-115">它将 **AclObject** 参数的值用作模型，并更改项的安全描述符中的值，以与 **AclObject** 参数中的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="8abc1-115">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="8abc1-116">示例</span><span class="sxs-lookup"><span data-stu-id="8abc1-116">EXAMPLES</span></span>

### <span data-ttu-id="8abc1-117">示例1：将安全描述符从一个文件复制到另一个文件</span><span class="sxs-lookup"><span data-stu-id="8abc1-117">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="8abc1-118">这些命令将值从 Dog.txt 文件的安全描述符复制到 Cat.txt 文件的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-118">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="8abc1-119">完成这些命令后，Dog.txt 文件和 Cat.txt 文件的安全描述符将完全相同。</span><span class="sxs-lookup"><span data-stu-id="8abc1-119">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="8abc1-120">第一个命令使用 `Get-Acl` cmdlet 来获取 Dog.txt 文件的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="8abc1-121">赋值运算符 (`=`) 将安全描述符存储在 $DogACL 变量的值中。</span><span class="sxs-lookup"><span data-stu-id="8abc1-121">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="8abc1-122">第二个命令使用将 `Set-Acl` Cat.txt 的 ACL 中的值更改为中的值 `$DogACL` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-122">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="8abc1-123">**Path** 参数的值是 Cat.txt 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="8abc1-123">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="8abc1-124">**AclObject** 参数的值是模型 acl，在此示例中，是在变量中保存的 Dog.txt 的 acl `$DogACL` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-124">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="8abc1-125">示例2：使用管道运算符传递描述符</span><span class="sxs-lookup"><span data-stu-id="8abc1-125">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="8abc1-126">此命令与上一示例中的命令几乎相同，不同之处在于它使用管道运算符 (`|`) 将安全描述符从 `Get-Acl` 命令发送到 `Set-Acl` 命令。</span><span class="sxs-lookup"><span data-stu-id="8abc1-126">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="8abc1-127">第一个命令使用 `Get-Acl` cmdlet 来获取 Dog.txt 文件的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-127">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="8abc1-128">管道运算符 (`|`) 将表示 Dog.txt 安全描述符的对象传递给 `Set-Acl` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8abc1-128">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="8abc1-129">第二个命令使用将 `Set-Acl` Dog.txt 的安全描述符应用到 Cat.txt。</span><span class="sxs-lookup"><span data-stu-id="8abc1-129">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="8abc1-130">完成该命令后，Dog.txt 和 Cat.txt 文件的 ACL 将完全相同。</span><span class="sxs-lookup"><span data-stu-id="8abc1-130">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="8abc1-131">示例3：将安全描述符应用于多个文件</span><span class="sxs-lookup"><span data-stu-id="8abc1-131">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="8abc1-132">这些命令将 File0.txt 文件中的安全描述符应用于 `C:\Temp` 目录及其所有子目录中的所有文本文件。</span><span class="sxs-lookup"><span data-stu-id="8abc1-132">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="8abc1-133">第一个命令将获取当前目录中 File0.txt 文件的安全描述符，并使用赋值运算符 () 将 `=` 其存储在 `$NewACL` 变量中。</span><span class="sxs-lookup"><span data-stu-id="8abc1-133">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="8abc1-134">管道中的第一个命令使用 Get-ChildItem cmdlet 获取目录中的所有文本文件 `C:\Temp` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-134">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="8abc1-135">**递归** 参数将该命令扩展到的所有子目录 `C:\temp` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-135">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="8abc1-136">**Include** 参数将检索到的文件限制为文件扩展名为的文件 `.txt` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-136">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="8abc1-137">**Force** 参数将获取本来会被排除的隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="8abc1-137">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="8abc1-138"> (不能使用 `c:\temp\*.txt` ，因为 **递归** 参数适用于目录而非文件。 ) </span><span class="sxs-lookup"><span data-stu-id="8abc1-138">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="8abc1-139">管道运算符 (`|`) 将表示检索到的文件的对象发送到 `Set-Acl` cmdlet，这会将 **AclObject** 参数中的安全描述符应用到管道中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="8abc1-139">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="8abc1-140">在实践中，最好将 **WhatIf** 参数与 `Set-Acl` 可能影响多个项的所有命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="8abc1-140">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="8abc1-141">在这种情况下，管道中的第二个命令将为 `Set-Acl -AclObject $NewAcl -WhatIf` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-141">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="8abc1-142">此命令将列出会受该命令影响的文件。</span><span class="sxs-lookup"><span data-stu-id="8abc1-142">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="8abc1-143">查看结果后，可以在不带 **WhatIf** 参数的情况下再次运行该命令。</span><span class="sxs-lookup"><span data-stu-id="8abc1-143">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="8abc1-144">示例4：禁用继承并保留继承的访问规则</span><span class="sxs-lookup"><span data-stu-id="8abc1-144">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="8abc1-145">这些命令将禁止从父文件夹进行访问继承，同时仍然保留现有的继承访问规则。</span><span class="sxs-lookup"><span data-stu-id="8abc1-145">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="8abc1-146">第一个命令使用 `Get-Acl` cmdlet 来获取 Dog.txt 文件的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-146">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="8abc1-147">接下来，创建变量以将继承的访问规则转换为显式访问规则。</span><span class="sxs-lookup"><span data-stu-id="8abc1-147">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="8abc1-148">若要通过继承保护与此关联的访问规则，请将 `$isProtected` 变量设置为 `$true` 。若要允许继承，请将设置 `$isProtected` 为 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-148">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="8abc1-149">有关详细信息，请参阅 [设置访问规则保护](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)。</span><span class="sxs-lookup"><span data-stu-id="8abc1-149">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="8abc1-150">`$preserveInheritance`设置为 `$true` 以保留继承的访问规则的变量; 如果为 false，则删除继承的访问规则。</span><span class="sxs-lookup"><span data-stu-id="8abc1-150">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="8abc1-151">然后，使用 **SetAccessRuleProtection ( # B1** 方法更新访问规则保护。</span><span class="sxs-lookup"><span data-stu-id="8abc1-151">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="8abc1-152">最后一个命令使用将 `Set-Acl` 的安全描述符应用到 Dog.txt。</span><span class="sxs-lookup"><span data-stu-id="8abc1-152">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="8abc1-153">命令完成后，从 "宠物" 文件夹继承的 Dog.txt 的 Acl 将直接应用到 Dog.txt，而添加到宠物的新访问策略不会更改对 Dog.txt 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8abc1-153">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="8abc1-154">示例5：授予管理员对文件的完全控制权限</span><span class="sxs-lookup"><span data-stu-id="8abc1-154">Example 5: Grant Administrators Full Control of the file</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="8abc1-155">此命令将授予 **BUILTIN\Administrators** 组对 Dog.txt 文件的完全控制权限。</span><span class="sxs-lookup"><span data-stu-id="8abc1-155">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="8abc1-156">第一个命令使用 `Get-Acl` cmdlet 来获取 Dog.txt 文件的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-156">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="8abc1-157">创建后一种变量，为 **BUILTIN\Administrators** 组授予对 Dog.txt 文件的完全控制权。</span><span class="sxs-lookup"><span data-stu-id="8abc1-157">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="8abc1-158">`$identity`设置为[用户帐户](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)名称的变量。</span><span class="sxs-lookup"><span data-stu-id="8abc1-158">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span> <span data-ttu-id="8abc1-159">`$fileSystemRights`将变量设置为 FullControl，可以是指定与访问规则关联的操作的类型的[FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights)值之一。</span><span class="sxs-lookup"><span data-stu-id="8abc1-159">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="8abc1-160">`$type`设置为 "允许" 的变量指定是允许还是拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="8abc1-160">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="8abc1-161">`$fileSystemAccessRuleArgumentList`变量是在生成新的 **FileSystemAccessRule** 对象时传递的参数列表。</span><span class="sxs-lookup"><span data-stu-id="8abc1-161">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="8abc1-162">然后，创建一个新的 **FileSystemAccessRule** 对象，并将 **FileSystemAccessRule** 对象传递到 **SetAccessRule ( # B1** 方法，添加新的访问规则。</span><span class="sxs-lookup"><span data-stu-id="8abc1-162">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="8abc1-163">最后一个命令使用将 `Set-Acl` 的安全描述符应用到 Dog.txt。</span><span class="sxs-lookup"><span data-stu-id="8abc1-163">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="8abc1-164">命令完成后， **BUILTIN\Administrators** 组将对 Dog.txt 具有完全控制。</span><span class="sxs-lookup"><span data-stu-id="8abc1-164">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="8abc1-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8abc1-165">PARAMETERS</span></span>

### <span data-ttu-id="8abc1-166">-AclObject</span><span class="sxs-lookup"><span data-stu-id="8abc1-166">-AclObject</span></span>

<span data-ttu-id="8abc1-167">指定具有所需属性值的 ACL。</span><span class="sxs-lookup"><span data-stu-id="8abc1-167">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="8abc1-168">`Set-Acl` 更改 **Path** 或 **InputObject** 参数指定的项的 ACL，使其与指定安全对象中的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="8abc1-168">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="8abc1-169">可以将命令的输出保存 `Get-Acl` 在变量中，然后使用 **AclObject** 参数传递变量，或者键入 `Get-Acl` 命令。</span><span class="sxs-lookup"><span data-stu-id="8abc1-169">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-170">-CentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8abc1-170">-CentralAccessPolicy</span></span>

<span data-ttu-id="8abc1-171">建立或更改项的中心访问策略。</span><span class="sxs-lookup"><span data-stu-id="8abc1-171">Establishes or changes the central access policy of the item.</span></span>
<span data-ttu-id="8abc1-172">在计算机上输入中心访问策略的 CAP ID 或友好名称。</span><span class="sxs-lookup"><span data-stu-id="8abc1-172">Enter the CAP ID or friendly name of a central access policy on the computer.</span></span>

<span data-ttu-id="8abc1-173">从 Windows Server 2012 开始，管理员可以使用 Active Directory 和组策略为用户和组设置中心访问策略。</span><span class="sxs-lookup"><span data-stu-id="8abc1-173">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span>
<span data-ttu-id="8abc1-174">有关详细信息，请参阅 [动态访问控制：方案概述](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview)。</span><span class="sxs-lookup"><span data-stu-id="8abc1-174">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="8abc1-175">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="8abc1-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-176">-ClearCentralAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8abc1-176">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="8abc1-177">从指定项中删除中心访问策略。</span><span class="sxs-lookup"><span data-stu-id="8abc1-177">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="8abc1-178">从 Windows Server 2012 开始，管理员可以使用 Active Directory 和组策略为用户和组设置中心访问策略。</span><span class="sxs-lookup"><span data-stu-id="8abc1-178">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="8abc1-179">有关详细信息，请参阅 [动态访问控制：方案概述](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview)。</span><span class="sxs-lookup"><span data-stu-id="8abc1-179">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="8abc1-180">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="8abc1-180">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-181">-Exclude</span><span class="sxs-lookup"><span data-stu-id="8abc1-181">-Exclude</span></span>

<span data-ttu-id="8abc1-182">忽略指定项。</span><span class="sxs-lookup"><span data-stu-id="8abc1-182">Omits the specified items.</span></span> <span data-ttu-id="8abc1-183">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="8abc1-183">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8abc1-184">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="8abc1-184">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="8abc1-185">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-185">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8abc1-186">-Filter</span><span class="sxs-lookup"><span data-stu-id="8abc1-186">-Filter</span></span>

<span data-ttu-id="8abc1-187">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="8abc1-187">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="8abc1-188">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="8abc1-188">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8abc1-189">筛选器的语法（包括通配符的使用）取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="8abc1-189">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="8abc1-190">筛选器比其他参数更有效，因为提供程序是在检索对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="8abc1-190">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8abc1-191">-Include</span><span class="sxs-lookup"><span data-stu-id="8abc1-191">-Include</span></span>

<span data-ttu-id="8abc1-192">只更改指定项。</span><span class="sxs-lookup"><span data-stu-id="8abc1-192">Changes only the specified items.</span></span> <span data-ttu-id="8abc1-193">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="8abc1-193">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="8abc1-194">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="8abc1-194">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="8abc1-195">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-195">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8abc1-196">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8abc1-196">-InputObject</span></span>

<span data-ttu-id="8abc1-197">更改指定对象的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-197">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="8abc1-198">请输入包含对象的变量或可获取该对象的命令。</span><span class="sxs-lookup"><span data-stu-id="8abc1-198">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="8abc1-199">不能通过管道将对象更改为 `Set-Acl` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-199">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="8abc1-200">而应该在命令中显式使用 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="8abc1-200">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="8abc1-201">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="8abc1-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-202">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8abc1-202">-LiteralPath</span></span>

<span data-ttu-id="8abc1-203">更改指定项的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-203">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="8abc1-204">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="8abc1-204">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="8abc1-205">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-205">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8abc1-206">如果路径包含转义符，请将其括在单引号中 (`'`) 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-206">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="8abc1-207">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="8abc1-207">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="8abc1-208">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="8abc1-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-209">-Passthru</span><span class="sxs-lookup"><span data-stu-id="8abc1-209">-Passthru</span></span>

<span data-ttu-id="8abc1-210">返回表示已更改的安全描述符的对象。</span><span class="sxs-lookup"><span data-stu-id="8abc1-210">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="8abc1-211">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="8abc1-211">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-212">-Path</span><span class="sxs-lookup"><span data-stu-id="8abc1-212">-Path</span></span>

<span data-ttu-id="8abc1-213">更改指定项的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-213">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="8abc1-214">输入项的路径，如文件或注册表项的路径。</span><span class="sxs-lookup"><span data-stu-id="8abc1-214">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="8abc1-215">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-215">Wildcards are permitted.</span></span>

<span data-ttu-id="8abc1-216">如果将安全对象传递到 `Set-Acl` (通过使用 **AclObject** 或 **SecurityDescriptor** 参数，或者通过将安全对象从 Get-Acl 传递到 `Set-Acl`) ，并且省略了 **path** 参数 (名称和值) ，则 `Set-Acl` 使用安全对象中包含的路径。</span><span class="sxs-lookup"><span data-stu-id="8abc1-216">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8abc1-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8abc1-217">-Confirm</span></span>

<span data-ttu-id="8abc1-218">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="8abc1-218">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-219">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="8abc1-219">-UseTransaction</span></span>

<span data-ttu-id="8abc1-220">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="8abc1-220">Includes the command in the active transaction.</span></span>
<span data-ttu-id="8abc1-221">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="8abc1-221">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="8abc1-222">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="8abc1-222">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8abc1-223">-WhatIf</span></span>

<span data-ttu-id="8abc1-224">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8abc1-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8abc1-225">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="8abc1-225">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8abc1-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8abc1-226">CommonParameters</span></span>

<span data-ttu-id="8abc1-227">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8abc1-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8abc1-228">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8abc1-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8abc1-229">输入</span><span class="sxs-lookup"><span data-stu-id="8abc1-229">INPUTS</span></span>

### <span data-ttu-id="8abc1-230">System.Security.AccessControl.ObjectSecurity、System.Security.AccessControl.CommonSecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="8abc1-230">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="8abc1-231">你可以通过管道将 ACL 对象或安全描述符发送到 `Set-Acl` 。</span><span class="sxs-lookup"><span data-stu-id="8abc1-231">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="8abc1-232">输出</span><span class="sxs-lookup"><span data-stu-id="8abc1-232">OUTPUTS</span></span>

### <span data-ttu-id="8abc1-233">System.Security.AccessControl.FileSecurity</span><span class="sxs-lookup"><span data-stu-id="8abc1-233">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="8abc1-234">默认情况下，不 `Set-Acl` 会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="8abc1-234">By default, `Set-Acl` does not generate any output.</span></span> <span data-ttu-id="8abc1-235">但是，如果使用 **Passthru** 参数，则它会生成一个安全对象。</span><span class="sxs-lookup"><span data-stu-id="8abc1-235">However, if you use the **Passthru** parameter, it generates a security object.</span></span> <span data-ttu-id="8abc1-236">安全对象的类型取决于项的类型。</span><span class="sxs-lookup"><span data-stu-id="8abc1-236">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="8abc1-237">注释</span><span class="sxs-lookup"><span data-stu-id="8abc1-237">NOTES</span></span>

<span data-ttu-id="8abc1-238">`Set-Acl`PowerShell 文件系统和注册表提供程序支持 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8abc1-238">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="8abc1-239">因此，可以使用它来更改文件、目录和注册表项的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8abc1-239">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="8abc1-240">相关链接</span><span class="sxs-lookup"><span data-stu-id="8abc1-240">RELATED LINKS</span></span>

[<span data-ttu-id="8abc1-241">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="8abc1-241">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="8abc1-242">FileSystemAccessRule</span><span class="sxs-lookup"><span data-stu-id="8abc1-242">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="8abc1-243">ObjectSecurity. SetAccessRuleProtection</span><span class="sxs-lookup"><span data-stu-id="8abc1-243">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="8abc1-244">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="8abc1-244">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
