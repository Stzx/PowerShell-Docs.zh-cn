---
ms.date: 06/12/2017
keywords: dsc,powershell,配置,安装程序
title: 设置 DSC请求客户端
description: 本文概述了可用于设置 DSC 拉取客户端的信息。
ms.openlocfilehash: 584af3aee46d801e363422ae7a197348231a1442
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646819"
---
# <a name="setting-up-a-dsc-pull-client"></a><span data-ttu-id="59b96-104">设置 DSC请求客户端</span><span class="sxs-lookup"><span data-stu-id="59b96-104">Setting up a DSC pull client</span></span>

> <span data-ttu-id="59b96-105">适用于：Windows PowerShell 4.0 和 Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="59b96-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59b96-106">请求服务器（Windows 功能 DSC-Service）是 Windows Server 的一个受支持组件，不过目前没有提供新功能的计划。</span><span class="sxs-lookup"><span data-stu-id="59b96-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="59b96-107">建议开始将托管客户端转换至 [Azure Automation DSC](/azure/automation/automation-dsc-getting-started)（包括 Windows Server 上的请求服务器以外的功能）或[此处](pullserver.md#community-solutions-for-pull-service)列出的社区解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="59b96-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="59b96-108">必须告知每个目标节点使用请求模式，并为其提供用于联系请求服务器以获取配置和资源以及应在其中发送报表数据的 URL 或文件位置。</span><span class="sxs-lookup"><span data-stu-id="59b96-108">Each target node has to be told to use pull mode and given the URL or file location where it can contact the pull server to get configurations and resources, and where it should send report data.</span></span>

<span data-ttu-id="59b96-109">以下主题说明了如何设置请求客户端：</span><span class="sxs-lookup"><span data-stu-id="59b96-109">The following topics explain how to set up pull clients:</span></span>

- <span data-ttu-id="59b96-110">[使用配置名称设置拉取客户端](pullClientConfigNames.md)
\*-[使用配置 ID 设置拉取客户端](pullClientConfigID.md)</span><span class="sxs-lookup"><span data-stu-id="59b96-110">[Setting up a pull client using configuration names](pullClientConfigNames.md)
\*-[Setting up a pull client using configuration ID](pullClientConfigID.md)</span></span>

> [!NOTE]
> <span data-ttu-id="59b96-111">这些主题适用于 PowerShell 5.0。</span><span class="sxs-lookup"><span data-stu-id="59b96-111">These topics apply to PowerShell 5.0.</span></span> <span data-ttu-id="59b96-112">有关在 PowerShell 4.0 中设置请求客户端的信息，请参阅[在 PowerShell 4.0 中使用配置 ID 设置请求客户端](pullClientConfigID4.md)。</span><span class="sxs-lookup"><span data-stu-id="59b96-112">To set up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md).</span></span>
