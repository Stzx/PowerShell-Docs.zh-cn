---
ms.date: 07/17/2020
ms.topic: reference
title: ResourceGet 方法
description: ResourceGet 方法
ms.openlocfilehash: bff737f04e02740fa09fd82d7b27c75b11303dad
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650767"
---
# <a name="resourceget-method"></a><span data-ttu-id="c6d15-103">ResourceGet 方法</span><span class="sxs-lookup"><span data-stu-id="c6d15-103">ResourceGet method</span></span>

<span data-ttu-id="c6d15-104">直接调用 DSC 资源的 **Get** 方法。</span><span class="sxs-lookup"><span data-stu-id="c6d15-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6d15-105">语法</span><span class="sxs-lookup"><span data-stu-id="c6d15-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="c6d15-106">参数</span><span class="sxs-lookup"><span data-stu-id="c6d15-106">Parameters</span></span>

<span data-ttu-id="c6d15-107">ResourceType  \[in\]：要调用的资源的名称。</span><span class="sxs-lookup"><span data-stu-id="c6d15-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="c6d15-108">ModuleName  \[in\]：包含要调用资源的模块名称。</span><span class="sxs-lookup"><span data-stu-id="c6d15-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="c6d15-109">resourceProperty  \[in\]：在哈希表中分别将资源属性名及其值指定为键和值。</span><span class="sxs-lookup"><span data-stu-id="c6d15-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="c6d15-110">使用 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet 可以发现资源属性及其类型。</span><span class="sxs-lookup"><span data-stu-id="c6d15-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="c6d15-111">configurations  \[out\]：返回响应时，包含配置的嵌入实例。</span><span class="sxs-lookup"><span data-stu-id="c6d15-111">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="c6d15-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c6d15-112">Return value</span></span>

<span data-ttu-id="c6d15-113">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="c6d15-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6d15-114">备注</span><span class="sxs-lookup"><span data-stu-id="c6d15-114">Remarks</span></span>

<span data-ttu-id="c6d15-115">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="c6d15-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6d15-116">要求</span><span class="sxs-lookup"><span data-stu-id="c6d15-116">Requirements</span></span>

<span data-ttu-id="c6d15-117">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c6d15-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="c6d15-118">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6d15-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="c6d15-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6d15-119">See also</span></span>

[<span data-ttu-id="c6d15-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c6d15-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
