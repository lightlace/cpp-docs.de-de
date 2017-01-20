---
title: "task-Klasse (Concurrency Runtime)"
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
  - "ppltasks/concurrency::task"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task-Klasse"
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# task-Klasse (Concurrency Runtime)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Parallel Patterns Library \(PPL\) `task`\-Klasse.  Ein `task`\-Objekt stellt Arbeit dar, die asynchron und übereinstimmend mit anderen Tasks und paralleler Arbeit , die von parallelen Algorithmen in der Concurrency Runtime erzeugt wird, ausgeführt werden kann.  Es enthält bei erfolgreichem Abschluss ein Ergebnis vom Typ `_ResultType`.  Tasks des Typs `task<void>` führen zu keinem Ergebnis.  Ein Task kann erwartet und unabhängig von anderen Tasks abgebrochen werden.  Er kann mit anderen Tasks mithilfe von Continuations \(`then`\) sowie Join\-Muster \(`when_all`\) und Choise\-Muster \(`when_any`\) erstellt werden.  
  
## Syntax  
  
```  
template <  
   typename _Type  
>  
class task;  
  
template <>  
class task<void>;  
  
template<  
   typename _ReturnType  
>  
class task;  
```  
  
#### Parameter  
 `_Type`  
 `T`  
 `_ReturnType`  
 Der Ergebnistyp dieses Tasks.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`result_type`|Der Typ des von einem Objekt dieser Klasse erstellten Ergebnisses.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task::task\-Konstruktor](../Topic/task::task%20Constructor.md)|Überladen.  Erstellt ein `task`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task::get\-Methode](../Topic/task::get%20Method.md)|Überladen.  Gibt das von diesem Task erstellte Ergebnis zurück.  Wenn sich der Task nicht in einem abschließenden Zustand befindet, wird mit dem `get`\-Aufruf gewartet, bis der Task fertig gestellt wurde.  Diese Methode gibt bei dem Aufruf eines Tasks mit einem `result_type` von `void` keinen Wert zurück.|  
|[task::is\_apartment\_aware\-Methode](../Topic/task::is_apartment_aware%20Method.md)|Bestimmt, ob der Task eine `IAsyncInfo`\-Schnittstelle der Windows Runtime entpackt oder von einem solchen Task abgeleitet wurde.|  
|[task::is\_done\-Methode](../Topic/task::is_done%20Method%20\(Concurrency%20Runtime\).md)|Bestimmt, ob der Task abgeschlossen wurde.|  
|[task::scheduler\-Methode \(Concurrency Runtime\)](../Topic/task::scheduler%20Method%20\(Concurrency%20Runtime\).md)|Gibt den Planer für diesen Task zurück.|  
|[task::then\-Methode](../Topic/task::then%20Method.md)|Überladen.  Fügt diesem Task einen Fortsetzungstask hinzu.|  
|[task::wait\-Methode](../Topic/task::wait%20Method.md)|Erwartet, dass dieser Task einen Terminalzustand erreicht.  Es ist möglich, dass das `wait`\-Element den Task inline ausführt, wenn alle Taskabhängigkeiten erfüllt sind und er nicht bereits zur Ausführung durch einen Hintergrundworker aufgehoben wurde.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task::operator\!\=\-Operator](../Topic/task::operator!=%20Operator.md)|Überladen.  Bestimmt, ob zwei `task`\-Objekte unterschiedliche interne Prozesse darstellen.|  
|[task::operator\=\-Operator](../Topic/task::operator=%20Operator.md)|Überladen.  Ersetzt den Inhalt eines `task`\-Objekts durch einen anderen.|  
|[task::operator\=\=\-Operator](../Topic/task::operator==%20Operator.md)|Überladen.  Bestimmt, ob zwei `task`\-Objekte den gleichen internen Task darstellen.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Vererbungshierarchie  
 `task`  
  
## Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)