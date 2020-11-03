---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113345
Help Version: 7.0.1.0
Locale: en-US
Module Guid: 0e7b895d-2fec-43f7-8cae-11e8d16f6e40
Module Name: ThreadJob
ms.date: 07/09/2019
title: ThreadJob 模块
ms.openlocfilehash: 0e368b474123130e44250adb53d5bd6a5415dc91
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199146"
---
# <span data-ttu-id="5539c-102">ThreadJob 模块</span><span class="sxs-lookup"><span data-stu-id="5539c-102">ThreadJob Module</span></span>

## <span data-ttu-id="5539c-103">说明</span><span class="sxs-lookup"><span data-stu-id="5539c-103">Description</span></span>
<span data-ttu-id="5539c-104">此模块扩展现有的 PowerShell BackgroundJob，以包含基于线程的新 **ThreadJob** 作业。</span><span class="sxs-lookup"><span data-stu-id="5539c-104">This module extends the existing PowerShell BackgroundJob to include a new thread based **ThreadJob** job.</span></span> <span data-ttu-id="5539c-105">这是一种更轻量的解决方案，用于运行在现有 PowerShell 作业基础结构中工作的并发 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="5539c-105">This is a lighter weight solution for running concurrent PowerShell scripts that works within the existing PowerShell job infrastructure.</span></span>

## <span data-ttu-id="5539c-106">ThreadJob Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5539c-106">ThreadJob Cmdlets</span></span>

### [<span data-ttu-id="5539c-107">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="5539c-107">Start-ThreadJob</span></span>](Start-ThreadJob.md)
<span data-ttu-id="5539c-108">创建类似于 cmdlet 的后台作业 `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="5539c-108">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>
