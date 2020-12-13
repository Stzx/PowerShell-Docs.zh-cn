---
ms.date: 09/13/2016
ms.topic: reference
title: 加载和导出格式设置数据
description: 加载和导出格式设置数据
ms.openlocfilehash: 38857526801051bf6d31d300d5be1a3fd2c80391
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666512"
---
# <a name="loading-and-exporting-formatting-data"></a><span data-ttu-id="1a2f6-103">加载和导出格式设置数据</span><span class="sxs-lookup"><span data-stu-id="1a2f6-103">Loading and Exporting Formatting Data</span></span>

<span data-ttu-id="1a2f6-104">创建格式化文件后，需要通过将文件加载到当前会话中来更新会话的格式数据。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-104">Once you have created your formatting file, you need to update the format data of the session by loading your files into the current session.</span></span> <span data-ttu-id="1a2f6-105"> (在打开当前会话时注册的管理单元加载 Windows PowerShell 提供的格式设置文件。 ) 更新当前会话的格式数据后，Windows PowerShell 将使用该数据显示与已加载的格式设置文件中定义的视图关联的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-105">(The formatting files provided by Windows PowerShell are loaded by snap-ins that are registered when the current session is opened.) Once the format data of the current session is updated, Windows PowerShell uses that data to display the .NET objects associated with the views defined in the loaded formatting files.</span></span> <span data-ttu-id="1a2f6-106">可以加载到当前会话中的格式化文件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-106">There is no limit to the number of formatting files that you can load into the current session.</span></span> <span data-ttu-id="1a2f6-107">除了更新格式设置数据以外，还可以将当前会话中的格式数据导出回格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-107">In addition to updating the formatting data, you can export the format data in the current session back to a formatting file.</span></span>

## <a name="loading-format-data"></a><span data-ttu-id="1a2f6-108">正在加载格式数据</span><span class="sxs-lookup"><span data-stu-id="1a2f6-108">Loading format data</span></span>

<span data-ttu-id="1a2f6-109">可以使用以下方法将格式化文件加载到当前会话中：</span><span class="sxs-lookup"><span data-stu-id="1a2f6-109">Formatting files can be loaded into the current session using the following methods:</span></span>

- <span data-ttu-id="1a2f6-110">你可以从命令行将格式设置文件导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-110">You can import the formatting file into the current session from the command line.</span></span> <span data-ttu-id="1a2f6-111">按照以下过程中所述，使用 [update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-111">Use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet as described in the following procedure.</span></span>

