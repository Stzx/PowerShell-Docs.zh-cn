---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: TestConfiguration 方法
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464292"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="1ff37-103">TestConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="1ff37-103">TestConfiguration method</span></span>

<span data-ttu-id="1ff37-104">将配置文档发送到托管节点并针对该文档验证当前配置。</span><span class="sxs-lookup"><span data-stu-id="1ff37-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ff37-105">语法</span><span class="sxs-lookup"><span data-stu-id="1ff37-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="1ff37-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ff37-106">Parameters</span></span>

<span data-ttu-id="1ff37-107">**configurationData** \[in\] 配置的环境数据。</span><span class="sxs-lookup"><span data-stu-id="1ff37-107">**configurationData** \[in\] Environment data for the configuration.</span></span>

<span data-ttu-id="1ff37-108">InDesiredState  \[out\]：返回响应时，指定托管节点是否处于配置文档指定的状态。</span><span class="sxs-lookup"><span data-stu-id="1ff37-108">**InDesiredState** \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="1ff37-109">ResourcesInDesiredState  \[out\]：返回响应时，包含 MSFT_ResourceInDesiredState  类的嵌入实例，此类指定处于所需状态的资源。</span><span class="sxs-lookup"><span data-stu-id="1ff37-109">**ResourcesInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="1ff37-110">ResourcesNotInDesiredState  \[out\]：返回响应时，包含 MSFT_ResourceNotInDesiredState  类的嵌入实例，此类指定不处于所需状态的资源。</span><span class="sxs-lookup"><span data-stu-id="1ff37-110">**ResourcesNotInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="1ff37-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1ff37-111">Return value</span></span>

<span data-ttu-id="1ff37-112">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="1ff37-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ff37-113">备注</span><span class="sxs-lookup"><span data-stu-id="1ff37-113">Remarks</span></span>

<span data-ttu-id="1ff37-114">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="1ff37-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ff37-115">要求</span><span class="sxs-lookup"><span data-stu-id="1ff37-115">Requirements</span></span>

<span data-ttu-id="1ff37-116">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1ff37-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1ff37-117">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1ff37-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1ff37-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ff37-118">See also</span></span>

[<span data-ttu-id="1ff37-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1ff37-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
