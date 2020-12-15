---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 从列表框中选择项
description: 本文介绍如何使用 Windows PowerShell 中的 .NET Framework 窗体构建功能创建列表框控件。
ms.openlocfilehash: d6f881f0b92f294da105ae7df5e25e8c20ce5094
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391232"
---
# <a name="selecting-items-from-a-list-box"></a><span data-ttu-id="6eacf-104">从列表框中选择项</span><span class="sxs-lookup"><span data-stu-id="6eacf-104">Selecting Items from a List Box</span></span>

<span data-ttu-id="6eacf-105">使用 Windows PowerShell 3.0 和更高版本创建一个对话框，从而允许用户从列表框控件中选择项。</span><span class="sxs-lookup"><span data-stu-id="6eacf-105">Use Windows PowerShell 3.0 and later releases to create a dialog box that lets users select items from a list box control.</span></span>

## <a name="create-a-list-box-control-and-select-items-from-it"></a><span data-ttu-id="6eacf-106">创建一个列表框控件，并从中选择项</span><span class="sxs-lookup"><span data-stu-id="6eacf-106">Create a list box control, and select items from it</span></span>

<span data-ttu-id="6eacf-107">复制以下内容并将其粘贴到 Windows PowerShell ISE 中，然后将其另存为 Windows PowerShell 脚本 (.ps1)。</span><span class="sxs-lookup"><span data-stu-id="6eacf-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Select a Computer'
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
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80

[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')

$form.Controls.Add($listBox)

$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

<span data-ttu-id="6eacf-108">该脚本首先加载两个 .NET Framework 类：**System.Drawing** 和 **System.Windows.Forms**。</span><span class="sxs-lookup"><span data-stu-id="6eacf-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="6eacf-109">然后，启动 .NET Framework 类 **System.Windows.Forms.Form** 的新实例；它提供一个可以开始添加控件的空白窗体或窗口。</span><span class="sxs-lookup"><span data-stu-id="6eacf-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

<span data-ttu-id="6eacf-110">在创建 Form 类的实例后，为此类的三个属性赋值。</span><span class="sxs-lookup"><span data-stu-id="6eacf-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="6eacf-111">**文本。**</span><span class="sxs-lookup"><span data-stu-id="6eacf-111">**Text.**</span></span> <span data-ttu-id="6eacf-112">这将成为该窗口的标题。</span><span class="sxs-lookup"><span data-stu-id="6eacf-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="6eacf-113">**大小。**</span><span class="sxs-lookup"><span data-stu-id="6eacf-113">**Size.**</span></span> <span data-ttu-id="6eacf-114">这是窗体的大小（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="6eacf-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="6eacf-115">上述脚本创建的窗体大小为宽 300 像素、高 200 像素。</span><span class="sxs-lookup"><span data-stu-id="6eacf-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="6eacf-116">**StartingPosition。**</span><span class="sxs-lookup"><span data-stu-id="6eacf-116">**StartingPosition.**</span></span> <span data-ttu-id="6eacf-117">在上述脚本中，此可选属性将设置为 **CenterScreen**。</span><span class="sxs-lookup"><span data-stu-id="6eacf-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="6eacf-118">如果未添加此属性，Windows 将在窗体打开时选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="6eacf-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="6eacf-119">通过将 StartingPosition 设置为 CenterScreen，可使窗体在每次加载时都自动显示在屏幕中间 。</span><span class="sxs-lookup"><span data-stu-id="6eacf-119">By setting the **StartingPosition** to **CenterScreen**, you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="6eacf-120">接下来，为窗体创建“确定”按钮。 </span><span class="sxs-lookup"><span data-stu-id="6eacf-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="6eacf-121">指定“确定”按钮的大小和行为。 </span><span class="sxs-lookup"><span data-stu-id="6eacf-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="6eacf-122">在此示例中，按钮位置为距窗体上边缘 120 像素，距左边缘 75 像素。</span><span class="sxs-lookup"><span data-stu-id="6eacf-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="6eacf-123">按钮高度为 23 像素，按钮长度为 75 像素。</span><span class="sxs-lookup"><span data-stu-id="6eacf-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="6eacf-124">此脚本使用预定义的 Windows 窗体类型确定按钮行为。</span><span class="sxs-lookup"><span data-stu-id="6eacf-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

<span data-ttu-id="6eacf-125">采用相同方式创建“取消”按钮。 </span><span class="sxs-lookup"><span data-stu-id="6eacf-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="6eacf-126">“取消”按钮距窗口上边缘 120 像素，但距左边缘 150 像素。 </span><span class="sxs-lookup"><span data-stu-id="6eacf-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="6eacf-127">接下来，在窗口上提供标签文本，用于描述你希望用户提供的信息。</span><span class="sxs-lookup"><span data-stu-id="6eacf-127">Next, provide label text on your window that describes the information you want users to provide.</span></span> <span data-ttu-id="6eacf-128">在本例中，你希望用户选择一台计算机。</span><span class="sxs-lookup"><span data-stu-id="6eacf-128">In this case, you want users to select a computer.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

<span data-ttu-id="6eacf-129">添加控件（在本例中为列表框），从而让用户提供你在标签文本中描述的信息。</span><span class="sxs-lookup"><span data-stu-id="6eacf-129">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="6eacf-130">除了列表框，你还可以应用许多其他控件；有关更多控件，请参阅 [System.Windows.Forms 命名空间](/dotnet/api/system.windows.forms)。</span><span class="sxs-lookup"><span data-stu-id="6eacf-130">There are many other controls you can apply besides list boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms).</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

