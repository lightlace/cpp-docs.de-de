---
title: "structured_task_group-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::structured_task_group"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "structured_task_group-Klasse"
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# structured_task_group-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `structured_task_group`\-Klasse stellt eine stark strukturierte Auflistung paralleler Arbeit dar.  Sie können einzelne parallele Aufgaben mithilfe von `task_handle`\-Objekten in eine `structured_task_group` stellen und warten, bis sie abgeschlossen werden, oder Sie können die Aufgabengruppe abbrechen, bevor deren Ausführung beendet wird, wodurch auch alle Aufgaben abgebrochen werden, deren Ausführung nicht gestartet wurde.  
  
## Syntax  
  
```  
class structured_task_group;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[structured\_task\_group::structured\_task\_group\-Konstruktor](../Topic/structured_task_group::structured_task_group%20Constructor.md)|Überladen.  Erstellt ein neues `structured_task_group`\-Objekt.|  
|[structured\_task\_group::~structured\_task\_group\-Destruktor](../Topic/structured_task_group::~structured_task_group%20Destructor.md)|Zerstört ein `structured_task_group`\-Objekt.  Von Ihnen wird erwartet, entweder die `wait`\-Methode oder `run_and_wait`\-Methode vor der Zerstörung des ausgeführten Destruktors für das Objekt aufzurufen, außer wenn der Destruktor als Ergebnis der Stapelentladung aufgrund einer Ausnahme ausgeführt wird.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[structured\_task\_group::cancel\-Methode](../Topic/structured_task_group::cancel%20Method.md)|Versucht bestmöglich, die Teilstruktur der Arbeit abzubrechen, die aus dieser Aufgabengruppe stammt.  Jede in der Aufgabengruppe geplante Aufgabe wird transitiv abgebrochen, wenn möglich.|  
|[structured\_task\_group::is\_canceling\-Methode](../Topic/structured_task_group::is_canceling%20Method.md)|Informiert den Aufrufer, ob die Aufgabengruppe gerade in der Mitte eines Abbruchs ist.  Dies gibt nicht notwendigerweise an, dass die `cancel`\-Methode für das `structured_task_group`\-Objekt aufgerufen wurde \(obwohl dies diese Methode bestimmt dazu qualifiziert, `true` zurückzugeben\).  Möglicherweise wird das `structured_task_group`\-Objekt inline ausführt, und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen.  In Fällen wie diesen, in denen die Laufzeit vorzeitig bestimmen kann, dass der Abbruch durch dieses `structured_task_group`\-Objekt fließen wird, wird außerdem `true` zurückgegeben.|  
|[structured\_task\_group::run\-Methode](../Topic/structured_task_group::run%20Method.md)|Überladen.  Plant eine Aufgabe für das `structured_task_group`\-Objekt.  Der Aufrufer verwaltet die Lebensdauer des `task_handle`\-Objekts, das im `_Task_handle`\-Parameter übergeben wurde.  Die Version, die den `_Placement`\-Parameter akzeptiert, durch die die Aufgabe, zum Ausführung am Speicherort beeinflusst werden, dass durch diesen Parameter angegeben.|  
|[structured\_task\_group::run\_and\_wait\-Methode](../Topic/structured_task_group::run_and_wait%20Method.md)|Überladen.  Plant eine Aufgabe, die mithilfe des `structured_task_group`\-Objekts für vollständige Abbruchunterstützung inline auf dem aufrufenden Kontext ausgeführt werden soll.  Wenn ein `task_handle`\-Objekt als Parameter an `run_and_wait` übergeben wird, ist der Aufrufer verantwortlich dafür, die Lebensdauer des `task_handle`\-Objekts zu verwalten.  Die Funktion wartet dann, bis die gesamte Arbeit des `structured_task_group`\-Objekts abgeschlossen oder abgebrochen wurde.|  
|[structured\_task\_group::wait\-Methode](../Topic/structured_task_group::wait%20Method.md)|Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wurde.|  
  
## Hinweise  
 Es gibt eine Reihe von schweren Einschränkungen, die für die Verwendung eines `structured_task_group`\-Objekts gelten, um die Leistung zu erhöhen:  
  
-   Ein einzelnes `structured_task_group`\-Objekt kann nicht von mehreren Threads verwendet werden.  Alle Operationen auf einem `structured_task_group`\-Objekt müssen vom Thread ausgeführt werden, der das Objekt erstellt hat.  Die beiden Ausnahmen von dieser Regel sind die Memberfunktionen `cancel` und `is_canceling`.  Das Objekt ist möglicherweise nicht in der Erfassungsliste eines Lambda\-Ausdrucks und wird innerhalb einer Aufgabe verwendet, außer wenn die Aufgabe eine der Abbruchoperationen ist.  
  
-   Alle für ein `structured_task_group`\-Objekt geplanten Aufgaben werden durch die Verwendung von `task_handle`\-Objekten geplant, deren Lebensdauer Sie explizit verwalten müssen.  
  
-   Mehrere Gruppen können nur in absolut geschachtelter Reihenfolge verwendet werden.  Wenn zwei `structured_task_group`\-Objekte deklariert werden, muss das zweite deklarierte Objekt \(das innere\) zerstört werden, bevor irgendeine Methode, mit Ausnahme von `cancel` und `is_canceling`, für das erste Objekt \(das äußere\) aufgerufen wird.  Diese Bedingung trifft zu im Fall, dass mehrere `structured_task_group`\-Objekte einfach innerhalb der gleichen oder funktionell geschachtelten Bereiche deklariert werden, sowie im Fall einer Aufgabe, die in die Warteschlange für die `structured_task_group` über die `run`\-Methode oder `run_and_wait`\-Methode gestellt wurde.  
  
-   Im Gegensatz zur allgemeinen `task_group`\-Klasse sind alle Zustände in der `structured_task_group`\-Klasse endgültig.  Nachdem Sie den Aufgaben der Gruppe und darauf gewartet, indem es in die Warteschlange gestellt haben, können Sie nicht dieselbe Gruppe erneut.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Vererbungshierarchie  
 `structured_task_group`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group\-Klasse](../Topic/task_group%20Class.md)   
 [task\_handle\-Klasse](../../../parallel/concrt/reference/task-handle-class.md)