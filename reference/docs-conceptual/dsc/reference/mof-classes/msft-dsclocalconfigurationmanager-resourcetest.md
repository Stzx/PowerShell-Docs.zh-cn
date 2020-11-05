---
ms.date: 07/17/2020
ms.topic: reference
title: ResourceTest 方法
description: ResourceTest 方法
ms.openlocfilehash: cbac53ea96a59ec92fa840f75cd264a3125b965a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650677"
---
# <a name="resourcetest-method"></a><span data-ttu-id="892f3-103">ResourceTest 方法</span><span class="sxs-lookup"><span data-stu-id="892f3-103">ResourceTest method</span></span>

<span data-ttu-id="892f3-104">直接调用 DSC 资源的 **Test** 方法。</span><span class="sxs-lookup"><span data-stu-id="892f3-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="892f3-105">语法</span><span class="sxs-lookup"><span data-stu-id="892f3-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="892f3-106">参数</span><span class="sxs-lookup"><span data-stu-id="892f3-106">Parameters</span></span>

<span data-ttu-id="892f3-107">ResourceType  \[in\]：要调用的资源的名称。</span><span class="sxs-lookup"><span data-stu-id="892f3-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="892f3-108">ModuleName  \[in\]：包含要调用资源的模块名称。</span><span class="sxs-lookup"><span data-stu-id="892f3-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="892f3-109">resourceProperty\* \[in\] 在哈希表中分别将资源属性名及其值指定为键和值。</span><span class="sxs-lookup"><span data-stu-id="892f3-109">\**_resourceProperty_* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="892f3-110">使用 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet 可以发现资源属性及其类型。</span><span class="sxs-lookup"><span data-stu-id="892f3-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="892f3-111">*InDesiredState*\* \[out\] 返回响应时，如果目标节点处于所需状态，便会将此属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="892f3-111">*InDesiredState*\* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="892f3-112">返回值</span><span class="sxs-lookup"><span data-stu-id="892f3-112">Return value</span></span>

<span data-ttu-id="892f3-113">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="892f3-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="892f3-114">备注</span><span class="sxs-lookup"><span data-stu-id="892f3-114">Remarks</span></span>

<span data-ttu-id="892f3-115">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="892f3-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="892f3-116">要求</span><span class="sxs-lookup"><span data-stu-id="892f3-116">Requirements</span></span>

<span data-ttu-id="892f3-117">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="892f3-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="892f3-118">**命名空间** ：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="892f3-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="892f3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="892f3-119">See also</span></span>

[<span data-ttu-id="892f3-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="892f3-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
