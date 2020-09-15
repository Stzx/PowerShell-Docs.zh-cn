---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: StopConfiguration 方法
ms.openlocfilehash: 76e50c98b09dca86983320918c6899082580672a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463697"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="09236-103">StopConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="09236-103">StopConfiguration method</span></span>

<span data-ttu-id="09236-104">停止正在进行的配置更改。</span><span class="sxs-lookup"><span data-stu-id="09236-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="09236-105">语法</span><span class="sxs-lookup"><span data-stu-id="09236-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="09236-106">参数</span><span class="sxs-lookup"><span data-stu-id="09236-106">Parameters</span></span>

<span data-ttu-id="09236-107">force  \[in\]：若为 true  ，则强制停止配置。</span><span class="sxs-lookup"><span data-stu-id="09236-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="09236-108">返回值</span><span class="sxs-lookup"><span data-stu-id="09236-108">Return value</span></span>

<span data-ttu-id="09236-109">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="09236-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="09236-110">备注</span><span class="sxs-lookup"><span data-stu-id="09236-110">Remarks</span></span>

<span data-ttu-id="09236-111">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="09236-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="09236-112">要求</span><span class="sxs-lookup"><span data-stu-id="09236-112">Requirements</span></span>

<span data-ttu-id="09236-113">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="09236-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="09236-114">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="09236-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="09236-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09236-115">See also</span></span>

[<span data-ttu-id="09236-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="09236-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
