---
title: "CRestrictions-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL::CRestrictions"
  - "CRestrictions"
  - "ATL.CRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRestrictions-Klasse"
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine generische Klasse, die ermöglicht, um Einschränkungen für Schemarowsets anzugeben.  
  
## Syntax  
  
```  
template <   
   class T,   
   short nRestrictions,   
   const GUID* pguid   
>  
class CRestrictions : public CSchemaRowset <   
   T,   
   nRestrictions   
>  
```  
  
#### Parameter  
 `T`  
 Die Klasse wird für der Accessor.  
  
 `nRestrictions`  
 Die Anzahl der Beschränkungsspalten für das zu unterstützende Schemarowset.  
  
 `pguid`  
 Ein Zeiger der GUID für das Schema.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Öffnen](../../data/oledb/crestrictions-open.md)|Gibt ein Resultset entsprechend den vom Benutzer bereitgestellten Einschränkungen zurück.|  
  
## Anforderungen  
 **Header:**  atldbsch.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)