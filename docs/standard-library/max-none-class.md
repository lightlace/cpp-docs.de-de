---
title: "max_none-Klasse"
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
  - "max_none"
  - "stdext::max_none"
  - "stdext.max_none"
  - "allocators/stdext::max_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_none-Klasse"
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# max_none-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt eine [Klasse Max.](../standard-library/allocators-header.md) Objekts, beschränkt eine [Freelist](../standard-library/freelist-class.md) Objekt, das eine maximale Länge von 0 \(null\).  
  
## Syntax  
  
```  
template <std::size_t Max> class max_none  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Max`|Die max\-Klasse, die bestimmt die maximale Anzahl von Elementen zum Speichern in der `freelist`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[reserviert](../Topic/max_none::allocated.md)|Erhöht die Anzahl der reservierten Speicherblöcke.|  
|[die Zuordnung aufgehoben](../Topic/max_none::deallocated.md)|Verringert die Anzahl der reservierten Speicherblöcke.|  
|[full](../Topic/max_none::full.md)|Gibt einen Wert, der angibt, ob die Liste der freien Blöcke mit mehr Arbeitsspeicher hinzugefügt werden soll.|  
|[freigegeben](../Topic/max_none::released.md)|Verringert die Anzahl der Arbeitsspeicher bei der Freiliste blockiert.|  
|[gespeichert](../Topic/max_none::saved.md)|Erhöht die Anzahl der zur Liste freien Speicherblöcke.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)