---
title: "duration_values-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::duration_values"
dev_langs: 
  - "C++"
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# duration_values-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt bestimmte Werte für den Vorlagenparameter [duration](../standard-library/duration-class.md)`Rep` bereit.  
  
## Syntax  
  
```  
template<class Rep>  
   struct duration_values;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[duration\_values::max\-Methode](../Topic/duration_values::max%20Method.md)|Statisch  Gibt die Obergrenze für einen Wert des Typs `Rep` an.|  
|[duration\_values::min\-Methode](../Topic/duration_values::min%20Method.md)|Statisch  Gibt die Untergrenze für einen Wert des Typs `Rep` an.|  
|[duration\_values::zero\-Methode](../Topic/duration_values::zero%20Method.md)|Statisch  Gibt `Rep(0)` zurück.|  
  
## Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)