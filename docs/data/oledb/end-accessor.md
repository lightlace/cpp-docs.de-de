---
title: "END_ACCESSOR"
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
  - "END_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_ACCESSOR-Makro"
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# END_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert das Ende eines Accessoreintrags.  
  
## Syntax  
  
```  
  
END_ACCESSOR( )  
  
```  
  
## Hinweise  
 Für mehrere Accessoren für ein Rowset, müssen Sie `BEGIN_ACCESSOR_MAP` angeben und das Makro `BEGIN_ACCESSOR` für jeden einzelnen Accessor verwenden.  Das Makro `BEGIN_ACCESSOR` wird mit dem Makro `END_ACCESSOR` abgeschlossen.  Das Makro `BEGIN_ACCESSOR_MAP` wird mit dem Makro `END_ACCESSOR_MAP` abgeschlossen.  
  
## Beispiel  
 Siehe [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)