- <span data-ttu-id="1a2f6-112">你可以创建一个引用你的格式化文件的模块清单。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-112">You can create a module manifest that references your formatting file.</span></span> <span data-ttu-id="1a2f6-113">模块允许您打包格式化文件以进行分发。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-113">Modules allow you to package you formatting files for distribution.</span></span> <span data-ttu-id="1a2f6-114">使用 [new-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet 创建清单，并使用 [import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet 将模块加载到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-114">Use the [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet to create the manifest, and the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet to load the module into the current session.</span></span> <span data-ttu-id="1a2f6-115">有关模块的详细信息，请参阅 [编写 Windows PowerShell 模块](../module/writing-a-windows-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-115">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="1a2f6-116">你可以创建一个引用你的格式化文件的管理单元。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-116">You can create a snap-in that references your formatting file.</span></span> <span data-ttu-id="1a2f6-117">使用 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) 可引用您的格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-117">Use the [System.Management.Automation.PSSnapIn.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) to reference your formatting files.</span></span> <span data-ttu-id="1a2f6-118">强烈建议使用模块打包 cmdlet 以及任何关联的格式和类型文件以进行分发。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-118">It is strongly encouraged to use modules to package cmdlets, and any associated formatting and types files for distribution.</span></span> <span data-ttu-id="1a2f6-119">有关模块的详细信息，请参阅 [编写 Windows PowerShell 模块](../module/writing-a-windows-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-119">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="1a2f6-120">如果以编程方式调用命令，则可以将格式设置文件条目添加到运行命令的运行空间的初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-120">If you are invoking commands programmatically, you can add a formatting file entry to the initial session state of the runspace where the commands are run.</span></span> <span data-ttu-id="1a2f6-121">有关用于添加格式化文件的 .NET 类型的详细信息，请参阅 [Sessionstateformatentry？Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) 类。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-121">For more information about .NET type used to add the formatting file, see the [System.Management.Automation.Runspaces.Sessionstateformatentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) class.</span></span>

<span data-ttu-id="1a2f6-122">加载格式设置文件时，会将其添加到 Windows PowerShell 用来确定在命令行显示对象时使用的视图的内部列表。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-122">When a formatting file is loaded, it is added to an internal list that Windows PowerShell uses to determine which view to use when displaying objects at the command line.</span></span> <span data-ttu-id="1a2f6-123">您可以在列表开头添加格式文件，也可以将其追加到列表的末尾。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-123">You can prepend your formatting file to the beginning of the list, or you can append it to the end of the list.</span></span> <span data-ttu-id="1a2f6-124">如果正在加载定义了定义了现有视图的对象的视图的格式设置文件（例如，当你想要更改由 Windows PowerShell core cmdlet 返回的对象的显示方式），则了解将格式设置文件添加到此列表中的位置非常重要。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-124">Knowing where your formatting file is added to this list is important if you are loading formatting file that defines a view for an object that has an existing view defined, such as when you want to change how an object that is returned by a Windows PowerShell core cmdlet is displayed.</span></span> <span data-ttu-id="1a2f6-125">如果正在加载的格式设置文件定义对象的唯一视图，则可以使用前面所述的任何方法。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-125">If you are loading a formatting file that defines the only view for an object, you can use any of the methods described previously.</span></span>  <span data-ttu-id="1a2f6-126">如果要加载的格式设置文件定义了对象的其他视图，则必须使用 [update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet，并将文件预置到列表的开头。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-126">If you are loading a formatting file that defines another view for an object, you must use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet and prepend your file to the beginning of the list.</span></span>

## <a name="storing-your-formatting-file"></a><span data-ttu-id="1a2f6-127">存储格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1a2f6-127">Storing Your Formatting File</span></span>

<span data-ttu-id="1a2f6-128">不要求在磁盘上存储格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-128">There is no requirement for where your formatting files are stored on disk.</span></span> <span data-ttu-id="1a2f6-129">但是，强烈建议将它们存储在以下文件夹中： `user\documents\windowspowershell\`</span><span class="sxs-lookup"><span data-stu-id="1a2f6-129">However, it is strongly suggested that you store them in the following folder: `user\documents\windowspowershell\`</span></span>

#### <a name="loading-a-format-file-using-import-formatdata"></a><span data-ttu-id="1a2f6-130">使用 Import-FormatData 加载格式化文件</span><span class="sxs-lookup"><span data-stu-id="1a2f6-130">Loading a format file using Import-FormatData</span></span>

1. <span data-ttu-id="1a2f6-131">将格式化文件存储到磁盘。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-131">Store your formatting file to disk.</span></span>

2. <span data-ttu-id="1a2f6-132">使用以下命令之一运行 [update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-132">Run the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet using one of the following commands.</span></span>

   <span data-ttu-id="1a2f6-133">若要在列表的前面添加格式文件，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-133">To add your formatting file to the front of the list use this command.</span></span> <span data-ttu-id="1a2f6-134">如果要更改对象的显示方式，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-134">Use this command if you are changing how an object is displayed.</span></span>

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   <span data-ttu-id="1a2f6-135">若要在列表的末尾添加格式文件，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-135">To add your formatting file to the end of the list use this command.</span></span>

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   <span data-ttu-id="1a2f6-136">使用 [update-formatdata](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet 添加文件后，当会话处于打开状态时，不能从列表中删除该文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-136">Once you have added a file using the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet, you cannot remove the file from the list while the session is open.</span></span> <span data-ttu-id="1a2f6-137">要从列表中删除格式化文件，必须关闭会话。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-137">You must close the session to remove the formatting file from the list.</span></span>

## <a name="exporting-format-data"></a><span data-ttu-id="1a2f6-138">导出格式数据</span><span class="sxs-lookup"><span data-stu-id="1a2f6-138">Exporting format data</span></span>

<span data-ttu-id="1a2f6-139">在此处插入节正文。</span><span class="sxs-lookup"><span data-stu-id="1a2f6-139">Insert section body here.</span></span>
