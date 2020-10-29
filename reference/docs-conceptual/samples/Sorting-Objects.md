---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 对对象进行排序
description: 使用 Sort-Object cmdlet 可依据一个或多个属性对一系列对象进行排序。
ms.openlocfilehash: 836207adfc566003e9714e45920d9b4e24a677e9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501008"
---
# <a name="sorting-objects"></a><span data-ttu-id="d8098-104">对对象进行排序</span><span class="sxs-lookup"><span data-stu-id="d8098-104">Sorting Objects</span></span>

<span data-ttu-id="d8098-105">可以通过使用 `Sort-Object` cmdlet 组织已显示的数据，使其更易于扫描。</span><span class="sxs-lookup"><span data-stu-id="d8098-105">We can organize displayed data to make it easier to scan by using the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="d8098-106">`Sort-Object` 依据一个或多个属性的名称进行排序，并返回按这些属性的值进行排序的数据。</span><span class="sxs-lookup"><span data-stu-id="d8098-106">`Sort-Object` takes the name of one or more properties to sort on, and returns data sorted by the values of those properties.</span></span>

## <a name="basic-sorting"></a><span data-ttu-id="d8098-107">基本排序</span><span class="sxs-lookup"><span data-stu-id="d8098-107">Basic sorting</span></span>

<span data-ttu-id="d8098-108">请考虑列出当前目录中的子目录和文件的问题。</span><span class="sxs-lookup"><span data-stu-id="d8098-108">Consider the problem of listing subdirectories and files in the current directory.</span></span>
<span data-ttu-id="d8098-109">如果想要依次按 LastWriteTime  和 Name  进行排序，可键入：</span><span class="sxs-lookup"><span data-stu-id="d8098-109">If we want to sort by **LastWriteTime** and then by **Name** , we can do it by typing:</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
11/6/2017 10:10:11 AM  .localization-config
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:15 AM  tests
6/6/2018 7:58:59 PM    CONTRIBUTING.md
6/6/2018 7:58:59 PM    README.md
...
```

<span data-ttu-id="d8098-110">也可通过指定 Descending  开关参数按相反顺序对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="d8098-110">You can also sort the objects in reverse order by specifying the **Descending** switch parameter.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property LastWriteTime, Name -Descending |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  reference
12/1/2018 10:13:50 PM  dsc
...
6/6/2018 7:58:59 PM    README.md
6/6/2018 7:58:59 PM    CONTRIBUTING.md
11/6/2017 10:10:15 AM  tests
11/6/2017 10:10:11 AM  ThirdPartyNotices
11/6/2017 10:10:11 AM  LICENSE-CODE
11/6/2017 10:10:11 AM  LICENSE
11/6/2017 10:10:11 AM  appveyor.yml
11/6/2017 10:10:11 AM  .openpublishing.build.ps1
11/6/2017 10:10:11 AM  .localization-config
```

## <a name="using-hash-tables"></a><span data-ttu-id="d8098-111">使用哈希表</span><span class="sxs-lookup"><span data-stu-id="d8098-111">Using hash tables</span></span>

<span data-ttu-id="d8098-112">可以使用数组中的哈希表按不同顺序对不同属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="d8098-112">You can sort different properties in different orders by using hash tables in an array.</span></span>
<span data-ttu-id="d8098-113">每个哈希表使用 Expression  键将属性名称指定为字符串，并使用 Ascending  或 Descending  键按 `$true` 或 `$false` 指定排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d8098-113">Each hash table uses an **Expression** key to specify the property name as string and an **Ascending** or **Descending** key to specify the sort order by `$true` or `$false`.</span></span>
<span data-ttu-id="d8098-114">Expression  键是必需的。</span><span class="sxs-lookup"><span data-stu-id="d8098-114">The **Expression** key is mandatory.</span></span>
<span data-ttu-id="d8098-115">Ascending  或 Descending  键是可选的。</span><span class="sxs-lookup"><span data-stu-id="d8098-115">The **Ascending** or **Descending** key is optional.</span></span>

