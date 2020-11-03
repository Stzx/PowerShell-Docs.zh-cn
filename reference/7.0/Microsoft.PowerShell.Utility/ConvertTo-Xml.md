---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: c8d4f0607c28160ec40f9b36e03afdb7ba8b0c16
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197143"
---
# <span data-ttu-id="43a21-103">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="43a21-103">ConvertTo-Xml</span></span>

## <span data-ttu-id="43a21-104">摘要</span><span class="sxs-lookup"><span data-stu-id="43a21-104">SYNOPSIS</span></span>
<span data-ttu-id="43a21-105">创建对象的基于 XML 的表示形式。</span><span class="sxs-lookup"><span data-stu-id="43a21-105">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="43a21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43a21-106">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="43a21-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43a21-107">DESCRIPTION</span></span>

<span data-ttu-id="43a21-108">`ConvertTo-Xml`Cmdlet 可创建一个或多个更多 .net 对象的[基于 XML](/dotnet/api/system.xml.xmldocument)的表示形式。</span><span class="sxs-lookup"><span data-stu-id="43a21-108">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="43a21-109">若要使用此 cmdlet，请通过管道将一个或多个对象传递给 cmdlet，或使用 **InputObject** 参数来指定对象。</span><span class="sxs-lookup"><span data-stu-id="43a21-109">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="43a21-110">当通过管道将多个对象传递给 `ConvertTo-Xml` 或使用 **InputObject** 参数提交多个对象时，将 `ConvertTo-Xml` 返回一个内存中 XML 文档，其中包含所有对象的表示形式。</span><span class="sxs-lookup"><span data-stu-id="43a21-110">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="43a21-111">此 cmdlet 类似于 [export-clixml](./Export-Clixml.md) ，但前者将 `Export-Clixml` 生成的 XML 存储在 [公共语言基础结构中 (CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) 文件，该文件可以重新导入为包含 [export-clixml](./Import-Clixml.md)的对象。</span><span class="sxs-lookup"><span data-stu-id="43a21-111">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="43a21-112">`ConvertTo-Xml` 返回 XML 文档的内存中表示形式，以便您可以继续在 PowerShell 中处理它。</span><span class="sxs-lookup"><span data-stu-id="43a21-112">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="43a21-113">`ConvertTo-Xml` 没有将对象转换为 CLI XML 的选项。</span><span class="sxs-lookup"><span data-stu-id="43a21-113">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="43a21-114">示例</span><span class="sxs-lookup"><span data-stu-id="43a21-114">EXAMPLES</span></span>

### <span data-ttu-id="43a21-115">示例1：将日期转换为 XML</span><span class="sxs-lookup"><span data-stu-id="43a21-115">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="43a21-116">此命令将 **DateTime** 对象) 的当前日期转换为 XML (。</span><span class="sxs-lookup"><span data-stu-id="43a21-116">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="43a21-117">示例2：将进程转换为 XML</span><span class="sxs-lookup"><span data-stu-id="43a21-117">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="43a21-118">此命令可将表示计算机上所有进程的进程对象转换为一个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="43a21-118">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="43a21-119">这些对象的级别深度将扩展至三。</span><span class="sxs-lookup"><span data-stu-id="43a21-119">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="43a21-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43a21-120">PARAMETERS</span></span>

### <span data-ttu-id="43a21-121">-As</span><span class="sxs-lookup"><span data-stu-id="43a21-121">-As</span></span>

<span data-ttu-id="43a21-122">确定输出格式。</span><span class="sxs-lookup"><span data-stu-id="43a21-122">Determines the output format.</span></span>
<span data-ttu-id="43a21-123">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="43a21-123">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="43a21-124">字符串。</span><span class="sxs-lookup"><span data-stu-id="43a21-124">String.</span></span>
<span data-ttu-id="43a21-125">返回单个字符串。</span><span class="sxs-lookup"><span data-stu-id="43a21-125">Returns a single string.</span></span>
- <span data-ttu-id="43a21-126">流。</span><span class="sxs-lookup"><span data-stu-id="43a21-126">Stream.</span></span>
<span data-ttu-id="43a21-127">返回一个字符串数组。</span><span class="sxs-lookup"><span data-stu-id="43a21-127">Returns an array of strings.</span></span>
- <span data-ttu-id="43a21-128">Document。</span><span class="sxs-lookup"><span data-stu-id="43a21-128">Document.</span></span>
<span data-ttu-id="43a21-129">返回一个 **xml** 对象。</span><span class="sxs-lookup"><span data-stu-id="43a21-129">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="43a21-130">默认值为 Document。</span><span class="sxs-lookup"><span data-stu-id="43a21-130">The default value is Document.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43a21-131">-Depth</span><span class="sxs-lookup"><span data-stu-id="43a21-131">-Depth</span></span>

<span data-ttu-id="43a21-132">指定 XML 表示形式中所包含的包含对象的级别数。</span><span class="sxs-lookup"><span data-stu-id="43a21-132">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="43a21-133">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="43a21-133">The default value is 1.</span></span>

<span data-ttu-id="43a21-134">例如，如果对象的属性还包含对象，若要保存所包含对象的属性的 XML 表示形式，则必须将深度指定为 2。</span><span class="sxs-lookup"><span data-stu-id="43a21-134">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="43a21-135">可以覆盖 Types.ps1xml 文件中对象类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="43a21-135">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="43a21-136">有关详细信息，请参阅 about_Types.ps1xml。</span><span class="sxs-lookup"><span data-stu-id="43a21-136">For more information, see about_Types.ps1xml.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43a21-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="43a21-137">-InputObject</span></span>

<span data-ttu-id="43a21-138">指定要转换的对象。</span><span class="sxs-lookup"><span data-stu-id="43a21-138">Specifies the object to be converted.</span></span> <span data-ttu-id="43a21-139">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="43a21-139">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="43a21-140">还可以通过管道将对象传递给 **convertto-html** 。</span><span class="sxs-lookup"><span data-stu-id="43a21-140">You can also pipe objects to **ConvertTo-XML** .</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43a21-141">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="43a21-141">-NoTypeInformation</span></span>

<span data-ttu-id="43a21-142">省略对象节点中的 Type 属性。</span><span class="sxs-lookup"><span data-stu-id="43a21-142">Omits the Type attribute from the object nodes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43a21-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43a21-143">CommonParameters</span></span>

<span data-ttu-id="43a21-144">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="43a21-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43a21-145">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="43a21-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43a21-146">输入</span><span class="sxs-lookup"><span data-stu-id="43a21-146">INPUTS</span></span>

### <span data-ttu-id="43a21-147">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="43a21-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="43a21-148">可以通过管道将任何对象传递给 **convertto-html** 。</span><span class="sxs-lookup"><span data-stu-id="43a21-148">You can pipe any object to **ConvertTo-XML** .</span></span>

## <span data-ttu-id="43a21-149">输出</span><span class="sxs-lookup"><span data-stu-id="43a21-149">OUTPUTS</span></span>

### <span data-ttu-id="43a21-150">System.object 或 System.Xml.Xml文档</span><span class="sxs-lookup"><span data-stu-id="43a21-150">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="43a21-151">*As* 参数的值确定 **convertto-html** 返回的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="43a21-151">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="43a21-152">注释</span><span class="sxs-lookup"><span data-stu-id="43a21-152">NOTES</span></span>

## <span data-ttu-id="43a21-153">相关链接</span><span class="sxs-lookup"><span data-stu-id="43a21-153">RELATED LINKS</span></span>

[<span data-ttu-id="43a21-154">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="43a21-154">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="43a21-155">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="43a21-155">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="43a21-156">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="43a21-156">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="43a21-157">Get-Date</span><span class="sxs-lookup"><span data-stu-id="43a21-157">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="43a21-158">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="43a21-158">Import-Clixml</span></span>](Import-Clixml.md)
