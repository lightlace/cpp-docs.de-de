---
title: "concurrent_queue-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_queue/concurrency::concurrent_queue"
  - "concurrent_queue/Concurrency::concurrent_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_queue-Klasse"
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# concurrent_queue-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `concurrent_queue`\-Klasse ist eine Sequenzcontainerklasse, die "First In, First Out"\-Zugriff auf ihre Elemente zulässt.  Sie aktiviert einen beschränkten Satz von parallelitätssicheren Vorgängen, z. B. `push` und `try_pop`.  
  
## Syntax  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;  
```  
  
#### Parameter  
 `_Ty`  
 Der Datentyp der Elemente, die in der Warteschlange gespeichert werden sollen.  
  
 `_Ax`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zur Zuordnung und zur Freigabe des Arbeitsspeichers für diese Parallelwarteschlange kapselt.  Dieses Argument ist optional, und der Standardwert ist `allocator<``_Ty``>`.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`allocator_type`|Ein Typ, der die Belegungsfunktionsklasse für die gleichzeitige Warteschlange darstellt.|  
|`const_iterator`|Ein Typ, der einen nicht threadsicheren `const`\-Iterator über Elemente in einer gleichzeitigen Warteschlange darstellt.|  
|`const_reference`|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einer gleichzeitigen Lesewarteschlange gespeichert ist und `const`\-Operationen durchführt.|  
|`difference_type`|Ein Typ, der die vorzeichenbehaftete Entfernung zwischen zwei Elementen in einer gleichzeitigen Warteschlange bereitstellt.|  
|`iterator`|Ein Typ, der einen nicht threadsicheren Iterator über die Elemente in einer gleichzeitigen Warteschlange darstellt.|  
|`reference`|Ein Typ, der einen Verweis auf ein Element in einer gleichzeitigen Warteschlange bereitstellt.|  
|`size_type`|Ein Typ, der die Anzahl von Elementen in einer gleichzeitigen Warteschlange angibt.|  
|`value_type`|Ein Typ, der den in einer gleichzeitigen Warteschlange gespeicherten Datentyp darstellt.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_queue::concurrent\_queue\-Konstruktor](../Topic/concurrent_queue::concurrent_queue%20Constructor.md)|Überladen.  Erstellt eine gleichzeitige Warteschlange.|  
|[concurrent\_queue::~concurrent\_queue\-Destruktor](../Topic/concurrent_queue::~concurrent_queue%20Destructor.md)|Zerstört die gleichzeitige Warteschlange.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[concurrent\_queue::clear\-Methode](../Topic/concurrent_queue::clear%20Method.md)|Löscht die gleichzeitige Warteschlange und zerstört alle gerade in der Warteschlange vorhandenen Elemente.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_queue::empty\-Methode](../Topic/concurrent_queue::empty%20Method.md)|Testet, ob die gleichzeitige Warteschlange beim Aufruf dieser Methode leer ist.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_queue::get\_allocator\-Methode](../Topic/concurrent_queue::get_allocator%20Method.md)|Gibt eine Kopie der Belegungsfunktion zurück, die verwendet wurde, um die parallele Warteschlange zu erstellen.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_queue::push\-Methode](../Topic/concurrent_queue::push%20Method.md)|Überladen.  Enqueues ein Element am Ende der gleichzeitigen Warteschlange.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_queue::try\_pop\-Methode](../Topic/concurrent_queue::try_pop%20Method.md)|Entfernt ein Element aus der Warteschlange, sofern vorhanden.  Diese Methode ist nebenläufigkeitssicher.|  
|[concurrent\_queue::unsafe\_begin\-Methode](../Topic/concurrent_queue::unsafe_begin%20Method.md)|Überladen.  Gibt einen Iterator vom Typ `iterator` oder `const_iterator` zum Anfang der gleichzeitigen Warteschlange zurück.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_queue::unsafe\_end\-Methode](../Topic/concurrent_queue::unsafe_end%20Method.md)|Überladen.  Gibt einen Iterator vom Typ `iterator` oder `const_iterator` zum Ende der gleichzeitigen Warteschlange zurück.  Diese Methode ist nicht nebenläufigkeitssicher.|  
|[concurrent\_queue::unsafe\_size\-Methode](../Topic/concurrent_queue::unsafe_size%20Method.md)|Gibt die Anzahl der Elemente in der Warteschlange zurück.  Diese Methode ist nicht nebenläufigkeitssicher.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `concurrent_queue`  
  
## Anforderungen  
 **Header:** concurrent\_queue.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)