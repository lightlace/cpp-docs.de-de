---
title: "task_handle-Klasse"
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
  - "ppl/concurrency::task_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_handle-Klasse"
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# task_handle-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `task_handle`\-Klasse stellt eine einzelne parallele Arbeitsaufgabe dar.  Sie kapselt die Anweisungen und die zum Ausführen eines Teils der Arbeit erforderlichen Daten.  
  
## Syntax  
  
```  
template<  
   typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts, das aufgerufen wird, um die vom `task_handle`\-Objekt dargestellten Arbeiten auszuführen.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_handle::task\_handle\-Konstruktor](../Topic/task_handle::task_handle%20Constructor.md)|Erstellt ein neues `task_handle`\-Objekt.  Die Arbeit der Aufgabe wird ausgeführt, indem die als Parameter an den Konstruktor angegebene Funktion aufgerufen wird.|  
|[task\_handle::~task\_handle\-Destruktor](../Topic/task_handle::~task_handle%20Destructor.md)|Zerstört das `task_handle`\-Objekt.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_handle::operator\(\)\-Operator](../Topic/task_handle::operator\(\)%20Operator.md)|Der Funktionsaufrufoperator, den die Laufzeit aufruft, um die Arbeit des Aufgabenhandles auszuführen.|  
  
## Hinweise  
 `task_handle`\-Objekte können in Verbindung mit einer `structured_task_group` oder einem allgemeineren `task_group`\-Objekt verwendet werden, um die Arbeit in parallele Aufgaben aufzuteilen.  Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Beachten Sie, dass der Ersteller eines `task_handle`\-Objekts für das Verwalten der Lebensdauer des erstellten `task_handle`\-Objekts zuständig ist, bis es nicht mehr von der Concurrency Runtime benötigt wird.  In der Regel bedeutet dies, dass das `task_handle`\-Objekt erst zerstört werden darf, bis die `wait`\-Methode oder `run_and_wait`\-Methode der `task_group` oder `structured_task_group` aufgerufen wurde, für die es in die Warteschlange gestellt wurde.  
  
 `task_handle`\-Objekte werden in der Regel in Verbindung mit C\+\+\-Lambdas verwendet.  Da Sie den wahren Typ des Lambdas nicht wissen, wird i. d. R. die [make\_task](../Topic/make_task%20Function.md)\-Funktion verwendet, um ein `task_handle`\-Objekt zu erstellen.  
  
 Beim Testlauf wird eine Kopie der Arbeitsfunktion erstellt, die an ein `task_handle`\-Objekt übergeben wird.  Daher werden Zustandsänderungen, die in einem an ein `task_handle`\-Objekt übergebenen Funktionsobjekt auftreten, nicht in der Kopie dieses Funktionsobjekts angezeigt.  
  
## Vererbungshierarchie  
 `task_handle`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group\-Klasse](../Topic/task_group%20Class.md)   
 [structured\_task\_group\-Klasse](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [make\_task\-Funktion](../Topic/make_task%20Function.md)   
 [task\_group::run\-Methode](../Topic/task_group::run%20Method.md)   
 [task\_group::wait\-Methode](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait\-Methode](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group::run\-Methode](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait\-Methode](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait\-Methode](../Topic/structured_task_group::run_and_wait%20Method.md)