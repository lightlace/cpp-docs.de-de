---
title: "concurrent_priority_queue-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_priority_queue/concurrency::concurrent_priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_priority_queue-Klasse"
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# concurrent_priority_queue-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `concurrent_priority_queue`\-Klasse ist ein Container, der es mehreren Threads gleichzeitig ermöglicht, für Elemente die Vorgänge "push" und "pop" auszuführen.  Elemente werden in Reihenfolge ihrer Priorität per pop ausgelesen, wenn die Priorität mit einem als Vorlagenargument angegebenen Funktionselement bestimmt wird.  
  
## Syntax  
  
```  
template <  
   typename _Ty,  
   typename _Compare=std::less<_Ty>,  
   typename _Ax = std::allocator<_Ty>  
>  
, typename _Ax = std::allocator<_Ty> > class concurrent_priority_queue;  
```  
  
#### Parameter  
 `_Ty`  
 Der Datentyp der in der Prioritätswarteschlange zu speichernden Elemente.  
  
 `_Compare`  
 Der Typ des Funktionsobjekts, das zwei Elementwerte vergleichen kann z Sortierschlüssel, um ihre relative Position in der Prioritätswarteschlange zu bestimmen.  Dieses Argument ist optional, und das binäre Prädikat `less<``_Ty``>` ist der Standardwert.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuweisungsobjekt darstellt, das Informationen über die Zuordnung und Freigabe des Speichers für die gleichzeitige Prioritätswarteschlange kapselt.  Dieses Argument ist optional, und der Standardwert ist `allocator<``_Ty``>`.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`allocator_type`|Ein Typ, der die allocator\-Klasse für die gleichzeitige Prioritätswarteschlange darstellt.|  
|`const_reference`|Ein Typ, der einen \- Verweis auf ein Element des Typs darstellt, gespeicherten in einer gleichzeitigen Prioritätswarteschlange.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element des Typs darstellt, gespeicherten in einer gleichzeitigen Prioritätswarteschlange.|  
|`size_type`|Ein Typ, der die Anzahl der Elemente in einer gleichzeitigen Prioritätswarteschlange zählt.|  
|`value_type`|Ein Typ, der dem Datentyp darstellt, gespeicherten in einer gleichzeitigen Prioritätswarteschlange.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_priority\_queue::concurrent\_priority\_queue\-Konstruktor](../Topic/concurrent_priority_queue::concurrent_priority_queue%20Constructor.md)|Überladen.  Erstellt eine gleichzeitige Prioritätswarteschlange.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_priority\_queue::clear\-Methode](../Topic/concurrent_priority_queue::clear%20Method.md)|Löscht alle Elemente in der parallelen Priorität.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_priority\_queue::empty\-Methode](../Topic/concurrent_priority_queue::empty%20Method.md)|Tests, wenn die gleichzeitige Prioritätswarteschlange zum Zeitpunkt leer ist, diese Methode wird aufgerufen.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_priority\_queue::get\_allocator\-Methode](../Topic/concurrent_priority_queue::get_allocator%20Method.md)|Gibt eine Kopie der Zuordnung zurück, die verwendet wird, um die gleichzeitige Prioritätswarteschlange zu erstellen.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_priority\_queue::push\-Methode](../Topic/concurrent_priority_queue::push%20Method.md)|Überladen.  Fügt ein Element der gleichzeitigen Prioritätswarteschlange hinzu.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_priority\_queue::size\-Methode](../Topic/concurrent_priority_queue::size%20Method.md)|Gibt die Anzahl der Elemente in der parallelen Prioritätswarteschlange zurück.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_priority\_queue::swap\-Methode](../Topic/concurrent_priority_queue::swap%20Method.md)|Vertauscht der Inhalt zweier gleichzeitigen Prioritätswarteschlangen aus.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_priority\_queue::try\_pop\-Methode](../Topic/concurrent_priority_queue::try_pop%20Method.md)|Entfernt und gibt das höchste Element der Warteschlange zurück, wenn die Warteschlange nicht leer ist.  Diese Methode ist nebenläufigkeitssicher.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_priority\_queue::operator\=\-Operator](../Topic/concurrent_priority_queue::operator=%20Operator.md)|Überladen.  Weist den Inhalt eines anderen `concurrent_priority_queue`\-Objekts diesem Objekt zu.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## Hinweise  
 Ausführliche Informationen zur `concurrent_priority_queue`\-Klasse finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `concurrent_priority_queue`  
  
## Anforderungen  
 **Header:**  concurrent\_priority\_queue.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md)