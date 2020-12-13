---
ms.date: 09/12/2016
ms.topic: reference
title: 如何添加参数信息
description: 如何添加参数信息
ms.openlocfilehash: 8f4fc46ef256a77b058df4ba506124f80732cb39
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663056"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="6467f-103">如何添加参数信息</span><span class="sxs-lookup"><span data-stu-id="6467f-103">How to Add Parameter Information</span></span>

<span data-ttu-id="6467f-104">本部分介绍如何添加在 cmdlet 帮助主题的 **PARAMETERS** 节中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="6467f-104">This section describes how to add content that is displayed in the **PARAMETERS** section of the cmdlet Help topic.</span></span> <span data-ttu-id="6467f-105">帮助主题的 **参数** 部分列出了 cmdlet 的每个参数，并提供了每个参数的详细说明。</span><span class="sxs-lookup"><span data-stu-id="6467f-105">The **PARAMETERS** section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="6467f-106">" **参数** " 部分的内容应与 "帮助" 主题的 " **语法** " 部分的内容一致。</span><span class="sxs-lookup"><span data-stu-id="6467f-106">The content of the **PARAMETERS** section should be consistent with the content of the **SYNTAX** section of the Help topic.</span></span> <span data-ttu-id="6467f-107">帮助作者负责确保 " **语法** 和 **Parameters** " 节点包含类似的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="6467f-107">It is the responsibility of the Help author to make sure that both the **Syntax** and **Parameters** node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="6467f-108">若要获取帮助文件的完整视图，请打开 `dll-Help.xml` 位于 PowerShell 安装目录中的文件之一。</span><span class="sxs-lookup"><span data-stu-id="6467f-108">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="6467f-109">例如，该 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` 文件包含多个 PowerShell cmdlet 的内容。</span><span class="sxs-lookup"><span data-stu-id="6467f-109">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="6467f-110">添加参数</span><span class="sxs-lookup"><span data-stu-id="6467f-110">To Add Parameters</span></span>

1. <span data-ttu-id="6467f-111">打开 cmdlet 帮助文件，找到所记录的 cmdlet 的命令节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-111">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="6467f-112">如果要添加新的 cmdlet，则需要创建新的命令节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-112">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="6467f-113">帮助文件将包含为其提供帮助内容的每个 cmdlet 的命令节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-113">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="6467f-114">下面是空白命令节点的示例。</span><span class="sxs-lookup"><span data-stu-id="6467f-114">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

1. <span data-ttu-id="6467f-115">在命令节点中，找到 "说明" 节点并添加 "参数" 节点，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6467f-115">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span>
   <span data-ttu-id="6467f-116">只允许一个参数节点，并且它应紧跟在语法节点之后。</span><span class="sxs-lookup"><span data-stu-id="6467f-116">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

1. <span data-ttu-id="6467f-117">在 "参数" 节点中，添加 cmdlet 的每个参数的 **参数** 节点，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6467f-117">Within the Parameters node, add a **Parameter** node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="6467f-118">在此示例中，为三个参数添加了 **参数** 节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-118">In this example, a **Parameter** node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="6467f-119">由于这些是在语法节点中使用的相同 XML 标记，因此，在此处指定的参数必须与 "语法" 节点指定的参数匹配，你可以从 "语法" 节点复制参数节点，然后将其粘贴到 "参数" 节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-119">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="6467f-120">但是，请确保只复制参数节点的一个实例，即使该参数是在语法的多个参数集中指定的，也是如此。</span><span class="sxs-lookup"><span data-stu-id="6467f-120">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

1. <span data-ttu-id="6467f-121">对于每个参数节点，设置定义每个参数的特征的属性值。</span><span class="sxs-lookup"><span data-stu-id="6467f-121">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="6467f-122">这些属性包括以下属性： required、pipelineinput 和 position。</span><span class="sxs-lookup"><span data-stu-id="6467f-122">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="6467f-123">对于每个参数节点，添加参数的名称。</span><span class="sxs-lookup"><span data-stu-id="6467f-123">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="6467f-124">下面是添加到参数节点的参数名称的示例。</span><span class="sxs-lookup"><span data-stu-id="6467f-124">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="6467f-125">对于每个 **参数** 节点，添加参数的描述。</span><span class="sxs-lookup"><span data-stu-id="6467f-125">For each **Parameter** node, add the description of the parameter.</span></span> <span data-ttu-id="6467f-126">下面是添加到 **参数** 节点的参数说明的示例。</span><span class="sxs-lookup"><span data-stu-id="6467f-126">Here is an example of the parameter description added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="6467f-127">对于每个 **参数** 节点，添加参数的 .net 类型。</span><span class="sxs-lookup"><span data-stu-id="6467f-127">For each **Parameter** node, add the .NET type of the parameter.</span></span> <span data-ttu-id="6467f-128">参数类型与参数名称一起显示。</span><span class="sxs-lookup"><span data-stu-id="6467f-128">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="6467f-129">下面是添加到 **参数** 节点的 .net 类型参数的示例。</span><span class="sxs-lookup"><span data-stu-id="6467f-129">Here is an example of the parameter .NET type added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="6467f-130">对于每个 **参数** 节点，添加参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="6467f-130">For each **Parameter** node, add the default value of the parameter.</span></span> <span data-ttu-id="6467f-131">显示内容时，会将以下句子添加到参数说明：默认值为 **DefaultValue** 。</span><span class="sxs-lookup"><span data-stu-id="6467f-131">The following sentence is added to the parameter description when the content is displayed: **DefaultValue** is the default.</span></span>

   <span data-ttu-id="6467f-132">下面是一个将参数默认值添加到 **参数** 节点的示例。</span><span class="sxs-lookup"><span data-stu-id="6467f-132">Here is an example of the parameter default value is added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="6467f-133">对于每个具有多个值的参数，请添加一个可能的值节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-133">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="6467f-134">下面是可能的值节点的一个示例，它为参数定义了两个可能的值</span><span class="sxs-lookup"><span data-stu-id="6467f-134">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="6467f-135">下面是添加参数时要记住的一些内容。</span><span class="sxs-lookup"><span data-stu-id="6467f-135">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="6467f-136">参数的属性不会显示在 cmdlet 帮助主题的所有视图中。</span><span class="sxs-lookup"><span data-stu-id="6467f-136">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="6467f-137">但是，当用户要求提供 **完全** () 或参数时，它们将按参数说明显示在一个表中， `Get-Help <cmdletname> -full` ( `Get-Help <cmdletname> -parameter`) 视图。</span><span class="sxs-lookup"><span data-stu-id="6467f-137">However, they are displayed in a table following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help <cmdletname> -parameter`) view of the topic.</span></span>

