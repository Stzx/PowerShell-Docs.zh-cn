---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 创建自定义输入框
description: 本文介绍如何使用 Windows PowerShell 中的 .NET Framework 窗体构建功能创建自定义输入框。
ms.openlocfilehash: b7786706d2461c329da429c1bd4971d7dc874d6d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390076"
---
# <a name="creating-a-custom-input-box"></a><span data-ttu-id="c8c51-104">创建自定义输入框</span><span class="sxs-lookup"><span data-stu-id="c8c51-104">Creating a Custom Input Box</span></span>

<span data-ttu-id="c8c51-105">通过使用 Windows PowerShell 3.0 及更高版本中的 Microsoft .NET Framework 窗体构建功能为图形自定义输入框编写脚本。</span><span class="sxs-lookup"><span data-stu-id="c8c51-105">Script a graphical custom input box by using Microsoft .NET Framework form-building features in Windows PowerShell 3.0 and later releases.</span></span>

## <a name="create-a-custom-graphical-input-box"></a><span data-ttu-id="c8c51-106">创建自定义图形输入框</span><span class="sxs-lookup"><span data-stu-id="c8c51-106">Create a custom, graphical input box</span></span>

<span data-ttu-id="c8c51-107">复制以下内容并将其粘贴到 Windows PowerShell ISE 中，然后将其另存为 Windows PowerShell 脚本 (.ps1)。</span><span class="sxs-lookup"><span data-stu-id="c8c51-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)

$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)

$form.Topmost = $true

$form.Add_Shown({$textBox.Select()})
$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

<span data-ttu-id="c8c51-108">该脚本首先加载两个 .NET Framework 类：**System.Drawing** 和 **System.Windows.Forms**。</span><span class="sxs-lookup"><span data-stu-id="c8c51-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="c8c51-109">然后，启动 .NET Framework 类 **System.Windows.Forms.Form** 的新实例；它提供一个可以开始添加控件的空白窗体或窗口。</span><span class="sxs-lookup"><span data-stu-id="c8c51-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object System.Windows.Forms.Form
```

<span data-ttu-id="c8c51-110">在创建 Form 类的实例后，为此类的三个属性赋值。</span><span class="sxs-lookup"><span data-stu-id="c8c51-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="c8c51-111">**文本。**</span><span class="sxs-lookup"><span data-stu-id="c8c51-111">**Text.**</span></span> <span data-ttu-id="c8c51-112">这将成为该窗口的标题。</span><span class="sxs-lookup"><span data-stu-id="c8c51-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="c8c51-113">**大小。**</span><span class="sxs-lookup"><span data-stu-id="c8c51-113">**Size.**</span></span> <span data-ttu-id="c8c51-114">这是窗体的大小（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="c8c51-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="c8c51-115">上述脚本创建的窗体大小为宽 300 像素、高 200 像素。</span><span class="sxs-lookup"><span data-stu-id="c8c51-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="c8c51-116">**StartingPosition。**</span><span class="sxs-lookup"><span data-stu-id="c8c51-116">**StartingPosition.**</span></span> <span data-ttu-id="c8c51-117">在上述脚本中，此可选属性将设置为 **CenterScreen**。</span><span class="sxs-lookup"><span data-stu-id="c8c51-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="c8c51-118">如果未添加此属性，Windows 将在窗体打开时选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="c8c51-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="c8c51-119">通过将 StartingPosition 设置为 CenterScreen，可使窗体在每次加载时都自动显示在屏幕中间 。</span><span class="sxs-lookup"><span data-stu-id="c8c51-119">By setting the **StartingPosition** to **CenterScreen**, you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="c8c51-120">接下来，为窗体创建“确定”按钮。 </span><span class="sxs-lookup"><span data-stu-id="c8c51-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="c8c51-121">指定“确定”按钮的大小和行为。 </span><span class="sxs-lookup"><span data-stu-id="c8c51-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="c8c51-122">在此示例中，按钮位置为距窗体上边缘 120 像素，距左边缘 75 像素。</span><span class="sxs-lookup"><span data-stu-id="c8c51-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="c8c51-123">按钮高度为 23 像素，按钮长度为 75 像素。</span><span class="sxs-lookup"><span data-stu-id="c8c51-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="c8c51-124">此脚本使用预定义的 Windows 窗体类型确定按钮行为。</span><span class="sxs-lookup"><span data-stu-id="c8c51-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="c8c51-125">采用相同方式创建“取消”按钮。 </span><span class="sxs-lookup"><span data-stu-id="c8c51-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="c8c51-126">“取消”按钮距窗口上边缘 120 像素，但距左边缘 150 像素。 </span><span class="sxs-lookup"><span data-stu-id="c8c51-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="c8c51-127">接下来，在窗口上提供标签文本，用于描述你希望用户提供的信息。</span><span class="sxs-lookup"><span data-stu-id="c8c51-127">Next, provide label text on your window that describes the information you want users to provide.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)
```

<span data-ttu-id="c8c51-128">添加控件（在本例中为文本框），从而让用户提供你在标签文本中描述的信息。</span><span class="sxs-lookup"><span data-stu-id="c8c51-128">Add the control (in this case, a text box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="c8c51-129">除了文本框，你还可以应用许多其他控件；有关更多控件，请参阅 [System.Windows.Forms 命名空间](/dotnet/api/system.windows.forms)。</span><span class="sxs-lookup"><span data-stu-id="c8c51-129">There are many other controls you can apply besides text boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms).</span></span>

```powershell
$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)
```

<span data-ttu-id="c8c51-130">将 Topmost 属性设置为 $True，以强制此窗口在其他已打开的窗口和对话框之上打开。</span><span class="sxs-lookup"><span data-stu-id="c8c51-130">Set the **Topmost** property to **$true** to force the window to open atop other open windows and dialog boxes.</span></span>

```powershell
$form.Topmost = $true
```

<span data-ttu-id="c8c51-131">接下来，添加此代码行以激活窗体，并将焦点设置到你创建的文本框。</span><span class="sxs-lookup"><span data-stu-id="c8c51-131">Next, add this line of code to activate the form, and set the focus to the text box that you created.</span></span>

```powershell
$form.Add_Shown({$textBox.Select()})
```

<span data-ttu-id="c8c51-132">添加以下代码行以在 Windows 中显示该窗体。</span><span class="sxs-lookup"><span data-stu-id="c8c51-132">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="c8c51-133">最后，**If** 块内的代码指示在用户在文本框中提供文本，然后单击“确定”按钮或按“Enter”键后，Windows 应如何处理该窗体。</span><span class="sxs-lookup"><span data-stu-id="c8c51-133">Finally, the code inside the **If** block instructs Windows what to do with the form after users provide text in the text box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="c8c51-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c51-134">See Also</span></span>

- <span data-ttu-id="c8c51-135">[GitHub：Dave Wyatt 的 WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c8c51-135">[GitHub: Dave Wyatt's WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))</span></span>
- [<span data-ttu-id="c8c51-136">Windows PowerShell 每周提示：创建自定义输入框</span><span class="sxs-lookup"><span data-stu-id="c8c51-136">Windows PowerShell Tip of the Week:  Creating a Custom Input Box</span></span>](https://technet.microsoft.com/library/ff730941.aspx)
