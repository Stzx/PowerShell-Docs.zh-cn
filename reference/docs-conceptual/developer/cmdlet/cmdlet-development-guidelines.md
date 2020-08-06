---
title: Cmdlet 开发指南 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.openlocfilehash: 5dd83b12a9052ff5f146c4c4e077a9358907cbd0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784480"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="8f287-102">Cmdlet 开发指南</span><span class="sxs-lookup"><span data-stu-id="8f287-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="8f287-103">本节中的主题提供了可用于生成格式正确的 cmdlet 的开发指南。</span><span class="sxs-lookup"><span data-stu-id="8f287-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="8f287-104">通过利用 Windows PowerShell 运行时提供的通用功能并遵循这些准则，你可以最大程度地开发强大的 cmdlet，并为用户提供一致的体验。</span><span class="sxs-lookup"><span data-stu-id="8f287-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="8f287-105">此外，您还可以减少测试负担，因为一般功能不需要重新测试。</span><span class="sxs-lookup"><span data-stu-id="8f287-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8f287-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f287-106">In This Section</span></span>

- [<span data-ttu-id="8f287-107">必需的开发指南</span><span class="sxs-lookup"><span data-stu-id="8f287-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="8f287-108">强烈建议的开发指南</span><span class="sxs-lookup"><span data-stu-id="8f287-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="8f287-109">咨询性的开发指南</span><span class="sxs-lookup"><span data-stu-id="8f287-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="8f287-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f287-110">See Also</span></span>

[<span data-ttu-id="8f287-111">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f287-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="8f287-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8f287-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
