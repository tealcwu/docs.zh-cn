---
title: "如何：确定 Windows 窗体 StatusBar 控件中被单击的面板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a91ad8c28bae7d517a9e13937d5de340b1b6a605
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>如何：确定 Windows 窗体 StatusBar 控件中被单击的面板
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip>和<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性和将来使用，如果你选择。  
  
 到程序[StatusBar 控件](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)控件以响应用户单击时，请使用 case 语句中的<xref:System.Windows.Forms.StatusBar.PanelClick>事件。 该事件包含的自变量 （面板参数），其中包含对被单击的引用<xref:System.Windows.Forms.StatusBarPanel>。 使用此引用，可以确定被单击的面板的索引，并相应地进行编程。  
  
> [!NOTE]
>  确保<xref:System.Windows.Forms.StatusBar>控件的<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`true`。  
  
### <a name="to-determine-which-panel-was-clicked"></a>若要确定被单击的面板  
  
1.  在<xref:System.Windows.Forms.StatusBar.PanelClick>事件处理程序中，使用`Select Case`(在[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]) 或`switch case`([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]或[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 语句，以确定哪个面板被单击通过检查事件自变量中被单击的面板的索引。  
  
     下面的代码示例要求是否存在，请在窗体上的<xref:System.Windows.Forms.StatusBar>控件， `StatusBar1`，和两个<xref:System.Windows.Forms.StatusBarPanel>对象，`StatusBarPanel1`和`StatusBarPanel2`。  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)][!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [如何：设置状态栏面板的大小](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [演练：在运行时更新状态栏信息](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [StatusBar 控件概述](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
