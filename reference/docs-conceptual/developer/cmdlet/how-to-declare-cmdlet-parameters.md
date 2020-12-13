---
ms.date: 09/13/2016
ms.topic: reference
title: 如何声明 Cmdlet 参数
description: 如何声明 Cmdlet 参数
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667090"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="aad31-103">如何声明 Cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="aad31-103">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="aad31-104">这些示例演示如何声明命名、位置、必需、可选参数和开关参数。</span><span class="sxs-lookup"><span data-stu-id="aad31-104">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="aad31-105">这些示例还演示如何定义参数别名。</span><span class="sxs-lookup"><span data-stu-id="aad31-105">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="aad31-106">如何声明命名参数</span><span class="sxs-lookup"><span data-stu-id="aad31-106">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="aad31-107">定义公共属性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="aad31-107">Define a public property as shown in the following code.</span></span> <span data-ttu-id="aad31-108">添加参数特性时，请 `Position` 从特性中省略关键字。</span><span class="sxs-lookup"><span data-stu-id="aad31-108">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="aad31-109">有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aad31-109">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="aad31-110">如何声明位置参数</span><span class="sxs-lookup"><span data-stu-id="aad31-110">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="aad31-111">定义公共属性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="aad31-111">Define a public property as shown in the following code.</span></span> <span data-ttu-id="aad31-112">添加参数特性时，请将关键字设置 `Position` 为参数位置。</span><span class="sxs-lookup"><span data-stu-id="aad31-112">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="aad31-113">值0指示第一个位置。</span><span class="sxs-lookup"><span data-stu-id="aad31-113">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="aad31-114">有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aad31-114">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="aad31-115">如何声明必需参数</span><span class="sxs-lookup"><span data-stu-id="aad31-115">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="aad31-116">定义公共属性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="aad31-116">Define a public property as shown in the following code.</span></span> <span data-ttu-id="aad31-117">添加参数特性时，请将关键字设置 `Mandatory` 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="aad31-117">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="aad31-118">有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aad31-118">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="aad31-119">如何声明可选参数</span><span class="sxs-lookup"><span data-stu-id="aad31-119">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="aad31-120">定义公共属性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="aad31-120">Define a public property as shown in the following code.</span></span> <span data-ttu-id="aad31-121">添加参数属性时，请省略 `Mandatory` 关键字。</span><span class="sxs-lookup"><span data-stu-id="aad31-121">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="aad31-122">如何声明开关参数</span><span class="sxs-lookup"><span data-stu-id="aad31-122">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="aad31-123">将公共属性定义为 [SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)类型，然后声明参数属性。</span><span class="sxs-lookup"><span data-stu-id="aad31-123">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="aad31-124">有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aad31-124">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="aad31-125">如何使用别名声明参数</span><span class="sxs-lookup"><span data-stu-id="aad31-125">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="aad31-126">定义公共属性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="aad31-126">Define a public property as shown in the following code.</span></span> <span data-ttu-id="aad31-127">添加一个别名属性，其中列出了参数的别名。</span><span class="sxs-lookup"><span data-stu-id="aad31-127">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="aad31-128">在此示例中，为同一参数定义了三个别名。</span><span class="sxs-lookup"><span data-stu-id="aad31-128">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="aad31-129">第一个别名提供快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aad31-129">The first alias provides a shortcut.</span></span> <span data-ttu-id="aad31-130">第二个和第三个别名提供了可用于不同方案的名称。</span><span class="sxs-lookup"><span data-stu-id="aad31-130">The second and third aliases provide names you can use for different scenarios.</span></span>

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="aad31-131">有关 Alias 特性的详细信息，请参阅 [Alias 特性声明](./alias-attribute-declaration.md)。</span><span class="sxs-lookup"><span data-stu-id="aad31-131">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aad31-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aad31-132">See Also</span></span>

[<span data-ttu-id="aad31-133">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="aad31-133">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="aad31-134">参数属性声明</span><span class="sxs-lookup"><span data-stu-id="aad31-134">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="aad31-135">别名属性声明</span><span class="sxs-lookup"><span data-stu-id="aad31-135">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="aad31-136">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aad31-136">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
