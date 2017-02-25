---
title: "max_variable_size-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::max_variable_size"
  - "allocators/stdext::max_variable_size"
  - "stdext.max_variable_size"
  - "max_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_variable_size-Klasse"
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# max_variable_size-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt eine [Klasse Max.](../standard-library/allocators-header.md) Objekts, beschränkt eine [Freelist](../standard-library/freelist-class.md) zugeordnete Objekt auf eine maximale Länge, die etwa proportional zur Anzahl von Speicherblöcken.  
  
## Syntax  
  
```  
class max_variable_size  
```  
  
### Konstruktoren  
  
|||  
|-|-|  
|[max\_variable\_size](../Topic/max_variable_size::max_variable_size.md)|Konstruiert ein Objekt vom Typ `max_variable_size`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[reserviert](../Topic/max_variable_size::allocated.md)|Erhöht die Anzahl der reservierten Speicherblöcke.|  
|[die Zuordnung aufgehoben](../Topic/max_variable_size::deallocated.md)|Verringert die Anzahl der reservierten Speicherblöcke.|  
|[full](../Topic/max_variable_size::full.md)|Gibt einen Wert, der angibt, ob die Liste der freien Blöcke mit mehr Arbeitsspeicher hinzugefügt werden soll.|  
|[freigegeben](../Topic/max_variable_size::released.md)|Verringert die Anzahl der Arbeitsspeicher bei der Freiliste blockiert.|  
|[gespeichert](../Topic/max_variable_size::saved.md)|Erhöht die Anzahl der zur Liste freien Speicherblöcke.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)