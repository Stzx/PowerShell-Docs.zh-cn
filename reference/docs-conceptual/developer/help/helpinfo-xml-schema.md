---
title: HelpInfo XML 架构
ms.date: 09/12/2016
ms.openlocfilehash: e894c1f2695ddbc5a386f8fec96054a7b31e7778
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893248"
---
# <a name="helpinfo-xml-schema"></a>HelpInfo XML 架构

本主题包含可更新帮助信息文件（通常称为 "HelpInfo XML 文件"）的 XML 架构。

## <a name="helpinfo-xml-schema"></a>HelpInfo XML 架构

HelpInfo XML 文件基于以下 XML 架构。

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="https://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
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

## <a name="helpinfo-xml-elements"></a>HelpInfo XML 元素

HelpInfo XML 文件包含以下元素。

- **HelpContentURI** -包含模块的帮助 CAB 文件位置的 URI。 URI 必须以 "http" 或 "https" 开头。 URI 应指定 internet 位置，但不得包含 CAB 文件名。 **HelpContentURI**值可以与**HelpInfoURI**值相同或不同。

- **SupportedUICultures** -表示所有 UI 区域性中的模块帮助文件。 包含**UICulture**元素，其中每个元素都表示一组指定 UI 区域性中的模块的帮助文件。

- **UICulture** -表示指定 UI 区域性中的模块的一组帮助文件。 为在其中编写帮助文件的每个 UI 区域性添加一个**UICulture**元素。

- **UICultureName** -包含在其中编写帮助文件的 UI 区域性的语言代码。

- **UICultureVersion** -在 "N1。N2.N3.N4 "格式，表示 UI 区域性中 help CAB 文件的版本。 每次上传**UICultureName**指定的 UI 区域性中的新帮助 CAB 文件时，请递增此版本号。 有关此值的详细信息，请参阅[版本类](/dotnet/api/system.version)。
