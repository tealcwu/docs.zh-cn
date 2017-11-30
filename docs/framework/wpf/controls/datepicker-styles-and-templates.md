---
title: "包含 DatePicker 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fbe8a3935da2d9aa928467b4c64da455f3b53c5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="datepicker-styles-and-templates"></a><span data-ttu-id="9c406-102">包含 DatePicker 样式和模板</span><span class="sxs-lookup"><span data-stu-id="9c406-102">DatePicker Styles and Templates</span></span>
<span data-ttu-id="9c406-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.DatePicker>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DatePicker> control.</span></span> <span data-ttu-id="9c406-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9c406-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9c406-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="datepicker-parts"></a><span data-ttu-id="9c406-106">包含 DatePicker 部件</span><span class="sxs-lookup"><span data-stu-id="9c406-106">DatePicker Parts</span></span>  
 <span data-ttu-id="9c406-107">下表列出的命名的部件<xref:System.Windows.Controls.DatePicker>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-107">The following table lists the named parts for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
|<span data-ttu-id="9c406-108">部件</span><span class="sxs-lookup"><span data-stu-id="9c406-108">Part</span></span>|<span data-ttu-id="9c406-109">类型</span><span class="sxs-lookup"><span data-stu-id="9c406-109">Type</span></span>|<span data-ttu-id="9c406-110">描述</span><span class="sxs-lookup"><span data-stu-id="9c406-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9c406-111">PART_Root</span><span class="sxs-lookup"><span data-stu-id="9c406-111">PART_Root</span></span>|<xref:System.Windows.Controls.Grid>|<span data-ttu-id="9c406-112">控件的根。</span><span class="sxs-lookup"><span data-stu-id="9c406-112">The root of the control.</span></span>|  
|<span data-ttu-id="9c406-113">PART_Button</span><span class="sxs-lookup"><span data-stu-id="9c406-113">PART_Button</span></span>|<xref:System.Windows.Controls.Button>|<span data-ttu-id="9c406-114">打开和关闭按钮<xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="9c406-114">The button that opens and closes the <xref:System.Windows.Controls.Calendar>.</span></span>|  
|<span data-ttu-id="9c406-115">PART_TextBox</span><span class="sxs-lookup"><span data-stu-id="9c406-115">PART_TextBox</span></span>|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|<span data-ttu-id="9c406-116">文本框中，您可以输入日期。</span><span class="sxs-lookup"><span data-stu-id="9c406-116">The text box that allows you to input a date.</span></span>|  
|<span data-ttu-id="9c406-117">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="9c406-117">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="9c406-118">弹出窗口<xref:System.Windows.Controls.DatePicker>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-118">The popup for the <xref:System.Windows.Controls.DatePicker> control.</span></span>|  
  
## <a name="datepicker-states"></a><span data-ttu-id="9c406-119">包含 DatePicker 状态</span><span class="sxs-lookup"><span data-stu-id="9c406-119">DatePicker States</span></span>  
 <span data-ttu-id="9c406-120">下表列出的可视状态<xref:System.Windows.Controls.DatePicker>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-120">The following table lists the visual states for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
