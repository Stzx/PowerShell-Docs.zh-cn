---
ms.date: 09/13/2016
ms.topic: reference
title: 格式参数
description: 格式参数
ms.openlocfilehash: 5f970683fedc71b208ff6becad761d94611a91a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652818"
---
# <a name="format-parameters"></a><span data-ttu-id="1c576-103">格式参数</span><span class="sxs-lookup"><span data-stu-id="1c576-103">Format Parameters</span></span>

<span data-ttu-id="1c576-104">下表列出了用于格式化或生成数据的参数的建议名称和功能。</span><span class="sxs-lookup"><span data-stu-id="1c576-104">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="1c576-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c576-105">Parameter</span></span>|<span data-ttu-id="1c576-106">功能</span><span class="sxs-lookup"><span data-stu-id="1c576-106">Functionality</span></span>|
|---|---|
|<span data-ttu-id="1c576-107">**方式**</span><span class="sxs-lookup"><span data-stu-id="1c576-107">**As**</span></span><br><span data-ttu-id="1c576-108">数据类型：关键字</span><span class="sxs-lookup"><span data-stu-id="1c576-108">Data type: Keyword</span></span>|<span data-ttu-id="1c576-109">实现此参数以指定 cmdlet 输出格式。</span><span class="sxs-lookup"><span data-stu-id="1c576-109">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="1c576-110">例如，可能的值可以是文本或脚本。</span><span class="sxs-lookup"><span data-stu-id="1c576-110">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="1c576-111">**二进制**</span><span class="sxs-lookup"><span data-stu-id="1c576-111">**Binary**</span></span><br><span data-ttu-id="1c576-112">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1c576-112">Data type: SwitchParameter</span></span>|<span data-ttu-id="1c576-113">实现此参数以指示该 cmdlet 处理二进制值。</span><span class="sxs-lookup"><span data-stu-id="1c576-113">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="1c576-114">**编码**</span><span class="sxs-lookup"><span data-stu-id="1c576-114">**Encoding**</span></span><br><span data-ttu-id="1c576-115">数据类型：关键字</span><span class="sxs-lookup"><span data-stu-id="1c576-115">Data type: Keyword</span></span>|<span data-ttu-id="1c576-116">实现此参数可指定支持的编码类型。</span><span class="sxs-lookup"><span data-stu-id="1c576-116">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="1c576-117">例如，可能的值可能是 ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte 和 String。</span><span class="sxs-lookup"><span data-stu-id="1c576-117">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="1c576-118">**换**</span><span class="sxs-lookup"><span data-stu-id="1c576-118">**NewLine**</span></span><br><span data-ttu-id="1c576-119">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1c576-119">Data type: SwitchParameter</span></span>|<span data-ttu-id="1c576-120">实现此参数，以便在指定参数时支持换行字符。</span><span class="sxs-lookup"><span data-stu-id="1c576-120">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="1c576-121">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="1c576-121">**ShortName**</span></span><br><span data-ttu-id="1c576-122">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1c576-122">Data type: SwitchParameter</span></span>|<span data-ttu-id="1c576-123">实现此参数以便在指定参数时支持短名称。</span><span class="sxs-lookup"><span data-stu-id="1c576-123">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="1c576-124">Width </span><span class="sxs-lookup"><span data-stu-id="1c576-124">**Width**</span></span><br><span data-ttu-id="1c576-125">数据类型： Int32</span><span class="sxs-lookup"><span data-stu-id="1c576-125">Data type: Int32</span></span>|<span data-ttu-id="1c576-126">实现此参数，以便用户可以指定输出设备的宽度。</span><span class="sxs-lookup"><span data-stu-id="1c576-126">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="1c576-127">**包装**</span><span class="sxs-lookup"><span data-stu-id="1c576-127">**Wrap**</span></span><br><span data-ttu-id="1c576-128">数据类型： SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1c576-128">Data type: SwitchParameter</span></span>|<span data-ttu-id="1c576-129">实现此参数以便在指定参数时支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="1c576-129">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="1c576-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c576-130">See Also</span></span>

[<span data-ttu-id="1c576-131">Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="1c576-131">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="1c576-132">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1c576-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="1c576-133">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="1c576-133">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
