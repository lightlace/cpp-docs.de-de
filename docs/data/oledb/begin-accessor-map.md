---
title: "BEGIN_ACCESSOR_MAP"
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
  - "BEGIN_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR_MAP-Makro"
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert den Beginn der Accessor\-Zuordnungseinträge.  
  
## Syntax  
  
```  
  
BEGIN_ACCESSOR_MAP(  
x  
,   
num  
 )  
  
```  
  
#### Parameter  
 *w*  
 \[in\] Der Name der Benutzerdatensatzklasse.  
  
 *num*  
 \[in\] Die Anzahl der Accessoren in dieser Accessorzuordnung.  
  
## Hinweise  
 Bei mehreren Accessoren für ein Rowset, müssen Sie `BEGIN_ACCESSOR_MAP` am Anfang angeben und das `BEGIN_ACCESSOR`\-Makro für jeden einzelnen Accessor verwenden. Das `BEGIN_ACCESSOR`\-Makro wird mit dem `END_ACCESSOR`\-Makro abgeschlossen. Die Accessorzuordnung wird mit dem `END_ACCESSOR_MAP`\-Makro abgeschlossen.  
  
 Wenn es nur einen Accessor im Benutzerdatensatz gibt, verwenden Sie das Makro [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md).  
  
## Beispiel  
 [!CODE [NVC_OLEDB_Consumer#15](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#15)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)