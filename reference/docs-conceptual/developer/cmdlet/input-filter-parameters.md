---
ms.date: 09/13/2016
ms.topic: reference
title: 输入筛选参数
description: 输入筛选参数
ms.openlocfilehash: 419ffea2afb4aa534a3e19ecdfce6d6af1da46a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648531"
---
# <a name="input-filter-parameters"></a>输入筛选参数

Cmdlet 可以定义 `Filter` 、 `Include` 和参数， `Exclude` 以筛选该 cmdlet 影响的输入对象集。

通常，输入对象集由 `InputObject` 、 `Path` 或 `Name` 参数指定。 例如，一个 cmdlet 可以有一个 `Path` 参数，该参数使用通配符来接受多个路径，并且每个路径指向一个输入对象。 一起使用时， `Filter` 、 `Include` 和 `Exclude` 参数会进一步限定 cmdlet 在每次调用时所使用的路径。

## <a name="include-and-exclude-parameters"></a>包括和排除参数

`Include`和 `Exclude` 参数标识传递到 cmdlet 的输入对象集中包含或排除的对象。 如果筛选器可以用标准通配符语言表示，请使用这些参数。  (有关通配符的详细信息，请参阅 [在 Cmdlet 参数中支持通配符](./supporting-wildcard-characters-in-cmdlet-parameters.md)。 ) `Include` 参数包括名称与包含筛选器匹配的所有对象。 `Exclude`参数会排除名称与筛选器匹配的所有对象。

## <a name="filter-parameter"></a>筛选器参数

`Filter`参数指定了不以标准通配符语言表示的筛选器。 例如，Active Directory 服务接口 (ADSI) 或 SQL 筛选器都可以通过其参数传递给 cmdlet `Filter` 。 在 Windows PowerShell 提供的 cmdlet 中，这些筛选器由使用 cmdlet 访问数据存储的 Windows PowerShell 提供程序指定。 每个提供程序通常定义自己的筛选器。

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a>如果未指定任何输入对象集，则进行筛选

如果未指定任何输入对象集，这通常意味着要针对所有对象进行筛选。 有关详细信息，请参阅[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
