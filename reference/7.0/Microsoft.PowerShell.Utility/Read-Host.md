---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: aacc89001373ecc8ef75e630f965a8d807bd4ac3
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "93198910"
---
# <span data-ttu-id="1d35f-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="1d35f-103">Read-Host</span></span>

## <span data-ttu-id="1d35f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1d35f-104">SYNOPSIS</span></span>
<span data-ttu-id="1d35f-105">从控制台读取一行输入。</span><span class="sxs-lookup"><span data-stu-id="1d35f-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="1d35f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d35f-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="1d35f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d35f-107">DESCRIPTION</span></span>

<span data-ttu-id="1d35f-108">`Read-Host`Cmdlet 从控制台读取一行输入。</span><span class="sxs-lookup"><span data-stu-id="1d35f-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="1d35f-109">可使用它来提示用户输入数据。</span><span class="sxs-lookup"><span data-stu-id="1d35f-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="1d35f-110">因为可以将输入保存为安全字符串，所以可以使用此 cmdlet 来提示用户输入安全数据（如密码）以及共享的数据。</span><span class="sxs-lookup"><span data-stu-id="1d35f-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="1d35f-111">示例</span><span class="sxs-lookup"><span data-stu-id="1d35f-111">EXAMPLES</span></span>

### <span data-ttu-id="1d35f-112">示例1：将控制台输入保存到变量</span><span class="sxs-lookup"><span data-stu-id="1d35f-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="1d35f-113">此示例显示字符串 "请输入你的年龄：" 作为提示。</span><span class="sxs-lookup"><span data-stu-id="1d35f-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="1d35f-114">输入值并按下 Enter 键时，该值将存储在 `$Age` 变量中。</span><span class="sxs-lookup"><span data-stu-id="1d35f-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="1d35f-115">示例2：将控制台输入另存为安全字符串</span><span class="sxs-lookup"><span data-stu-id="1d35f-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="1d35f-116">此示例显示字符串 "Enter a Password：" 作为提示。</span><span class="sxs-lookup"><span data-stu-id="1d35f-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="1d35f-117">输入值时，将在 `*` 控制台上显示星号 () 以替代输入。</span><span class="sxs-lookup"><span data-stu-id="1d35f-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="1d35f-118">按下 Enter 键时，该值将作为 **SecureString** 对象存储在 `$pwd_secure_string` 变量中。</span><span class="sxs-lookup"><span data-stu-id="1d35f-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="1d35f-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d35f-119">PARAMETERS</span></span>

### <span data-ttu-id="1d35f-120">-AsSecureString</span><span class="sxs-lookup"><span data-stu-id="1d35f-120">-AsSecureString</span></span>

<span data-ttu-id="1d35f-121">指示该 cmdlet 显示星号 (`*`) 用户键入作为输入的字符。</span><span class="sxs-lookup"><span data-stu-id="1d35f-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="1d35f-122">使用此参数时，该 cmdlet 的输出 `Read-Host` 是 **SecureString** 对象， ( **SecureString** ) 。</span><span class="sxs-lookup"><span data-stu-id="1d35f-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="1d35f-123">-Prompt</span><span class="sxs-lookup"><span data-stu-id="1d35f-123">-Prompt</span></span>

<span data-ttu-id="1d35f-124">指定提示的文本。</span><span class="sxs-lookup"><span data-stu-id="1d35f-124">Specifies the text of the prompt.</span></span>
<span data-ttu-id="1d35f-125">键入一个字符串。</span><span class="sxs-lookup"><span data-stu-id="1d35f-125">Type a string.</span></span>
<span data-ttu-id="1d35f-126">如果该字符串包含空格，请将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="1d35f-126">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="1d35f-127">PowerShell 将向你输入的文本追加一个冒号 (`:`) 。</span><span class="sxs-lookup"><span data-stu-id="1d35f-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d35f-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1d35f-128">CommonParameters</span></span>

<span data-ttu-id="1d35f-129">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="1d35f-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d35f-130">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="1d35f-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d35f-131">输入</span><span class="sxs-lookup"><span data-stu-id="1d35f-131">INPUTS</span></span>

### <span data-ttu-id="1d35f-132">无</span><span class="sxs-lookup"><span data-stu-id="1d35f-132">None</span></span>

<span data-ttu-id="1d35f-133">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1d35f-133">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1d35f-134">输出</span><span class="sxs-lookup"><span data-stu-id="1d35f-134">OUTPUTS</span></span>

### <span data-ttu-id="1d35f-135">System.String 或 System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="1d35f-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="1d35f-136">如果使用 **AsSecureString** 参数，则 `Read-Host` 将返回 **SecureString** 。</span><span class="sxs-lookup"><span data-stu-id="1d35f-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString** .</span></span> <span data-ttu-id="1d35f-137">否则，它将返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="1d35f-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="1d35f-138">注释</span><span class="sxs-lookup"><span data-stu-id="1d35f-138">NOTES</span></span>

## <span data-ttu-id="1d35f-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="1d35f-139">RELATED LINKS</span></span>

[<span data-ttu-id="1d35f-140">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="1d35f-140">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="1d35f-141">Get-Host</span><span class="sxs-lookup"><span data-stu-id="1d35f-141">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="1d35f-142">Write-Host</span><span class="sxs-lookup"><span data-stu-id="1d35f-142">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="1d35f-143">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="1d35f-143">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
