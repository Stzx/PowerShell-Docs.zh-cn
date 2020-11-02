---
ms.date: 07/17/2020
ms.topic: reference
title: GetConfigurationResultOutput 方法
description: GetConfigurationResultOutput 方法
ms.openlocfilehash: 7c885109b3078189b7ac653733a5fb24db66312e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644710"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="2f65f-103">GetConfigurationResultOutput 方法</span><span class="sxs-lookup"><span data-stu-id="2f65f-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="2f65f-104">获取与特定作业相关的配置代理输出。</span><span class="sxs-lookup"><span data-stu-id="2f65f-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f65f-105">语法</span><span class="sxs-lookup"><span data-stu-id="2f65f-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="2f65f-106">参数</span><span class="sxs-lookup"><span data-stu-id="2f65f-106">Parameters</span></span>

<span data-ttu-id="2f65f-107">jobId  \[in\]：要为其获取输出数据的作业的 ID。</span><span class="sxs-lookup"><span data-stu-id="2f65f-107">**jobId** \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="2f65f-108">resumeOutputBookmark  \[in\]：指定输出应接着上一书签。</span><span class="sxs-lookup"><span data-stu-id="2f65f-108">**resumeOutputBookmark** \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="2f65f-109">output  \[out\]：指定作业的输出。</span><span class="sxs-lookup"><span data-stu-id="2f65f-109">**output** \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="2f65f-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2f65f-110">Return value</span></span>

<span data-ttu-id="2f65f-111">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="2f65f-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f65f-112">备注</span><span class="sxs-lookup"><span data-stu-id="2f65f-112">Remarks</span></span>

<span data-ttu-id="2f65f-113">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="2f65f-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f65f-114">要求</span><span class="sxs-lookup"><span data-stu-id="2f65f-114">Requirements</span></span>

<span data-ttu-id="2f65f-115">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2f65f-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2f65f-116">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f65f-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2f65f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f65f-117">See also</span></span>

[<span data-ttu-id="2f65f-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2f65f-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
