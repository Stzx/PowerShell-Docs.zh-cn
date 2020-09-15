---
ms.date: 07/17/2020
keywords: dsc,powershell,配置,安装程序
title: SendMetaConfigurationApply 方法
ms.openlocfilehash: 896afe2f3370e108b48583aafb33ee7b0eb1301b
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463714"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="0078d-103">SendMetaConfigurationApply 方法</span><span class="sxs-lookup"><span data-stu-id="0078d-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="0078d-104">设置用于控制配置代理的本地配置管理器设置。</span><span class="sxs-lookup"><span data-stu-id="0078d-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="0078d-105">语法</span><span class="sxs-lookup"><span data-stu-id="0078d-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="0078d-106">参数</span><span class="sxs-lookup"><span data-stu-id="0078d-106">Parameters</span></span>

<span data-ttu-id="0078d-107">ConfigurationData  \[in\]：配置的环境数据。</span><span class="sxs-lookup"><span data-stu-id="0078d-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="0078d-108">force  \[in\]：若为 true  ，则强制停止配置。</span><span class="sxs-lookup"><span data-stu-id="0078d-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="0078d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0078d-109">Return value</span></span>

<span data-ttu-id="0078d-110">如果成功，则返回零；否则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="0078d-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0078d-111">备注</span><span class="sxs-lookup"><span data-stu-id="0078d-111">Remarks</span></span>

<span data-ttu-id="0078d-112">这是一种静态方法。</span><span class="sxs-lookup"><span data-stu-id="0078d-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0078d-113">要求</span><span class="sxs-lookup"><span data-stu-id="0078d-113">Requirements</span></span>

<span data-ttu-id="0078d-114">**MOF：** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0078d-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="0078d-115">**命名空间**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0078d-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="0078d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0078d-116">See also</span></span>

[<span data-ttu-id="0078d-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0078d-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
