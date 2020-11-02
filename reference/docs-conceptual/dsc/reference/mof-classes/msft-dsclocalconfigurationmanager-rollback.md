---
ms.date: 07/17/2020
ms.topic: reference
title: RollBack 方法
description: RollBack 方法
ms.openlocfilehash: 82ca54ed23a3a892b785f603be3b423def5ee636
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650621"
---
# <a name="rollback-method"></a><span data-ttu-id="898c9-103">RollBack 方法</span><span class="sxs-lookup"><span data-stu-id="898c9-103">RollBack method</span></span>

<span data-ttu-id="898c9-104">将配置回滚到以前的版本。</span><span class="sxs-lookup"><span data-stu-id="898c9-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="898c9-105">语法</span><span class="sxs-lookup"><span data-stu-id="898c9-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="898c9-106">参数</span><span class="sxs-lookup"><span data-stu-id="898c9-106">Parameters</span></span>

<span data-ttu-id="898c9-107">configurationNumber  \[in\]：指定请求获取的配置。</span><span class="sxs-lookup"><span data-stu-id="898c9-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="898c9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="898c9-108">Return value</span></span>

<span data-ttu-id="898c9-109">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="898c9-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="898c9-110">备注</span><span class="sxs-lookup"><span data-stu-id="898c9-110">Remarks</span></span>

<span data-ttu-id="898c9-111">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="898c9-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="898c9-112">要求</span><span class="sxs-lookup"><span data-stu-id="898c9-112">Requirements</span></span>

<span data-ttu-id="898c9-113">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="898c9-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="898c9-114">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="898c9-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="898c9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="898c9-115">See also</span></span>

[<span data-ttu-id="898c9-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="898c9-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
