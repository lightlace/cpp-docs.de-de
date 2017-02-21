---
title: "CDynamicStringAccessorW-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessorW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessorW-Klasse"
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicStringAccessorW-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht Ihnen, auf eine Datenquelle zuzugreifen, wenn Ihnen das Datenbankschema \(die zugrunde liegende Struktur\).  
  
## Syntax  
  
```  
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## Hinweise  
 Sie beide Anforderung, dass der Anbieterabruf alle Daten, die vom Datenspeicher als Zeichenfolgendaten, jedoch Zugriff werden, `CDynamicStringAccessor` Unicode\-Zeichenfolgen\-Daten erfordert.  
  
 `CDynamicStringAccessorW` erbt **GetString** und `SetString` von `CDynamicStringAccessor`.  Wenn Sie verwenden, gelten diese Methoden in `CDynamicStringAccessorW`, ***BaseType*** ist **WCHAR** ein.  
  
## Anforderungen  
 **Header**: atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor\-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor\-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor\-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)