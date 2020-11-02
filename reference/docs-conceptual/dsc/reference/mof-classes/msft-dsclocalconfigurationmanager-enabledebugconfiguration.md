---
ms.date: 07/17/2020
ms.topic: reference
title: EnableDebugConfiguration 方法
description: EnableDebugConfiguration 方法
ms.openlocfilehash: 536366e6e1627a249f3bc2dc19bfd8ff3de42117
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644778"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="833db-103">EnableDebugConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="833db-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="833db-104">启用 DSC 资源调试。</span><span class="sxs-lookup"><span data-stu-id="833db-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="833db-105">语法</span><span class="sxs-lookup"><span data-stu-id="833db-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="833db-106">参数</span><span class="sxs-lookup"><span data-stu-id="833db-106">Parameters</span></span>

<span data-ttu-id="833db-107">BreakAll  \[in\]：在资源脚本中的每一行设置断点。</span><span class="sxs-lookup"><span data-stu-id="833db-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="833db-108">返回值</span><span class="sxs-lookup"><span data-stu-id="833db-108">Return value</span></span>

<span data-ttu-id="833db-109">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="833db-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="833db-110">备注</span><span class="sxs-lookup"><span data-stu-id="833db-110">Remarks</span></span>

<span data-ttu-id="833db-111">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="833db-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="833db-112">要求</span><span class="sxs-lookup"><span data-stu-id="833db-112">Requirements</span></span>

<span data-ttu-id="833db-113">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="833db-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="833db-114">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="833db-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="833db-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="833db-115">See also</span></span>

[<span data-ttu-id="833db-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="833db-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
