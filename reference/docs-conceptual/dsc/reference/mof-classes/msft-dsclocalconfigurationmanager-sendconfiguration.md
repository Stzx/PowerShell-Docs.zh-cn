---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: SendConfiguration 方法
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953384"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="e48c6-103">SendConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="e48c6-103">SendConfiguration method</span></span>

<span data-ttu-id="e48c6-104">将配置文档发送到托管节点并将其保存为挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="e48c6-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="e48c6-105">语法</span><span class="sxs-lookup"><span data-stu-id="e48c6-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="e48c6-106">参数</span><span class="sxs-lookup"><span data-stu-id="e48c6-106">Parameters</span></span>

<span data-ttu-id="e48c6-107">ConfigurationData  \[in\]：配置的环境数据。</span><span class="sxs-lookup"><span data-stu-id="e48c6-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="e48c6-108">force  \[in\]：若为 true  ，则强制停止配置。</span><span class="sxs-lookup"><span data-stu-id="e48c6-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="e48c6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e48c6-109">Return value</span></span>

<span data-ttu-id="e48c6-110">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="e48c6-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e48c6-111">备注</span><span class="sxs-lookup"><span data-stu-id="e48c6-111">Remarks</span></span>

<span data-ttu-id="e48c6-112">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="e48c6-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e48c6-113">要求</span><span class="sxs-lookup"><span data-stu-id="e48c6-113">Requirements</span></span>

<span data-ttu-id="e48c6-114">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e48c6-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e48c6-115">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e48c6-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e48c6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e48c6-116">See also</span></span>

[<span data-ttu-id="e48c6-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e48c6-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
