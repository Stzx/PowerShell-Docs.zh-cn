---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: eccee5ad302395116430006ed4dc0395946696b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197836"
---
# <span data-ttu-id="3242b-103">Update-List</span><span class="sxs-lookup"><span data-stu-id="3242b-103">Update-List</span></span>

## <span data-ttu-id="3242b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3242b-104">SYNOPSIS</span></span>
<span data-ttu-id="3242b-105">在包含对象集合的属性值中添加和删除项。</span><span class="sxs-lookup"><span data-stu-id="3242b-105">Adds items to and removes items from a property value that contains a collection of objects.</span></span>

## <span data-ttu-id="3242b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3242b-106">SYNTAX</span></span>

### <span data-ttu-id="3242b-107">AddRemoveSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="3242b-107">AddRemoveSet (Default)</span></span>

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="3242b-108">ReplaceSet</span><span class="sxs-lookup"><span data-stu-id="3242b-108">ReplaceSet</span></span>

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## <span data-ttu-id="3242b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3242b-109">DESCRIPTION</span></span>

<span data-ttu-id="3242b-110">`Update-List`Cmdlet 可在对象的属性值中添加、移除或替换项，并返回已更新的对象。</span><span class="sxs-lookup"><span data-stu-id="3242b-110">The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object.</span></span> <span data-ttu-id="3242b-111">此 cmdlet 旨在用于包含对象集合的属性。</span><span class="sxs-lookup"><span data-stu-id="3242b-111">This cmdlet is designed for properties that contain collections of objects.</span></span>

<span data-ttu-id="3242b-112">" **添加** " 和 " **删除** " 参数在集合中添加和移除单个项。</span><span class="sxs-lookup"><span data-stu-id="3242b-112">The **Add** and **Remove** parameters add individual items to and remove them from the collection.</span></span>
<span data-ttu-id="3242b-113">**Replace** 参数将替换整个集合。</span><span class="sxs-lookup"><span data-stu-id="3242b-113">The **Replace** parameter replaces the entire collection.</span></span>

<span data-ttu-id="3242b-114">如果未在命令中指定属性，则将 `Update-List` 返回描述更新的对象，而不是更新对象。</span><span class="sxs-lookup"><span data-stu-id="3242b-114">If you do not specify a property in the command, `Update-List` returns an object that describes the update instead of updating the object.</span></span> <span data-ttu-id="3242b-115">你可以将更新对象提交给更改对象的 cmdlet，例如 `Set` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3242b-115">You can submit the update object to cmdlets that change objects, such as `Set` cmdlets.</span></span>

<span data-ttu-id="3242b-116">仅当正在更新的属性支持使用的 **IList** 接口时，此 cmdlet 才有效 `Update-List` 。</span><span class="sxs-lookup"><span data-stu-id="3242b-116">This cmdlet works only when the property that is being updated supports the **IList** interface that `Update-List` uses.</span></span> <span data-ttu-id="3242b-117">此外， `Set` 接受更新的任何 cmdlet 都必须支持 **IList** 接口。</span><span class="sxs-lookup"><span data-stu-id="3242b-117">Also, any `Set` cmdlets that accept an update must support the **IList** interface.</span></span>

<span data-ttu-id="3242b-118">随 PowerShell 一起安装的核心 cmdlet 不支持此接口。</span><span class="sxs-lookup"><span data-stu-id="3242b-118">The core cmdlets that are installed with PowerShell do not support this interface.</span></span> <span data-ttu-id="3242b-119">若要确定 cmdlet 是否支持 `Update-List` ，请参阅 Cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="3242b-119">To determine whether a cmdlet supports `Update-List`, see the cmdlet Help topic.</span></span>

## <span data-ttu-id="3242b-120">示例</span><span class="sxs-lookup"><span data-stu-id="3242b-120">EXAMPLES</span></span>

### <span data-ttu-id="3242b-121">示例1：将项添加到属性值</span><span class="sxs-lookup"><span data-stu-id="3242b-121">Example 1: Add items to a property value</span></span>

