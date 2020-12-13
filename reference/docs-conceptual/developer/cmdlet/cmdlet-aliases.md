---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 别名
description: Cmdlet 别名
ms.openlocfilehash: 734553a9911aef256df563afa6abcdb23d7a62e6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660790"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="1a4b5-103">Cmdlet 别名</span><span class="sxs-lookup"><span data-stu-id="1a4b5-103">Cmdlet Aliases</span></span>

<span data-ttu-id="1a4b5-104">可以使用 cmdlet 别名来改善 cmdlet 用户体验。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-104">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="1a4b5-105">你可以将别名添加到常用的 cmdlet，以减少键入并更轻松地完成任务。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-105">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="1a4b5-106">可以在 cmdlet 中包含内置别名，或者用户可以定义自己的自定义别名。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-106">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="1a4b5-107">例如， [get-help](/powershell/module/microsoft.powershell.core/get-command) cmdlet 具有内置 `gcm` 别名。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-107">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="1a4b5-108">你还可以使用别名来添加其他语言的命令名称，以便用户无需了解新的命令。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-108">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="1a4b5-109">别名指南</span><span class="sxs-lookup"><span data-stu-id="1a4b5-109">Alias Guidelines</span></span>

<span data-ttu-id="1a4b5-110">为 cmdlet 创建内置别名时，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="1a4b5-110">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="1a4b5-111">在分配别名之前，请启动 Windows PowerShell，然后运行 [获取别名](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet 以查看已使用的别名。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-111">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="1a4b5-112">包含一个别名前缀，该前缀引用 cmdlet 名称的谓词和引用 cmdlet 名称名词的别名后缀。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-112">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="1a4b5-113">例如，cmdlet 的别名 `Import-Module` 为 "ipmo"。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-113">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="1a4b5-114">有关所有谓词及其别名的列表，请参阅 [Cmdlet 谓词](./approved-verbs-for-windows-powershell-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-114">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="1a4b5-115">对于具有相同谓词的 cmdlet，请包含相同的别名前缀。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-115">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="1a4b5-116">例如，其名称中具有 "Get" 谓词的所有 Windows PowerShell cmdlet 的别名均使用 "g" 前缀。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-116">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="1a4b5-117">对于具有相同名词的 cmdlet，请包含相同的别名后缀。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-117">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="1a4b5-118">例如，名称中包含 "Session" 名词的所有 Windows PowerShell cmdlet 的别名均使用 "sn" 后缀。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-118">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="1a4b5-119">对于等效于其他语言中的命令的 cmdlet，请使用命令的名称。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-119">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="1a4b5-120">通常，请尽可能缩短别名。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-120">In general, make aliases as short as possible.</span></span> <span data-ttu-id="1a4b5-121">请确保该别名至少具有一个用于该谓词的非重复字符和名词的一个不同字符。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-121">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="1a4b5-122">根据需要添加更多字符，使别名唯一。</span><span class="sxs-lookup"><span data-stu-id="1a4b5-122">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a4b5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a4b5-123">See Also</span></span>

[<span data-ttu-id="1a4b5-124">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1a4b5-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
