---
title: "max_unbounded-Klasse"
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
  - "allocators/stdext::max_unbounded"
  - "stdext::max_unbounded"
  - "stdext.max_unbounded"
  - "max_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_unbounded-Klasse"
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 18
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# max_unbounded-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt eine [Klasse Max.](../standard-library/allocators-header.md) \-Objekt, das nicht die maximale Länge des begrenzt ein [Freelist](../standard-library/freelist-class.md) Objekt.  
  
## Syntax  
  
```  
class max_unbounded  
```  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[reserviert](../Topic/max_unbounded::allocated.md)|Erhöht die Anzahl der reservierten Speicherblöcke.|  
|[die Zuordnung aufgehoben](../Topic/max_unbounded::deallocated.md)|Verringert die Anzahl der reservierten Speicherblöcke.|  
|[full](../Topic/max_unbounded::full.md)|Gibt einen Wert, der angibt, ob die Liste der freien Blöcke mit mehr Arbeitsspeicher hinzugefügt werden soll.|  
|[freigegeben](../Topic/max_unbounded::released.md)|Verringert die Anzahl der Arbeitsspeicher bei der Freiliste blockiert.|  
|[gespeichert](../Topic/max_unbounded::saved.md)|Erhöht die Anzahl der zur Liste freien Speicherblöcke.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)