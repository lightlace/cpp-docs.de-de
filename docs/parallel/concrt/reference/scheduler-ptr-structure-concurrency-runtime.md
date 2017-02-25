---
title: "scheduler_ptr-Struktur (Concurrency Runtime) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplinterface/concurrency::scheduler_ptr"
dev_langs: 
  - "C++"
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# scheduler_ptr-Struktur (Concurrency Runtime)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Zeiger auf einen Planer dar.  Diese Klasse ist vorhanden, um die Spezifikation einer freigegebenen Lebensdauer mithilfe von "shared\_ptr" oder nur eines einfachen Verweises und eines unformatierten Zeigers zu ermöglichen.  
  
## Syntax  
  
```  
struct scheduler_ptr;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_ptr::scheduler\_ptr\-Konstruktor \(Concurrency Runtime\)](../Topic/scheduler_ptr::scheduler_ptr%20Constructor%20\(Concurrency%20Runtime\).md)|Überladen.  Erstellt einen scheduler\-Zeiger von "shared\_ptr" auf "scheduler".|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_ptr::get\-Method \(Concurrency Runtime\)](../Topic/scheduler_ptr::get%20Method%20\(Concurrency%20Runtime\).md)|Gibt den Rohzeiger auf den Planer zurück.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_ptr::operator bool\-Operator \(Concurrency Runtime\)](../Topic/scheduler_ptr::operator%20bool%20Operator%20\(Concurrency%20Runtime\).md)|Testet, dass der scheduler\-Zeiger nicht NULL ist.|  
|[scheduler\_ptr::operator\-\> Operator \(Concurrency Runtime\)](../Topic/scheduler_ptr::operator-%3E%20Operator%20\(Concurrency%20Runtime\).md)|Verhält sich wie ein Zeiger.|  
  
## Vererbungshierarchie  
 `scheduler_ptr`  
  
## Anforderungen  
 **Header:** pplinterface.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)