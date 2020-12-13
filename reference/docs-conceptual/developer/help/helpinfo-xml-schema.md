---
ms.date: 09/12/2016
ms.topic: reference
title: HelpInfo XML 架构
description: HelpInfo XML 架构
ms.openlocfilehash: 157fd9c0f47c57efbaa9b7888fa174a34ad9567d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662020"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="f773b-103">HelpInfo XML 架构</span><span class="sxs-lookup"><span data-stu-id="f773b-103">HelpInfo XML Schema</span></span>

<span data-ttu-id="f773b-104">本主题包含可更新帮助信息文件（通常称为 "HelpInfo XML 文件"）的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="f773b-104">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="f773b-105">HelpInfo XML 架构</span><span class="sxs-lookup"><span data-stu-id="f773b-105">HelpInfo XML Schema</span></span>

<span data-ttu-id="f773b-106">HelpInfo XML 文件基于以下 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="f773b-106">HelpInfo XML files are based on the following XML schema.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="http://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
  <element name="HelpInfo">
    <complexType>
      <sequence>
        <element name="HelpContentURI" type="anyURI" minOccurs="1" maxOccurs="1" />
        <element name="SupportedUICultures" minOccurs="1" maxOccurs="1">
          <complexType>
            <sequence>
              <element name="UICulture" minOccurs="1" maxOccurs="unbounded">
                <complexType>
                  <sequence>
                    <element name="UICultureName" type="language" minOccurs="1" maxOccurs="1" />
                    <element name="UICultureVersion" type="string" minOccurs="1" maxOccurs="1" />
                  </sequence>
                </complexType>
              </element>
            </sequence>
          </complexType>
        </element>
      </sequence>
    </complexType>
  </element>
</schema>
```

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="f773b-107">HelpInfo XML 元素</span><span class="sxs-lookup"><span data-stu-id="f773b-107">HelpInfo XML Elements</span></span>

<span data-ttu-id="f773b-108">HelpInfo XML 文件包含以下元素。</span><span class="sxs-lookup"><span data-stu-id="f773b-108">The HelpInfo XML file includes the following elements.</span></span>

- <span data-ttu-id="f773b-109">**HelpContentURI** -包含模块的帮助 CAB 文件位置的 URI。</span><span class="sxs-lookup"><span data-stu-id="f773b-109">**HelpContentURI** - Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="f773b-110">URI 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="f773b-110">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="f773b-111">URI 应指定 internet 位置，但不得包含 CAB 文件名。</span><span class="sxs-lookup"><span data-stu-id="f773b-111">The URI should specify an internet location, but must not include the CAB filename.</span></span> <span data-ttu-id="f773b-112">**HelpContentURI** 值可以与 **HelpInfoURI** 值相同或不同。</span><span class="sxs-lookup"><span data-stu-id="f773b-112">The **HelpContentURI** value can be the same or different from the **HelpInfoURI** value.</span></span>

- <span data-ttu-id="f773b-113">**SupportedUICultures** -表示所有 UI 区域性中的模块帮助文件。</span><span class="sxs-lookup"><span data-stu-id="f773b-113">**SupportedUICultures** - Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="f773b-114">包含 **UICulture** 元素，其中每个元素都表示一组指定 UI 区域性中的模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="f773b-114">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

- <span data-ttu-id="f773b-115">**UICulture** -表示指定 UI 区域性中的模块的一组帮助文件。</span><span class="sxs-lookup"><span data-stu-id="f773b-115">**UICulture** - Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="f773b-116">为在其中编写帮助文件的每个 UI 区域性添加一个 **UICulture** 元素。</span><span class="sxs-lookup"><span data-stu-id="f773b-116">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

- <span data-ttu-id="f773b-117">**UICultureName** -包含在其中编写帮助文件的 UI 区域性的语言代码。</span><span class="sxs-lookup"><span data-stu-id="f773b-117">**UICultureName** - Contains the language code for the UI culture in which the help files are written.</span></span>

- <span data-ttu-id="f773b-118">**UICultureVersion** -在 "N1。N2.N3.N4 "格式，表示 UI 区域性中 help CAB 文件的版本。</span><span class="sxs-lookup"><span data-stu-id="f773b-118">**UICultureVersion** - Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="f773b-119">每次上传 **UICultureName** 指定的 UI 区域性中的新帮助 CAB 文件时，请递增此版本号。</span><span class="sxs-lookup"><span data-stu-id="f773b-119">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="f773b-120">有关此值的详细信息，请参阅 [版本类](/dotnet/api/system.version)。</span><span class="sxs-lookup"><span data-stu-id="f773b-120">For more information about this value, see [Version Class](/dotnet/api/system.version).</span></span>
