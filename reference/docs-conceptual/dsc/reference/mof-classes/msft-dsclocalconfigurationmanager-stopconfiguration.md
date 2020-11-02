---
ms.date: 07/17/2020
ms.topic: reference
title: StopConfiguration 方法
description: StopConfiguration 方法
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644621"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="cd7f8-103">StopConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="cd7f8-103">StopConfiguration method</span></span>

<span data-ttu-id="cd7f8-104">停止正在进行的配置更改。</span><span class="sxs-lookup"><span data-stu-id="cd7f8-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="cd7f8-105">语法</span><span class="sxs-lookup"><span data-stu-id="cd7f8-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="cd7f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="cd7f8-106">Parameters</span></span>

<span data-ttu-id="cd7f8-107">force  \[in\]：若为 true  ，则强制停止配置。</span><span class="sxs-lookup"><span data-stu-id="cd7f8-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="cd7f8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="cd7f8-108">Return value</span></span>

<span data-ttu-id="cd7f8-109">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="cd7f8-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd7f8-110">备注</span><span class="sxs-lookup"><span data-stu-id="cd7f8-110">Remarks</span></span>

<span data-ttu-id="cd7f8-111">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="cd7f8-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd7f8-112">要求</span><span class="sxs-lookup"><span data-stu-id="cd7f8-112">Requirements</span></span>

<span data-ttu-id="cd7f8-113">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="cd7f8-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="cd7f8-114">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="cd7f8-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="cd7f8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd7f8-115">See also</span></span>

[<span data-ttu-id="cd7f8-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="cd7f8-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
