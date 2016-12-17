---
title: "shared_future-Klasse"
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
  - "future/std::shared_future"
dev_langs: 
  - "C++"
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# shared_future-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein *asynchrones Rückgebeobjekt*.  Im Gegensatz zu [Zukunft](../standard-library/future-class.md) einem Objekt kann ein *asynchroner Anbieter* mit beliebig vielen `shared_future`\-Objekten zugeordnet sind.  
  
## Syntax  
  
```  
template<class Ty>  
class shared_future;  
```  
  
## Hinweise  
 Rufen Sie keine Methoden außer `valid`, `operator=` und Destruktor auf einem `shared_future`\-Objekt auf, das *leer* ist.  
  
 `shared_future`\-Objekte werden nicht synchronisiert.  Aufrufen von Methoden auf das gleiche Objekt von mehreren Threads stellt ein Datenrennen, das vor unvorhersehbare Ergebnisse hat.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[shared\_future::shared\_future\-Konstruktor](../Topic/shared_future::shared_future%20Constructor.md)|Erstellt ein `shared_future`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[shared\_future::get\-Methode](../Topic/shared_future::get%20Method.md)|Ruft das Ergebnis, das im *zugeordneten asynchronen Zustand* gespeichert wird.|  
|[shared\_future::valid\-Methode](../Topic/shared_future::valid%20Method.md)|Gibt an, ob das Objekt nicht leer ist.|  
|[shared\_future::wait\-Methode](../Topic/shared_future::wait%20Method.md)|Blockiert den aktuellen Thread, bis der asynchrone zugeordnete Zustand bereit ist.|  
|[shared\_future::wait\_for\-Methode](../Topic/shared_future::wait_for%20Method.md)|Blöcke auf den zugeordneten Zustand asynchronen ist bereit, oder bis die angegebene Zeit abgelaufen ist.|  
|[shared\_future::wait\_until\-Methode](../Topic/shared_future::wait_until%20Method.md)|Blöcke auf die entsprechenden asynchronen Zustand befindet oder zu einem angegebenen Zeitpunkt bereit.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[shared\_future::operator\= Operator](../Topic/shared_future::operator=%20Operator.md)|Weist einen neuen asynchronen zugeordneten Zustand zu.|  
  
## Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)