|<span data-ttu-id="9c406-121">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="9c406-121">VisualState Name</span></span>|<span data-ttu-id="9c406-122">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="9c406-122">VisualStateGroup Name</span></span>|<span data-ttu-id="9c406-123">描述</span><span class="sxs-lookup"><span data-stu-id="9c406-123">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9c406-124">普通</span><span class="sxs-lookup"><span data-stu-id="9c406-124">Normal</span></span>|<span data-ttu-id="9c406-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c406-125">CommonStates</span></span>|<span data-ttu-id="9c406-126">默认状态。</span><span class="sxs-lookup"><span data-stu-id="9c406-126">The default state.</span></span>|  
|<span data-ttu-id="9c406-127">已禁用</span><span class="sxs-lookup"><span data-stu-id="9c406-127">Disabled</span></span>|<span data-ttu-id="9c406-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c406-128">CommonStates</span></span>|<span data-ttu-id="9c406-129"><xref:System.Windows.Controls.DatePicker>处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="9c406-129">The <xref:System.Windows.Controls.DatePicker> is disabled.</span></span>|  
|<span data-ttu-id="9c406-130">有效</span><span class="sxs-lookup"><span data-stu-id="9c406-130">Valid</span></span>|<span data-ttu-id="9c406-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c406-131">ValidationStates</span></span>|<span data-ttu-id="9c406-132">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="9c406-132">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9c406-133">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9c406-133">InvalidFocused</span></span>|<span data-ttu-id="9c406-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c406-134">ValidationStates</span></span>|<span data-ttu-id="9c406-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="9c406-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9c406-136">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9c406-136">InvalidUnfocused</span></span>|<span data-ttu-id="9c406-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c406-137">ValidationStates</span></span>|<span data-ttu-id="9c406-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9c406-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="datepickertextbox-parts"></a><span data-ttu-id="9c406-139">DatePickerTextBox 部件</span><span class="sxs-lookup"><span data-stu-id="9c406-139">DatePickerTextBox Parts</span></span>  
 <span data-ttu-id="9c406-140">下表列出的命名的部件<xref:System.Windows.Controls.Primitives.DatePickerTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-140">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.</span></span>  
  
|<span data-ttu-id="9c406-141">部件</span><span class="sxs-lookup"><span data-stu-id="9c406-141">Part</span></span>|<span data-ttu-id="9c406-142">类型</span><span class="sxs-lookup"><span data-stu-id="9c406-142">Type</span></span>|<span data-ttu-id="9c406-143">描述</span><span class="sxs-lookup"><span data-stu-id="9c406-143">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9c406-144">PART_Watermark</span><span class="sxs-lookup"><span data-stu-id="9c406-144">PART_Watermark</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="9c406-145">包含中的初始文本的元素<xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="9c406-145">The element that contains the initial text in the <xref:System.Windows.Controls.DatePicker>.</span></span>|  
|<span data-ttu-id="9c406-146">PART_ContentElement</span><span class="sxs-lookup"><span data-stu-id="9c406-146">PART_ContentElement</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="9c406-147">可以包含一个可见元素<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="9c406-147">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="9c406-148">文本<xref:System.Windows.Controls.TextBox>显示在此元素。</span><span class="sxs-lookup"><span data-stu-id="9c406-148">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="datepickertextbox-states"></a><span data-ttu-id="9c406-149">DatePickerTextBox 状态</span><span class="sxs-lookup"><span data-stu-id="9c406-149">DatePickerTextBox States</span></span>  
 <span data-ttu-id="9c406-150">下表列出的可视状态<xref:System.Windows.Controls.Primitives.DatePickerTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-150">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.</span></span>  
  
