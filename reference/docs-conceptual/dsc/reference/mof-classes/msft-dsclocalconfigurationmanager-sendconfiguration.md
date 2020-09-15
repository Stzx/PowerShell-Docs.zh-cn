---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: SendConfiguration 方法
ms.openlocfilehash: afd6e8d7acc969df16fad1d0ba15c9fe0b1a26fd
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463935"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="dc564-103">SendConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="dc564-103">SendConfiguration method</span></span>

<span data-ttu-id="dc564-104">将配置文档发送到托管节点并将其保存为挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="dc564-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc564-105">语法</span><span class="sxs-lookup"><span data-stu-id="dc564-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="dc564-106">参数</span><span class="sxs-lookup"><span data-stu-id="dc564-106">Parameters</span></span>

<span data-ttu-id="dc564-107">ConfigurationData  \[in\]：配置的环境数据。</span><span class="sxs-lookup"><span data-stu-id="dc564-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="dc564-108">force  \[in\]：若为 true  ，则强制停止配置。</span><span class="sxs-lookup"><span data-stu-id="dc564-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="dc564-109">返回值</span><span class="sxs-lookup"><span data-stu-id="dc564-109">Return value</span></span>

<span data-ttu-id="dc564-110">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="dc564-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc564-111">备注</span><span class="sxs-lookup"><span data-stu-id="dc564-111">Remarks</span></span>

<span data-ttu-id="dc564-112">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="dc564-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc564-113">要求</span><span class="sxs-lookup"><span data-stu-id="dc564-113">Requirements</span></span>

<span data-ttu-id="dc564-114">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="dc564-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="dc564-115">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="dc564-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="dc564-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc564-116">See also</span></span>

[<span data-ttu-id="dc564-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="dc564-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