<span data-ttu-id="6eacf-131">在下一部分中，你可以指定希望列表框向用户显示的值。</span><span class="sxs-lookup"><span data-stu-id="6eacf-131">In the next section, you specify the values you want the list box to display to users.</span></span>

> [!NOTE]
> <span data-ttu-id="6eacf-132">此脚本创建的列表框只允许进行单选。</span><span class="sxs-lookup"><span data-stu-id="6eacf-132">The list box created by this script allows only one selection.</span></span> <span data-ttu-id="6eacf-133">若要创建允许进行多选的列表框控件，请指定 SelectionMode 属性的值，类似于以下内容：`$listBox.SelectionMode = 'MultiExtended'`。</span><span class="sxs-lookup"><span data-stu-id="6eacf-133">To create a list box control that allows multiple selections, specify a value for the **SelectionMode** property, similarly to the following: `$listBox.SelectionMode = 'MultiExtended'`.</span></span> <span data-ttu-id="6eacf-134">有关详细信息，请参阅[多选列表框](Multiple-selection-List-Boxes.md)。</span><span class="sxs-lookup"><span data-stu-id="6eacf-134">For more information, see [Multiple-selection List Boxes](Multiple-selection-List-Boxes.md).</span></span>

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

<span data-ttu-id="6eacf-135">将列表框控件添加到窗体中，并指示 Windows 在打开该窗体时，在其他窗口和对话框之上打开它。</span><span class="sxs-lookup"><span data-stu-id="6eacf-135">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="6eacf-136">添加以下代码行以在 Windows 中显示该窗体。</span><span class="sxs-lookup"><span data-stu-id="6eacf-136">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="6eacf-137">最后，**If** 块内的代码指示在用户从列表框中选择某个选项，然后单击“确定”按钮或按“Enter”键后，Windows 应如何处理该窗体。</span><span class="sxs-lookup"><span data-stu-id="6eacf-137">Finally, the code inside the **If** block instructs Windows what to do with the form after users select an option from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="6eacf-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6eacf-138">See Also</span></span>

- [<span data-ttu-id="6eacf-139">GitHub：Dave Wyatt 的 WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="6eacf-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="6eacf-140">[本周 Windows PowerShell 提示：从列表框中选择项](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6eacf-140">[Windows PowerShell Tip of the Week: Selecting Items from a List Box](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span></span>
