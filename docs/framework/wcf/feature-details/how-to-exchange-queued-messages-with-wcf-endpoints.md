---
title: "如何：使用 WCF 终结点交换排队消息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 975c5ea5d5b3ab81d37b713e84f273e4c2c1c0b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a>如何：使用 WCF 终结点交换排队消息
即使在通信时 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务不可用，队列也能确保客户端和该服务之间的可靠消息传输。 下面的过程演示如何在实现 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时使用标准排队绑定确保客户端和服务间的持久性通信。  
  
 本节介绍如何将 <xref:System.ServiceModel.NetMsmqBinding> 用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务之间的排队通信。  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>在 WCF 服务中使用队列  
  
1.  使用用 <xref:System.ServiceModel.ServiceContractAttribute> 标记的接口定义服务协定。 用 <xref:System.ServiceModel.OperationContractAttribute> 来标记属于服务协定一部分的接口中的操作，并将它们指定为单向操作（因为不返回对该方法的任何响应）。 下面的代码提供了示例服务协定及其操作定义。  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  当服务协定传递用户定义的类型时，您必须为这些类型定义数据协定。 下面的代码演示了两个数据协定，`PurchaseOrder` 和 `PurchaseOrderLineItem`。 这两种类型定义了发送给服务的数据。 （请注意，定义该数据协定的类也定义了大量方法。 这些方法不被视为数据协定的一部分。 只有那些使用 `DataMember` 属性声明的成员才是数据协定的一部分。）  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  实现在类中接口中定义的服务协定的方法。  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     请注意放置在 <xref:System.ServiceModel.OperationBehaviorAttribute> 方法上的 `SubmitPurchaseOrder`。 它指定了必须在某个事务内调用此操作，且当方法完成后，该事务会自动完成。  
  
4.  使用 <xref:System.Messaging> 创建一个事务性队列。 可以选择使用 Microsoft 消息队列 (MSMQ) Microsoft 管理控制台 (MMC) 来创建队列。 如果这样，将确保创建事务性队列。  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  在指定服务地址并使用标准 <xref:System.ServiceModel.Description.ServiceEndpoint> 绑定的配置中定义 <xref:System.ServiceModel.NetMsmqBinding>。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]使用[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]配置，请参阅[配置 Windows Communication Foundation 应用程序](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a)。  
  
  
  
6.  使用 `OrderProcessing` 为 <xref:System.ServiceModel.ServiceHost> 服务创建一个主机，该主机从队列读取消息并处理这些消息。 打开服务主机使服务处于可用状态。 显示一条消息，告知用户按任何键以终止服务。 调用 `ReadLine` 等待按键，然后关闭服务。  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>为排队服务创建客户端  
  
1.  下面的示例演示如何运行主机应用程序并使用 Svcutil.exe 工具创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端。  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  在配置中定义 <xref:System.ServiceModel.Description.ServiceEndpoint>，指定地址并使用标准 <xref:System.ServiceModel.NetMsmqBinding> 绑定，如下面的示例所示。  
  
  
  
3.  创建一个事务范围，以写入事务性队列，调用 `SubmitPurchaseOrder` 操作并关闭 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端，如下面的示例所示。  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>示例  
 下面的示例演示了服务代码、主机应用程序、App.config 文件以及为此示例包含的客户端代码。  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [已进行事务处理的 MSMQ 绑定](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [在 WCF 中排队](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [如何：与 WCF 终结点和消息队列应用程序交换消息](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [Windows Communication Foundation 到消息队列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [安装消息队列 (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [消息队列集成绑定示例](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [到 Windows Communication Foundation 的消息队列](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [基于消息队列的消息安全性](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
