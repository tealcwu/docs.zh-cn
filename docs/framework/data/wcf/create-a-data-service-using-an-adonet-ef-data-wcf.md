---
title: "如何：使用 ADO.NET 实体框架数据源创建数据服务（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9362aa6ea02f5878d2419ee7cbaab349cae27038
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>如何：使用 ADO.NET 实体框架数据源创建数据服务（WCF 数据服务）
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 将实体数据作为数据服务公开。 如果数据源为关系数据库，则此实体数据是由 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]提供的。 本主题介绍如何在基于现有数据库的 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Web 应用程序中创建基于[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]的数据模型，以及如何使用此数据模型创建新的数据服务。  
  
 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]还提供了一个可以在 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 项目外部生成[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]模型的命令行工具。 有关详细信息，请参阅[如何： 使用 EdmGen.exe 生成模型和映射文件](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>将基于现有数据库的实体框架模型添加到现有 Web 应用程序  
  
1.  上**项目**菜单上，单击**添加新项**。  
  
2.  在**模板**窗格中，单击**数据**类别，，然后选择**ADO.NET 实体数据模型**。  
  
3.  键入模型名称，然后单击**添加**。  
  
     将显示“[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]向导”的第一页。  
  
4.  在**选择模型内容**对话框中，选择**从数据库生成**。 然后，单击 **“下一步”**。  
  
5.  单击**新连接**按钮。  
  
6.  在**连接属性**对话框中，键入你的服务器名称，选择身份验证方法，键入数据库名称，然后单击**确定**。  
  
     **选择你的数据连接**的对话框中更新你的数据库的连接设置。  
  
7.  确保**实体连接设置另存为 App.Config 中：**选中复选框。 然后，单击 **“下一步”**。  
  
8.  在**选择数据库对象**对话框中，选择的所有数据库对象你打算在数据服务中公开。  
  
    > [!NOTE]
    >  数据服务不自动公开数据模型中包含的对象。 它们必须由服务本身显式公开。 有关详细信息，请参阅[配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。  
  
9. 单击**完成**以完成向导。  
  
     这将基于特定数据库创建默认数据模型。 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]允许对数据模型进行自定义。 有关详细信息，请参阅[任务](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb)。  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>使用新数据模型创建数据服务  
  
1.  在 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 中，打开代表数据模型的 .edmx 文件。  
  
2.  在**模型浏览器**，右键单击模型，单击**属性**，然后记下实体容器的名称。  
  
3.  在**解决方案资源管理器**，右键单击的名称你[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目，，然后单击**添加新项**。  
  
4.  在**添加新项**对话框中，选择**WCF 数据服务**。  
  
5.  为该服务，提供一个名称，然后单击**确定**。  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 将为新服务创建 XML 标记和代码文件。 默认情况下，代码编辑器窗口将打开。  
  
6.  在数据服务代码中，将用于定义数据服务的类定义中的注释 `/* TODO: put your data source class name here */` 替换为从 <xref:System.Data.Objects.ObjectContext> 类继承且作为数据模型的实体容器的类型，如步骤 2 中所述。  
  
7.  在数据服务代码中，启用经过授权的客户端来访问数据服务公开的实体集。 有关详细信息，请参阅[创建数据服务](../../../../docs/framework/data/wcf/creating-the-data-service.md)。  
  
8.  若要通过使用 Web 浏览器测试 Northwind.svc 数据服务，请按照本主题中的说明[从 Web 浏览器访问服务](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)。  
  
## <a name="see-also"></a>请参阅  
 [定义 WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [数据服务提供程序](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [如何：使用反射提供程序创建数据服务](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [如何：使用 LINQ to SQL 数据源创建数据服务](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