|<span data-ttu-id="9c406-151">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="9c406-151">VisualState Name</span></span>|<span data-ttu-id="9c406-152">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="9c406-152">VisualStateGroup Name</span></span>|<span data-ttu-id="9c406-153">描述</span><span class="sxs-lookup"><span data-stu-id="9c406-153">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9c406-154">普通</span><span class="sxs-lookup"><span data-stu-id="9c406-154">Normal</span></span>|<span data-ttu-id="9c406-155">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c406-155">CommonStates</span></span>|<span data-ttu-id="9c406-156">默认状态。</span><span class="sxs-lookup"><span data-stu-id="9c406-156">The default state.</span></span>|  
|<span data-ttu-id="9c406-157">已禁用</span><span class="sxs-lookup"><span data-stu-id="9c406-157">Disabled</span></span>|<span data-ttu-id="9c406-158">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c406-158">CommonStates</span></span>|<span data-ttu-id="9c406-159"><xref:System.Windows.Controls.Primitives.DatePickerTextBox>处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="9c406-159">The <xref:System.Windows.Controls.Primitives.DatePickerTextBox> is disabled.</span></span>|  
|<span data-ttu-id="9c406-160">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9c406-160">MouseOver</span></span>|<span data-ttu-id="9c406-161">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c406-161">CommonStates</span></span>|<span data-ttu-id="9c406-162">鼠标指针置于<xref:System.Windows.Controls.Primitives.DatePickerTextBox>。</span><span class="sxs-lookup"><span data-stu-id="9c406-162">The mouse pointer is positioned over the <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span></span>|  
|<span data-ttu-id="9c406-163">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="9c406-163">ReadOnly</span></span>|<span data-ttu-id="9c406-164">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c406-164">CommonStates</span></span>|<span data-ttu-id="9c406-165">用户不能更改中的文本<xref:System.Windows.Controls.Primitives.DatePickerTextBox>。</span><span class="sxs-lookup"><span data-stu-id="9c406-165">The user cannot change the text in the <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span></span>|  
|<span data-ttu-id="9c406-166">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="9c406-166">Focused</span></span>|<span data-ttu-id="9c406-167">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9c406-167">FocusStates</span></span>|<span data-ttu-id="9c406-168">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="9c406-168">The control has focus.</span></span>|  
|<span data-ttu-id="9c406-169">失去焦点</span><span class="sxs-lookup"><span data-stu-id="9c406-169">Unfocused</span></span>|<span data-ttu-id="9c406-170">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9c406-170">FocusStates</span></span>|<span data-ttu-id="9c406-171">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9c406-171">The control does not have focus.</span></span>|  
|<span data-ttu-id="9c406-172">打水印</span><span class="sxs-lookup"><span data-stu-id="9c406-172">Watermarked</span></span>|<span data-ttu-id="9c406-173">WatermarkStates</span><span class="sxs-lookup"><span data-stu-id="9c406-173">WatermarkStates</span></span>|<span data-ttu-id="9c406-174">该控件将显示其初始文本。</span><span class="sxs-lookup"><span data-stu-id="9c406-174">The control displays its initial text.</span></span>  <span data-ttu-id="9c406-175"><xref:System.Windows.Controls.Primitives.DatePickerTextBox>处于状态，当用户不具有输入文本或选择日期。</span><span class="sxs-lookup"><span data-stu-id="9c406-175">The <xref:System.Windows.Controls.Primitives.DatePickerTextBox> is in the state when the user has not entered text or selected a date.</span></span>|  
|<span data-ttu-id="9c406-176">Unwatermarked</span><span class="sxs-lookup"><span data-stu-id="9c406-176">Unwatermarked</span></span>|<span data-ttu-id="9c406-177">WatermarkStates</span><span class="sxs-lookup"><span data-stu-id="9c406-177">WatermarkStates</span></span>|<span data-ttu-id="9c406-178">用户输入到文本<xref:System.Windows.Controls.Primitives.DatePickerTextBox>或中选择了日期<xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="9c406-178">The user has entered text into the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> or selected a date in the <xref:System.Windows.Controls.DatePicker>.</span></span>|  
|<span data-ttu-id="9c406-179">有效</span><span class="sxs-lookup"><span data-stu-id="9c406-179">Valid</span></span>|<span data-ttu-id="9c406-180">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c406-180">ValidationStates</span></span>|<span data-ttu-id="9c406-181">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="9c406-181">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9c406-182">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9c406-182">InvalidFocused</span></span>|<span data-ttu-id="9c406-183">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c406-183">ValidationStates</span></span>|<span data-ttu-id="9c406-184"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="9c406-184">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9c406-185">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9c406-185">InvalidUnfocused</span></span>|<span data-ttu-id="9c406-186">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c406-186">ValidationStates</span></span>|<span data-ttu-id="9c406-187"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9c406-187">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="datepicker-controltemplate-example"></a><span data-ttu-id="9c406-188">包含 DatePicker ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="9c406-188">DatePicker ControlTemplate Example</span></span>  
 <span data-ttu-id="9c406-189">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.DatePicker>控件。</span><span class="sxs-lookup"><span data-stu-id="9c406-189">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 <span data-ttu-id="9c406-190">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="9c406-190">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9c406-191">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="9c406-191">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c406-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c406-192">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="9c406-193">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="9c406-193">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="9c406-194">控件自定义</span><span class="sxs-lookup"><span data-stu-id="9c406-194">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="9c406-195">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="9c406-195">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="9c406-196">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="9c406-196">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)