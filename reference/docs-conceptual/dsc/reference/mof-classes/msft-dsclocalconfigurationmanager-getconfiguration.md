---
ms.date: 07/17/2020
ms.topic: reference
title: GetConfiguration 方法
description: GetConfiguration 方法
ms.openlocfilehash: a49f810bd227142c8c3ae4de45f69450400e4e8c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650871"
---
# <a name="getconfiguration-method"></a><span data-ttu-id="1b297-103">GetConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="1b297-103">GetConfiguration method</span></span>

<span data-ttu-id="1b297-104">将配置文档发送到托管节点，并使用配置代理的 **Get** 方法以应用配置。</span><span class="sxs-lookup"><span data-stu-id="1b297-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b297-105">语法</span><span class="sxs-lookup"><span data-stu-id="1b297-105">Syntax</span></span>

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a><span data-ttu-id="1b297-106">参数</span><span class="sxs-lookup"><span data-stu-id="1b297-106">Parameters</span></span>

<span data-ttu-id="1b297-107">configurationData  \[in\]：指定要发送的配置数据。</span><span class="sxs-lookup"><span data-stu-id="1b297-107">**configurationData** \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="1b297-108">configurations  \[out\]：返回响应时，包含配置的嵌入实例。</span><span class="sxs-lookup"><span data-stu-id="1b297-108">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="1b297-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1b297-109">Return value</span></span>

<span data-ttu-id="1b297-110">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="1b297-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b297-111">备注</span><span class="sxs-lookup"><span data-stu-id="1b297-111">Remarks</span></span>

<span data-ttu-id="1b297-112">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="1b297-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b297-113">要求</span><span class="sxs-lookup"><span data-stu-id="1b297-113">Requirements</span></span>

<span data-ttu-id="1b297-114">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1b297-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1b297-115">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1b297-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1b297-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b297-116">See also</span></span>

[<span data-ttu-id="1b297-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1b297-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