<span data-ttu-id="d8098-116">下面的示例按 LastWriteTime  降序和 Name  升序对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="d8098-116">The following example sorts objects in descending **LastWriteTime** order and ascending **Name** order.</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = 'LastWriteTime'; Descending = $true }, @{ Expression = 'Name'; Ascending = $true } |
  Format-Table -Property LastWriteTime, Name
```

```output
LastWriteTime          Name
-------------          ----
12/1/2018 10:13:50 PM  dsc
12/1/2018 10:13:50 PM  reference
11/29/2018 6:56:01 PM  .openpublishing.redirection.json
11/29/2018 6:56:01 PM  gallery
11/24/2018 10:33:22 AM developer
11/20/2018 7:22:19 PM  .markdownlint.json
...
```

<span data-ttu-id="d8098-117">还可以将 scriptblock 设置为 Expression  键。</span><span class="sxs-lookup"><span data-stu-id="d8098-117">You can also set a scriptblock to the **Expression** key.</span></span>
<span data-ttu-id="d8098-118">运行 `Sort-Object` cmdlet 时，将执行 scriptblock 并使用结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="d8098-118">When running the `Sort-Object` cmdlet, the scriptblock is executed and the result is used for sorting.</span></span>

<span data-ttu-id="d8098-119">下面的示例按 CreationTime  和 LastWriteTime  之间的时间跨度以降序对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="d8098-119">The following example sorts objects in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

```powershell
Get-ChildItem |
  Sort-Object -Property @{ Expression = { $_.LastWriteTime - $_.CreationTime }; Descending = $true } |
  Format-Table -Property LastWriteTime, CreationTime
```

```output
LastWriteTime          CreationTime
-------------          ------------
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
12/1/2018 10:13:50 PM  11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:11 AM
11/7/2018 6:52:24 PM   11/6/2017 10:10:15 AM
11/3/2018 9:58:17 AM   11/6/2017 10:10:11 AM
10/26/2018 4:50:21 PM  11/6/2017 10:10:11 AM
11/17/2018 1:10:57 PM  11/29/2017 5:48:30 PM
11/12/2018 6:29:53 PM  12/7/2017 7:57:07 PM
...
```

## <a name="tips"></a><span data-ttu-id="d8098-120">提示</span><span class="sxs-lookup"><span data-stu-id="d8098-120">Tips</span></span>

<span data-ttu-id="d8098-121">可以省略 Property  参数名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d8098-121">You can omit the **Property** parameter name as following:</span></span>

```powershell
Sort-Object LastWriteTime, Name
```

<span data-ttu-id="d8098-122">此外，可以通过其内置别名 `sort` 来引用 `Sort-Object`：</span><span class="sxs-lookup"><span data-stu-id="d8098-122">Besides, you can refer to `Sort-Object` by its built-in alias, `sort`:</span></span>

```powershell
sort LastWriteTime, Name
```

<span data-ttu-id="d8098-123">用于排序的哈希表中的键可以缩写为：</span><span class="sxs-lookup"><span data-stu-id="d8098-123">The keys in the hash tables for sorting can be abbreviated as following:</span></span>

```powershell
Sort-Object @{ e = 'LastWriteTime'; d = $true }, @{ e = 'Name'; a = $true }
```

<span data-ttu-id="d8098-124">在此示例中，e  代表 Expression  ，d  代表 Descending  ，a  代表 Ascending  。</span><span class="sxs-lookup"><span data-stu-id="d8098-124">In this example, the **e** stands for **Expression** , the **d** stands for **Descending** , and the **a** stands for **Ascending** .</span></span>

<span data-ttu-id="d8098-125">为了提高可读性，可以将哈希表置于一个单独的变量中：</span><span class="sxs-lookup"><span data-stu-id="d8098-125">To improve readability, you can place the hash tables into a separate variable:</span></span>

```powershell
$order = @(
  @{ Expression = 'LastWriteTime'; Descending = $true }
  @{ Expression = 'Name'; Ascending = $true }
)

Get-ChildItem |
  Sort-Object $order |
  Format-Table LastWriteTime, Name
```
