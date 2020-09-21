---
ms.date: 07/14/2020
keywords: dsc,powershell,配置,安装程序
title: ApplyConfiguration 方法
ms.openlocfilehash: bec74ccd6f75448484adfd26bf8a4af4e224eb3f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463833"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="c4fd8-103">ApplyConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="c4fd8-103">ApplyConfiguration method</span></span>

<span data-ttu-id="c4fd8-104">使用配置代理应用处于挂起状态的配置。</span><span class="sxs-lookup"><span data-stu-id="c4fd8-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="c4fd8-105">如果没有挂起的配置，此方法将重新应用当前配置。</span><span class="sxs-lookup"><span data-stu-id="c4fd8-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4fd8-106">语法</span><span class="sxs-lookup"><span data-stu-id="c4fd8-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="c4fd8-107">参数</span><span class="sxs-lookup"><span data-stu-id="c4fd8-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="c4fd8-108">force</span><span class="sxs-lookup"><span data-stu-id="c4fd8-108">force</span></span>

<span data-ttu-id="c4fd8-109">如果为 **true**，将会重新应用当前配置，即使存在挂起的配置。</span><span class="sxs-lookup"><span data-stu-id="c4fd8-109">If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="c4fd8-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c4fd8-110">Return value</span></span>

<span data-ttu-id="c4fd8-111">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="c4fd8-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4fd8-112">注解</span><span class="sxs-lookup"><span data-stu-id="c4fd8-112">Remarks</span></span>

<span data-ttu-id="c4fd8-113">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="c4fd8-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4fd8-114">要求</span><span class="sxs-lookup"><span data-stu-id="c4fd8-114">Requirements</span></span>

<span data-ttu-id="c4fd8-115">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c4fd8-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="c4fd8-116">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4fd8-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="c4fd8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4fd8-117">See also</span></span>

[<span data-ttu-id="c4fd8-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c4fd8-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
