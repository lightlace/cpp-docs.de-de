---
title: "unique_lock-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::unique_lock"
dev_langs: 
  - "C++"
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# unique_lock-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine Vorlage dar, die instanziiert werden kann, um Objekte zu erstellen, die die Sperre und das Entsperren von `mutex` verwalten.  
  
## Syntax  
  
```  
template<class Mutex>  
class unique_lock;  
```  
  
## Hinweise  
 Das Vorlagenargument `Mutex` muss einen *Mutextyp* benennen.  
  
 Wird intern speichert `unique_lock` einen Zeiger auf einen zugeordneten Objekt `mutex` und `bool`, das angibt, ob der aktuelle Thread `mutex` besitzt.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`unique_lock::mutex_type`|Synonym für das Vorlagenargument `Mutex`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[unique\_lock::unique\_lock\-Konstruktor](../Topic/unique_lock::unique_lock%20Constructor.md)|Erstellt ein `unique_lock`\-Objekt.|  
|[unique\_lock::~unique\_lock\-Destruktor](../Topic/unique_lock::~unique_lock%20Destructor.md)|Gibt alle Ressourcen freigeben, die mit dem `unique_lock`\-Objekt zugeordnet werden.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[unique\_lock::lock\-Methode](../Topic/unique_lock::lock%20Method.md)|Blockiert den aufrufenden Thread, bis der Thread den Besitz zugeordneten `mutex` abruft.|  
|[unique\_lock::mutex\-Methode](../Topic/unique_lock::mutex%20Method.md)|Ruft den gespeicherten Zeiger zu zugeordneten `mutex` ab.|  
|[unique\_lock::owns\_lock\-Methode](../Topic/unique_lock::owns_lock%20Method.md)|Gibt an, dass der aufrufende Thread zugeordnete `mutex` besitzt.|  
|[unique\_lock::release\-Methode](../Topic/unique_lock::release%20Method.md)|Hebt `unique_lock` des Objekts vom zugeordneten `mutex`\-Objekt die Zuordnung.|  
|[unique\_lock::swap\-Methode](../Topic/unique_lock::swap%20Method.md)|Vertauscht zugeordnete `mutex` und den Besitzstatus mit dem eines bestimmten Objekts aus.|  
|[unique\_lock::try\_lock\-Methode](../Topic/unique_lock::try_lock%20Method.md)|Versucht, ohne Blockierung in den Besitz des verknüpften `mutex` zu gelangen.|  
|[unique\_lock::try\_lock\_for\-Methode](../Topic/unique_lock::try_lock_for%20Method.md)|Versucht, ohne Blockierung in den Besitz des verknüpften `mutex` zu gelangen.|  
|[unique\_lock::try\_lock\_until\-Methode](../Topic/unique_lock::try_lock_until%20Method.md)|Versucht, ohne Blockierung in den Besitz des verknüpften `mutex` zu gelangen.|  
|[unique\_lock::unlock\-Methode](../Topic/unique_lock::unlock%20Method.md)|Gibt Besitz zugeordneten `mutex`.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[unique\_lock::operator bool Operator](../Topic/unique_lock::operator%20bool%20Operator.md)|Gibt an, dass der aufrufende Thread Besitz zugeordneten `mutex`.|  
|[unique\_lock::operator\= Operator](../Topic/unique_lock::operator=%20Operator.md)|Kopiert der gespeicherten `mutex` Zeiger und den zugeordneten Besitzstatus von einem angegebenen Objekt.|  
  
## Vererbungshierarchie  
 `unique_lock`  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)