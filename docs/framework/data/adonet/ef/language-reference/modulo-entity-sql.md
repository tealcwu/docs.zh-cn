---
title: "（取模）（实体 SQL）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a04b2972c80aff654331aeb319390b6f817374bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="modulo-entity-sql"></a>（取模）（实体 SQL）
返回两个表达式相除后的余数。  
  
## <a name="syntax"></a>语法  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a>自变量  
 `dividend`  
 被除数的数值表达式。 `dividend` 为任何一种数值数据类型的任何有效表达式。  
  
 `divisor`  
 除数的数值表达式。 `divisor` 为任何一种数值数据类型的任何有效表达式。  
  
## <a name="result-types"></a>结果类型  
 Edm.Int32  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 % 算数运算符以返回两个表达式相除后的余数。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
