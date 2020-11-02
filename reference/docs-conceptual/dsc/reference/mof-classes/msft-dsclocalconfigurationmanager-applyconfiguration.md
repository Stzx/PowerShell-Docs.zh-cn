---
ms.date: 07/14/2020
ms.topic: reference
title: ApplyConfiguration 方法
description: ApplyConfiguration 方法
ms.openlocfilehash: aa99221b33d39c3ecc70156a11eaee10b540e2dc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664279"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="67796-103">ApplyConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="67796-103">ApplyConfiguration method</span></span>

<span data-ttu-id="67796-104">使用配置代理应用处于挂起状态的配置。</span><span class="sxs-lookup"><span data-stu-id="67796-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="67796-105">如果没有挂起的配置，此方法将重新应用当前配置。</span><span class="sxs-lookup"><span data-stu-id="67796-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="67796-106">语法</span><span class="sxs-lookup"><span data-stu-id="67796-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="67796-107">参数</span><span class="sxs-lookup"><span data-stu-id="67796-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="67796-108">force</span><span class="sxs-lookup"><span data-stu-id="67796-108">force</span></span>

<span data-ttu-id="67796-109">如果为 **true** ，将会重新应用当前配置，即使存在挂起的配置。</span><span class="sxs-lookup"><span data-stu-id="67796-109">If this is **true** , the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="67796-110">返回值</span><span class="sxs-lookup"><span data-stu-id="67796-110">Return value</span></span>

<span data-ttu-id="67796-111">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="67796-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="67796-112">注解</span><span class="sxs-lookup"><span data-stu-id="67796-112">Remarks</span></span>

<span data-ttu-id="67796-113">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="67796-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="67796-114">要求</span><span class="sxs-lookup"><span data-stu-id="67796-114">Requirements</span></span>

<span data-ttu-id="67796-115">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="67796-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="67796-116">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="67796-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="67796-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67796-117">See also</span></span>

[<span data-ttu-id="67796-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="67796-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