<span data-ttu-id="3242b-122">在此示例中，我们将创建一个类，它表示卡的卡片组，其中卡片存储为 **列表** 集合对象。</span><span class="sxs-lookup"><span data-stu-id="3242b-122">In this example we create a class that represents a deck of cards where the cards are stored as a **List** collection object.</span></span> <span data-ttu-id="3242b-123">**NewDeck ( # B1** 方法使用 `Update-List` 将一组完整的卡值添加到 **卡** 集合。</span><span class="sxs-lookup"><span data-stu-id="3242b-123">The **NewDeck()** method uses `Update-List`to add a complete deck of card values to the **cards** collection.</span></span>

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = [char]0x2663,[char]0x2666,[char]0x2665,[char]0x2660
        $_values = 'A',2,3,4,5,6,7,8,9,10,'J','Q','K'
        $_deck = foreach ($s in $_suits){ foreach ($v in $_values){ "$v$s"} }
        $this | Update-List -Property cards -Add $_deck | Out-Null
    }

    Show() {
        Write-Host
        Write-Host $this.name ": " $this.cards[0..12]
        if ($this.cards.count -gt 13) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[13..25]
        }
        if ($this.cards.count -gt 26) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[26..38]
        }
        if ($this.cards.count -gt 39) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[39..51]
        }
    }

    Shuffle() { $this.cards = Get-Random -InputObject $this.cards -Count 52 }

    Sort() { $this.cards.Sort() }
}
```

> [!NOTE]
> <span data-ttu-id="3242b-124">`Update-List`Cmdlet 可将更新后的对象输出到管道。</span><span class="sxs-lookup"><span data-stu-id="3242b-124">The `Update-List` cmdlet outputs the updated object to the pipeline.</span></span> <span data-ttu-id="3242b-125">我们通过管道将输出传递给 `Out-Null` ，以禁止显示不需要的显示。</span><span class="sxs-lookup"><span data-stu-id="3242b-125">We pipe the output to `Out-Null` to suppress the unwanted display.</span></span>

### <span data-ttu-id="3242b-126">示例2：在集合属性中添加和移除项</span><span class="sxs-lookup"><span data-stu-id="3242b-126">Example 2: Add and remove items of a collection property</span></span>

<span data-ttu-id="3242b-127">继续使用示例1中的代码，我们将创建 **卡片** 类的实例，以表示一组卡片和两个播放器容纳的卡。</span><span class="sxs-lookup"><span data-stu-id="3242b-127">Continuing with the code in Example 1, we will create instances of the **Cards** class to represent a deck of cards and the cards held by two players.</span></span> <span data-ttu-id="3242b-128">我们使用 `Update-List` cmdlet 向玩家的手中添加卡，并从纸牌中删除牌。</span><span class="sxs-lookup"><span data-stu-id="3242b-128">We use the `Update-List` cmdlet to add cards to the players' hands and to remove cards from the deck.</span></span>

```powershell
$player1 = [Cards]::new('Player 1')
$player2 = [Cards]::new('Player 2')

$deck = [Cards]::new('Deck')
$deck.NewDeck()
$deck.Shuffle()
$deck.Show()

# Deal two hands
$player1 | Update-List -Property cards -Add $deck.cards[0,2,4,6,8] | Out-Null
$player2 | Update-List -Property cards -Add $deck.cards[1,3,5,7,9] | Out-Null
$deck | Update-List -Property cards -Remove $player1.cards | Out-Null
$deck | Update-List -Property cards -Remove $player2.cards | Out-Null

$player1.Show()
$player2.Show()
$deck.Show()
```

```Output
Deck :  4♦ 7♥ J♦ 5♣ A♣ 8♦ J♣ Q♥ 6♦ 3♦ 9♦ 6♣ 2♣
        K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥ Q♠
        3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠ 2♥
        6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣ 8♥

Player 1 :  4♦ J♦ A♣ J♣ 6♦

Player 2 :  7♥ 5♣ 8♦ Q♥ 3♦

Deck :  9♦ 6♣ 2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣
        Q♣ A♥ Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠
        4♣ 2♠ 2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣
        A♦ K♣ 8♥
```

<span data-ttu-id="3242b-129">输出显示将卡发到玩家之前的卡片组的状态。</span><span class="sxs-lookup"><span data-stu-id="3242b-129">The output shows the state of the deck before the cards were dealt to the players.</span></span> <span data-ttu-id="3242b-130">您可以看到，每个玩家都接收了卡片组中的五行。</span><span class="sxs-lookup"><span data-stu-id="3242b-130">You can see that each player received five cards from the deck.</span></span> <span data-ttu-id="3242b-131">最终输出显示了将卡处理到玩家后的卡片组状态。</span><span class="sxs-lookup"><span data-stu-id="3242b-131">The final output shows the state of the deck after dealing the cards to the players.</span></span> <span data-ttu-id="3242b-132">`Update-List` 用于从卡片组中选择卡并将其添加到播放机的集合中。</span><span class="sxs-lookup"><span data-stu-id="3242b-132">`Update-List` was used to select the cards from the deck and add them to the players' collection.</span></span> <span data-ttu-id="3242b-133">然后，使用将从中删除玩家的卡片 `Update-List` 。</span><span class="sxs-lookup"><span data-stu-id="3242b-133">Then the players' cards were removed from the deck using `Update-List`.</span></span>

### <span data-ttu-id="3242b-134">示例3：在单个命令中添加和删除项</span><span class="sxs-lookup"><span data-stu-id="3242b-134">Example 3: Add and remove items in a single command</span></span>

<span data-ttu-id="3242b-135">`Update-List` 允许你在单个命令中使用 **Add** 和 **Remove** 参数。</span><span class="sxs-lookup"><span data-stu-id="3242b-135">`Update-List` allows you to use the **Add** and **Remove** parameters in a single command.</span></span> <span data-ttu-id="3242b-136">在此示例中，Player 1 要丢弃 `4♦` 并 `6♦` 获得两个新卡。</span><span class="sxs-lookup"><span data-stu-id="3242b-136">In this example, Player 1 wants to discard the `4♦` and `6♦` and get two new cards.</span></span>

```powershell
# Player 1 wants two new cards - remove 2 cards & add 2 cards
$player1 | Update-List -Property cards -Remove $player1.cards[0,4] -Add $deck.cards[0..1] | Out-Null
$player1.Show()

