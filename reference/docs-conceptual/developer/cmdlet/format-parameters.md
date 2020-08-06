---
title: 格式参数 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8e031f62aa8bcb0e9d5b900b2eace7187b1f3dd
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784276"
---
# <a name="format-parameters"></a><span data-ttu-id="6922c-102">格式参数</span><span class="sxs-lookup"><span data-stu-id="6922c-102">Format Parameters</span></span>

<span data-ttu-id="6922c-103">下表列出了用于格式化或生成数据的参数的建议名称和功能。</span><span class="sxs-lookup"><span data-stu-id="6922c-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="6922c-104">参数</span><span class="sxs-lookup"><span data-stu-id="6922c-104">Parameter</span></span>|<span data-ttu-id="6922c-105">功能</span><span class="sxs-lookup"><span data-stu-id="6922c-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="6922c-106">**方式**</span><span class="sxs-lookup"><span data-stu-id="6922c-106">**As**</span></span><br><span data-ttu-id="6922c-107">数据类型：关键字</span><span class="sxs-lookup"><span data-stu-id="6922c-107">Data type: Keyword</span></span>|<span data-ttu-id="6922c-108">实现此参数以指定 cmdlet 输出格式。</span><span class="sxs-lookup"><span data-stu-id="6922c-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="6922c-109">例如，可能的值可以是文本或脚本。</span><span class="sxs-lookup"><span data-stu-id="6922c-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="6922c-110">**二进制**</span><span class="sxs-lookup"><span data-stu-id="6922c-110">**Binary**</span></span><br><span data-ttu-id="6922c-111">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6922c-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="6922c-112">实现此参数以指示该 cmdlet 处理二进制值。</span><span class="sxs-lookup"><span data-stu-id="6922c-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="6922c-113">**编码**</span><span class="sxs-lookup"><span data-stu-id="6922c-113">**Encoding**</span></span><br><span data-ttu-id="6922c-114">数据类型：关键字</span><span class="sxs-lookup"><span data-stu-id="6922c-114">Data type: Keyword</span></span>|<span data-ttu-id="6922c-115">实现此参数可指定支持的编码类型。</span><span class="sxs-lookup"><span data-stu-id="6922c-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="6922c-116">例如，可能的值可能是 ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte 和 String。</span><span class="sxs-lookup"><span data-stu-id="6922c-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="6922c-117">**换**</span><span class="sxs-lookup"><span data-stu-id="6922c-117">**NewLine**</span></span><br><span data-ttu-id="6922c-118">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6922c-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="6922c-119">实现此参数，以便在指定参数时支持换行字符。</span><span class="sxs-lookup"><span data-stu-id="6922c-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="6922c-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="6922c-120">**ShortName**</span></span><br><span data-ttu-id="6922c-121">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6922c-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="6922c-122">实现此参数以便在指定参数时支持短名称。</span><span class="sxs-lookup"><span data-stu-id="6922c-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="6922c-123">Width</span><span class="sxs-lookup"><span data-stu-id="6922c-123">**Width**</span></span><br><span data-ttu-id="6922c-124">数据类型： Int32</span><span class="sxs-lookup"><span data-stu-id="6922c-124">Data type: Int32</span></span>|<span data-ttu-id="6922c-125">实现此参数，以便用户可以指定输出设备的宽度。</span><span class="sxs-lookup"><span data-stu-id="6922c-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="6922c-126">**包装**</span><span class="sxs-lookup"><span data-stu-id="6922c-126">**Wrap**</span></span><br><span data-ttu-id="6922c-127">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6922c-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="6922c-128">实现此参数以便在指定参数时支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="6922c-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="6922c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6922c-129">See Also</span></span>

[<span data-ttu-id="6922c-130">Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="6922c-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="6922c-131">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6922c-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="6922c-132">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="6922c-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
