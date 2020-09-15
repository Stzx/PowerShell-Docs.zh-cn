---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: RemoveConfiguration 方法
ms.openlocfilehash: ef15c873d8dfaf28e5cdeb611b72a70921c099be
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464343"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="4c8ab-103">RemoveConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="4c8ab-103">RemoveConfiguration method</span></span>

<span data-ttu-id="4c8ab-104">删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c8ab-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c8ab-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="4c8ab-106">参数</span><span class="sxs-lookup"><span data-stu-id="4c8ab-106">Parameters</span></span>

<span data-ttu-id="4c8ab-107">Stage  \[in\]：指定要删除的配置文档。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-107">**Stage** \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="4c8ab-108">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="4c8ab-108">The following values are valid:</span></span>

|<span data-ttu-id="4c8ab-109">值</span><span class="sxs-lookup"><span data-stu-id="4c8ab-109">Value</span></span> |<span data-ttu-id="4c8ab-110">说明</span><span class="sxs-lookup"><span data-stu-id="4c8ab-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="4c8ab-111">**1**</span><span class="sxs-lookup"><span data-stu-id="4c8ab-111">**1**</span></span> | <span data-ttu-id="4c8ab-112">**当前**配置文档 (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="4c8ab-113">**2**</span><span class="sxs-lookup"><span data-stu-id="4c8ab-113">**2**</span></span> | <span data-ttu-id="4c8ab-114">**挂起的**配置文档 (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="4c8ab-115">**4**</span><span class="sxs-lookup"><span data-stu-id="4c8ab-115">**4**</span></span> | <span data-ttu-id="4c8ab-116">**以前的**配置文档 (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="4c8ab-117">Force  \[in\]：若为 true  ，则强制删除配置。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4c8ab-118">返回值</span><span class="sxs-lookup"><span data-stu-id="4c8ab-118">Return value</span></span>

<span data-ttu-id="4c8ab-119">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c8ab-120">备注</span><span class="sxs-lookup"><span data-stu-id="4c8ab-120">Remarks</span></span>

<span data-ttu-id="4c8ab-121">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="4c8ab-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4c8ab-122">要求</span><span class="sxs-lookup"><span data-stu-id="4c8ab-122">Requirements</span></span>

<span data-ttu-id="4c8ab-123">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="4c8ab-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="4c8ab-124">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c8ab-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="4c8ab-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c8ab-125">See also</span></span>

[<span data-ttu-id="4c8ab-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="4c8ab-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