# remove dealt cards from deck
$deck | Update-List -Property cards -Remove $deck.cards[0..1] | Out-Null
$deck.Show()
```

```Output
Player 1 :  J♦ A♣ J♣ 9♦ 6♣

Deck :  2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥
        Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠
        2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣
        8♥
```

## <span data-ttu-id="3242b-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3242b-137">PARAMETERS</span></span>

### <span data-ttu-id="3242b-138">-Add</span><span class="sxs-lookup"><span data-stu-id="3242b-138">-Add</span></span>

<span data-ttu-id="3242b-139">指定要添加到集合中的属性值。</span><span class="sxs-lookup"><span data-stu-id="3242b-139">Specifies the property values to be added to the collection.</span></span> <span data-ttu-id="3242b-140">按照值应该在集合中出现的顺序输入值。</span><span class="sxs-lookup"><span data-stu-id="3242b-140">Enter the values in the order that they should appear in the collection.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3242b-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3242b-141">-InputObject</span></span>

<span data-ttu-id="3242b-142">指定要更新的对象。</span><span class="sxs-lookup"><span data-stu-id="3242b-142">Specifies the objects to be updated.</span></span> <span data-ttu-id="3242b-143">还可以通过管道将对象更新为 `Update-List` 。</span><span class="sxs-lookup"><span data-stu-id="3242b-143">You can also pipe the object to be updated to `Update-List`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3242b-144">-Property</span><span class="sxs-lookup"><span data-stu-id="3242b-144">-Property</span></span>

<span data-ttu-id="3242b-145">指定包含正在更新的集合的属性。</span><span class="sxs-lookup"><span data-stu-id="3242b-145">Specifies the property that contains the collection that is being updated.</span></span> <span data-ttu-id="3242b-146">如果省略此参数，则 `Update-List` 返回一个表示更改的对象，而不是更改该对象。</span><span class="sxs-lookup"><span data-stu-id="3242b-146">If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3242b-147">-Remove</span><span class="sxs-lookup"><span data-stu-id="3242b-147">-Remove</span></span>

<span data-ttu-id="3242b-148">指定要从集合中删除的属性值。</span><span class="sxs-lookup"><span data-stu-id="3242b-148">Specifies the property values to be removed from the collection.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3242b-149">-Replace</span><span class="sxs-lookup"><span data-stu-id="3242b-149">-Replace</span></span>

<span data-ttu-id="3242b-150">指定新集合。</span><span class="sxs-lookup"><span data-stu-id="3242b-150">Specifies a new collection.</span></span> <span data-ttu-id="3242b-151">此参数会将原始集合中的所有项替换为由此参数指定的项。</span><span class="sxs-lookup"><span data-stu-id="3242b-151">This parameter replaces all items in the original collection with the items specified by this parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ReplaceSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3242b-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3242b-152">CommonParameters</span></span>

<span data-ttu-id="3242b-153">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3242b-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3242b-154">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3242b-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3242b-155">输入</span><span class="sxs-lookup"><span data-stu-id="3242b-155">INPUTS</span></span>

### <span data-ttu-id="3242b-156">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="3242b-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3242b-157">你可以通过管道将要更新的对象传递给 `Update-List` 。</span><span class="sxs-lookup"><span data-stu-id="3242b-157">You can pipe the objects to be updated to `Update-List`.</span></span>

## <span data-ttu-id="3242b-158">输出</span><span class="sxs-lookup"><span data-stu-id="3242b-158">OUTPUTS</span></span>

### <span data-ttu-id="3242b-159">对象或 System.Management.Automation.PSListModifier</span><span class="sxs-lookup"><span data-stu-id="3242b-159">Objects or System.Management.Automation.PSListModifier</span></span>

<span data-ttu-id="3242b-160">`Update-List` 返回更新的对象，或返回一个表示更新操作的对象。</span><span class="sxs-lookup"><span data-stu-id="3242b-160">`Update-List` returns the updated object, or it returns an object that represents the update action.</span></span>

## <span data-ttu-id="3242b-161">注释</span><span class="sxs-lookup"><span data-stu-id="3242b-161">NOTES</span></span>

## <span data-ttu-id="3242b-162">相关链接</span><span class="sxs-lookup"><span data-stu-id="3242b-162">RELATED LINKS</span></span>

[<span data-ttu-id="3242b-163">Format-List</span><span class="sxs-lookup"><span data-stu-id="3242b-163">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="3242b-164">Select-Object</span><span class="sxs-lookup"><span data-stu-id="3242b-164">Select-Object</span></span>](Select-Object.md)
