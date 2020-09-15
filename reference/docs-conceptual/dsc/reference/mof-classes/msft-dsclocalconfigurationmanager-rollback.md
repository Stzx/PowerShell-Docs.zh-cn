---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: RollBack 方法
ms.openlocfilehash: 301b8926d2ebf1ebe524f52a67928d34e26d860e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464326"
---
# <a name="rollback-method"></a><span data-ttu-id="7c0df-103">RollBack 方法</span><span class="sxs-lookup"><span data-stu-id="7c0df-103">RollBack method</span></span>

<span data-ttu-id="7c0df-104">将配置回滚到以前的版本。</span><span class="sxs-lookup"><span data-stu-id="7c0df-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c0df-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c0df-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="7c0df-106">参数</span><span class="sxs-lookup"><span data-stu-id="7c0df-106">Parameters</span></span>

<span data-ttu-id="7c0df-107">configurationNumber  \[in\]：指定请求获取的配置。</span><span class="sxs-lookup"><span data-stu-id="7c0df-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="7c0df-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7c0df-108">Return value</span></span>

<span data-ttu-id="7c0df-109">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="7c0df-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c0df-110">备注</span><span class="sxs-lookup"><span data-stu-id="7c0df-110">Remarks</span></span>

<span data-ttu-id="7c0df-111">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="7c0df-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c0df-112">要求</span><span class="sxs-lookup"><span data-stu-id="7c0df-112">Requirements</span></span>

<span data-ttu-id="7c0df-113">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7c0df-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="7c0df-114">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c0df-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="7c0df-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c0df-115">See also</span></span>

[<span data-ttu-id="7c0df-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7c0df-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
