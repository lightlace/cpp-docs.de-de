---
title: "future-Klasse"
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
  - "future/std::future"
dev_langs: 
  - "C++"
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# future-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein *asynchrones Rückgebeobjekt*.  
  
## Syntax  
  
```  
template<class Ty>  
class future;  
```  
  
## Hinweise  
 Jeder *asynchrone StandardAnbieter* gibt ein Objekt zurück, dessen Typ eine Instanziierung dieser Vorlage ist.  Ein `future`\-Objekt stellt den Zugriff zum asynchronen einzigen Anbieter, dass es zugeordnet ist.  Wenn Sie mehrere asynchrone erfordern Objekte zurückgibt, die demselben asynchronen Anbieter zugeordnet werden, kopieren Sie das `future`\-Objekt an ein [shared\_future](../standard-library/shared-future-class.md)\-Objekt.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[future::future\-Konstruktor](../Topic/future::future%20Constructor.md)|Erstellt ein `future`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[future::get\-Methode](../Topic/future::get%20Method.md)|Ruft das Ergebnis, das im zugeordneten asynchronen Zustand gespeichert wird.|  
|[future::share\-Methode](../Topic/future::share%20Method.md)|Konvertiert das Objekt auf `shared_future`.|  
|[future::valid\-Methode](../Topic/future::valid%20Method.md)|Gibt an, ob das Objekt nicht leer ist.|  
|[future::wait\-Methode](../Topic/future::wait%20Method.md)|Blockiert den aktuellen Thread, bis der asynchrone zugeordnete Zustand bereit ist.|  
|[future::wait\_for\-Methode](../Topic/future::wait_for%20Method.md)|Blöcke auf den zugeordneten Zustand asynchronen ist bereit, oder bis die angegebene Zeit abgelaufen ist.|  
|[future::wait\_until\-Methode](../Topic/future::wait_until%20Method.md)|Blöcke auf die entsprechenden asynchronen Zustand befindet oder zu einem angegebenen Zeitpunkt bereit.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[future::operator\= Operator](../Topic/future::operator=%20Operator.md)|Überträgt asynchronen den zugeordneten Zustand von einem angegebenen Objekt.|  
  
## Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)