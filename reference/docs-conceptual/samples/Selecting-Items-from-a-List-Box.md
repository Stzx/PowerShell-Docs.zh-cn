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
# <a name="selecting-items-from-a-list-box"></a>从列表框中选择项

使用 Windows PowerShell 3.0 和更高版本创建一个对话框，从而允许用户从列表框控件中选择项。

## <a name="create-a-list-box-control-and-select-items-from-it"></a>创建一个列表框控件，并从中选择项

复制以下内容并将其粘贴到 Windows PowerShell ISE 中，然后将其另存为 Windows PowerShell 脚本 (.ps1)。

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

该脚本首先加载两个 .NET Framework 类：**System.Drawing** 和 **System.Windows.Forms**。 然后，启动 .NET Framework 类 **System.Windows.Forms.Form** 的新实例；它提供一个可以开始添加控件的空白窗体或窗口。

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

在创建 Form 类的实例后，为此类的三个属性赋值。

- **文本。** 这将成为该窗口的标题。

- **大小。** 这是窗体的大小（以像素为单位）。 上述脚本创建的窗体大小为宽 300 像素、高 200 像素。

- **StartingPosition。** 在上述脚本中，此可选属性将设置为 **CenterScreen**。
  如果未添加此属性，Windows 将在窗体打开时选择一个位置。 通过将 StartingPosition 设置为 CenterScreen，可使窗体在每次加载时都自动显示在屏幕中间 。

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

接下来，为窗体创建“确定”按钮。  指定“确定”按钮的大小和行为。  在此示例中，按钮位置为距窗体上边缘 120 像素，距左边缘 75 像素。 按钮高度为 23 像素，按钮长度为 75 像素。 此脚本使用预定义的 Windows 窗体类型确定按钮行为。

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

采用相同方式创建“取消”按钮。  “取消”按钮距窗口上边缘 120 像素，但距左边缘 150 像素。 

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

接下来，在窗口上提供标签文本，用于描述你希望用户提供的信息。 在本例中，你希望用户选择一台计算机。

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

添加控件（在本例中为列表框），从而让用户提供你在标签文本中描述的信息。 除了列表框，你还可以应用许多其他控件；有关更多控件，请参阅 [System.Windows.Forms 命名空间](/dotnet/api/system.windows.forms)。

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

在下一部分中，你可以指定希望列表框向用户显示的值。

> [!NOTE]
> 此脚本创建的列表框只允许进行单选。 若要创建允许进行多选的列表框控件，请指定 SelectionMode 属性的值，类似于以下内容：`$listBox.SelectionMode = 'MultiExtended'`。 有关详细信息，请参阅[多选列表框](Multiple-selection-List-Boxes.md)。

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

将列表框控件添加到窗体中，并指示 Windows 在打开该窗体时，在其他窗口和对话框之上打开它。

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

添加以下代码行以在 Windows 中显示该窗体。

```powershell
$result = $form.ShowDialog()
```

最后，**If** 块内的代码指示在用户从列表框中选择某个选项，然后单击“确定”按钮或按“Enter”键后，Windows 应如何处理该窗体。

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a>另请参阅

- [GitHub：Dave Wyatt 的 WinFormsExampleUpdates](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [本周 Windows PowerShell 提示：从列表框中选择项](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))