- <span data-ttu-id="6467f-138">参数说明是 cmdlet 帮助主题最重要的部分之一。</span><span class="sxs-lookup"><span data-stu-id="6467f-138">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="6467f-139">说明应简短，并且是完整的。</span><span class="sxs-lookup"><span data-stu-id="6467f-139">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="6467f-140">另外，请记住，如果参数说明太长，例如两个参数彼此交互，则可以在 cmdlet 帮助主题的 "注释" 部分添加更多内容。</span><span class="sxs-lookup"><span data-stu-id="6467f-140">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="6467f-141">参数说明提供两种类型的信息。</span><span class="sxs-lookup"><span data-stu-id="6467f-141">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="6467f-142">使用参数时，cmdlet 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6467f-142">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="6467f-143">参数的合法值。</span><span class="sxs-lookup"><span data-stu-id="6467f-143">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="6467f-144">因为参数值表示为 .NET 对象，所以用户需要的这些值的详细信息与传统命令行帮助中的值不同。</span><span class="sxs-lookup"><span data-stu-id="6467f-144">Because the parameter values are expressed as .NET objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="6467f-145">告诉用户参数要接受的数据类型，并包括示例。</span><span class="sxs-lookup"><span data-stu-id="6467f-145">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="6467f-146">如果未在命令行上指定参数，则参数的默认值是使用的值。</span><span class="sxs-lookup"><span data-stu-id="6467f-146">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="6467f-147">请注意，默认值是可选的，对于某些参数（如所需参数）不需要此值。</span><span class="sxs-lookup"><span data-stu-id="6467f-147">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="6467f-148">但是，您应为大多数可选参数指定默认值。</span><span class="sxs-lookup"><span data-stu-id="6467f-148">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="6467f-149">默认值可帮助用户了解不使用参数的影响。</span><span class="sxs-lookup"><span data-stu-id="6467f-149">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="6467f-150">确切描述默认值，如 "当前目录" 或 "PowerShell 安装目录 (`$PSHOME`) " 中的可选路径。</span><span class="sxs-lookup"><span data-stu-id="6467f-150">Describe the default value very specifically, such as the "Current directory" or the "PowerShell installation directory (`$PSHOME`)" for an optional path.</span></span> <span data-ttu-id="6467f-151">还可以编写描述默认值的句子，如用于 **passthru** 参数的以下句子： "如果未指定 passthru，该 cmdlet 不会将对象向下传递管道。"</span><span class="sxs-lookup"><span data-stu-id="6467f-151">You can also write a sentence that describes the default, such as the following sentence used for the **PassThru** parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span> <span data-ttu-id="6467f-152">另外，由于值与字段名称 **默认值** 相对显示，因此不需要在条目中包含 "默认值" 一词。</span><span class="sxs-lookup"><span data-stu-id="6467f-152">Also, because the value is displayed opposite the field name **Default value**, you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="6467f-153">此参数的默认值不会显示在 cmdlet 帮助主题的所有视图中。</span><span class="sxs-lookup"><span data-stu-id="6467f-153">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="6467f-154">但是，当用户要求) 或参数的 **完整** (`Get-Help <cmdletname> -full` 或 **参数** (`Get-Help
<cmdletname> -parameter`) 视图时，它会显示在)  (的表中。</span><span class="sxs-lookup"><span data-stu-id="6467f-154">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help
<cmdletname> -parameter`) view of the topic.</span></span>

