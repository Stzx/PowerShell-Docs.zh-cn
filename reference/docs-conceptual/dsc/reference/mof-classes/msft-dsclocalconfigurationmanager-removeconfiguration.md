---
ms.date: 07/17/2020
ms.topic: reference
title: RemoveConfiguration 方法
description: RemoveConfiguration 方法
ms.openlocfilehash: d5988ac014c457407c56a097c9a376427376eb3f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650730"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="5c52e-103">RemoveConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="5c52e-103">RemoveConfiguration method</span></span>

<span data-ttu-id="5c52e-104">删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c52e-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c52e-105">语法</span><span class="sxs-lookup"><span data-stu-id="5c52e-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="5c52e-106">参数</span><span class="sxs-lookup"><span data-stu-id="5c52e-106">Parameters</span></span>

<span data-ttu-id="5c52e-107">Stage  \[in\]：指定要删除的配置文档。</span><span class="sxs-lookup"><span data-stu-id="5c52e-107">**Stage** \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="5c52e-108">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="5c52e-108">The following values are valid:</span></span>

|<span data-ttu-id="5c52e-109">值</span><span class="sxs-lookup"><span data-stu-id="5c52e-109">Value</span></span> |<span data-ttu-id="5c52e-110">说明</span><span class="sxs-lookup"><span data-stu-id="5c52e-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="5c52e-111">**1**</span><span class="sxs-lookup"><span data-stu-id="5c52e-111">**1**</span></span> | <span data-ttu-id="5c52e-112">**当前** 配置文档 (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="5c52e-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="5c52e-113">**2**</span><span class="sxs-lookup"><span data-stu-id="5c52e-113">**2**</span></span> | <span data-ttu-id="5c52e-114">**挂起的** 配置文档 (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="5c52e-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="5c52e-115">**4**</span><span class="sxs-lookup"><span data-stu-id="5c52e-115">**4**</span></span> | <span data-ttu-id="5c52e-116">**以前的** 配置文档 (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="5c52e-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="5c52e-117">Force  \[in\]：若为 true  ，则强制删除配置。</span><span class="sxs-lookup"><span data-stu-id="5c52e-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="5c52e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5c52e-118">Return value</span></span>

<span data-ttu-id="5c52e-119">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="5c52e-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c52e-120">备注</span><span class="sxs-lookup"><span data-stu-id="5c52e-120">Remarks</span></span>

<span data-ttu-id="5c52e-121">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="5c52e-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c52e-122">要求</span><span class="sxs-lookup"><span data-stu-id="5c52e-122">Requirements</span></span>

<span data-ttu-id="5c52e-123">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5c52e-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="5c52e-124">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5c52e-124">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="5c52e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c52e-125">See also</span></span>

[<span data-ttu-id="5c52e-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="5c52e-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
