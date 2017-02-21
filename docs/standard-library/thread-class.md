---
title: "thread-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "thread/std::thread"
dev_langs: 
  - "C++"
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# thread-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads innerhalb einer Anwendung verwendet wird.  
  
## Syntax  
  
```  
class thread;  
```  
  
## Hinweise  
 Sie können ein `thread`\-Objekt zum Überwachen und Verwalten eines Ausführungsthreads innerhalb einer Anwendung verwenden.  Ein Threadobjekt, das mithilfe eines Standardkonstruktors erstellt wird, ist keinem Ausführungsthread zugeordnet.  Mit einem Threadobjekt, das mithilfe eines aufrufbaren Objekts erstellt wird, wird ein neuer Ausführungsthread erstellt, und das aufrufbare Objekt in diesem Thread wird aufgerufen.  Threadobjekte können verschoben aber nicht kopiert werden.  Daher kann ein Ausführungsthread nur einem Threadobjekt zugeordnet werden.  
  
 Jeder Ausführungsthread besitzt einen eindeutigen Bezeichner des Typs `thread::id`.  Die `this_thread::get_id`\-Funktion gibt den Bezeichner des aufrufenden Threads zurück.  Die `thread::get_id`\-Memberfunktion gibt den Bezeichner des von einem Threadobjekt verwalteten Threads zurück.  Ein nach Standard erstelltes Threadobjekt gibt die `thread::get_id`\-Methode ein Objekt zurück, das über einen Wert verfügt, der für alle nach Standard erstellten Threadobjekte gleich ist und sich von dem von `this_thread::get_id` zurückgegebenen Wert für jeden Ausführungsthread, der zum Zeitpunkt des Aufrufs verknüpft werden kann, unterschiedet.  
  
## Member  
  
### Öffentliche Klassen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[thread::id\-Klasse](../Topic/thread::id%20Class.md)|Identifiziert den zugeordneten Thread eindeutig.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[thread::thread\-Konstruktor](../Topic/thread::thread%20Constructor.md)|Erstellt ein `thread`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[thread::detach\-Methode](../Topic/thread::detach%20Method.md)|Trennt den zugeordneten Thread vom `thread`\-Objekt.|  
|[thread::get\_id\-Methode](../Topic/thread::get_id%20Method.md)|Gibt den eindeutigen Bezeichner des zugeordneten Threads zurück.|  
|[thread::hardware\_concurrency\-Methode](../Topic/thread::hardware_concurrency%20Method.md)|Statisch  Gibt eine Schätzung der Anzahl von Hardwarethreadkontexten zurück.|  
|[thread::join\-Methode](../Topic/thread::join%20Method.md)|Blockiert, bis der zugeordnete Thread abgeschlossen ist.|  
|[thread::joinable\-Methode](../Topic/thread::joinable%20Method.md)|Gibt an, ob dem zugehörigen Thread beigetreten werden kann.|  
|[thread::native\_handle\-Methode](../Topic/thread::native_handle%20Method.md)|Gibt den implementierungsspezifischen Typ zurück, der das Threadhandle darstellt.|  
|[thread::swap\-Methode](../Topic/thread::swap%20Method.md)|Tauscht den Objektzustand mit einem angegebenen `thread`\-Objekt aus.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[thread::operator\= Operator](../Topic/thread::operator=%20Operator.md)|Weist einem Thread das aktuelle `thread`\-Objekt zu.|  
  
## Anforderungen  
 **Header:** thread  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread\>](../standard-library/thread.md)