<span data-ttu-id="6467f-155">下面的 XML 演示 `<dev:defaultValue>` 添加到节点的一对标记 `<command:parameter>` 。</span><span class="sxs-lookup"><span data-stu-id="6467f-155">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span>
<span data-ttu-id="6467f-156">请注意，默认值紧跟在结束标记后 `</command:parameterValue>` (在指定参数值时) 或参数说明的结束 `</maml:description>` 标记。</span><span class="sxs-lookup"><span data-stu-id="6467f-156">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="6467f-157">名称。</span><span class="sxs-lookup"><span data-stu-id="6467f-157">name.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

<span data-ttu-id="6467f-158">为枚举类型添加值</span><span class="sxs-lookup"><span data-stu-id="6467f-158">Add Values for Enumerated Types</span></span>

<span data-ttu-id="6467f-159">如果参数具有多个值或枚举类型的值，则可以使用可选 \<dev:possibleValues> 节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-159">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="6467f-160">使用此节点可以指定多个值的名称和描述。</span><span class="sxs-lookup"><span data-stu-id="6467f-160">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="6467f-161">请注意，枚举值的说明不显示在该 cmdlet 显示的任何默认帮助视图中 `Get-Help` ，但其他帮助查看器可能会在其视图中显示此内容。</span><span class="sxs-lookup"><span data-stu-id="6467f-161">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="6467f-162">下面的 XML 演示 `<dev:possibleValues>` 具有两个指定值的节点。</span><span class="sxs-lookup"><span data-stu-id="6467f-162">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```
