---
title: "task_completion_event-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_completion_event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_completion_event-Klasse"
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# task_completion_event-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Mit der `task_completion_event`\-Klasse können Sie die Ausführung einer Aufgabe verzögern, bis eine Bedingung erfüllt ist, oder eine Aufgabe als Reaktion auf ein externes Ereignis starten.  
  
## Syntax  
  
```  
template<  
   typename _ResultType  
>  
class task_completion_event;  
  
template<>  
class task_completion_event<void>;  
```  
  
#### Parameter  
 `_ResultType`  
 Der Ergebnistyp dieser `task_completion_event`\-Klasse.  
  
 `T`  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_completion\_event::task\_completion\_event\-Konstruktor](../Topic/task_completion_event::task_completion_event%20Constructor.md)|Erstellt ein `task_completion_event`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_completion\_event::set\-Methode](../Topic/task_completion_event::set%20Method.md)|Überladen.  Legt das Aufgabenabschlussereignis fest.|  
|[task\_completion\_event::set\_exception\-Methode](../Topic/task_completion_event::set_exception%20Method.md)|Überladen.  Gibt eine Ausnahme an alle Aufgaben weiter, die dem Ereignis zugeordnet sind.|  
  
## Hinweise  
 Verwenden Sie eine Aufgabe, die aus einem Aufgabenabschlussereignis erstellt wird, wenn Ihr Szenario die Erstellung einer Aufgabe erfordert, die abgeschlossen wird, und planen Sie die Ausführung ihrer Fortsetzungen für einen späteren Zeitpunkt.  `task_completion_event` muss den gleichen Typ haben, wie die Aufgabe, die Sie erstellen, und das Aufrufen der set\-Methode für das Aufgabenabschlussereignis mit einem Wert dieses Typs führt zu einem Abschluss der zugeordneten Aufgabe und liefert diesen Wert als Ergebnis ihrer Fortsetzungen.  
  
 Wenn das Aufgabenabschlussereignis kein Signal erhält, werden alle Aufgaben, die daraus erstellt wurden, abgebrochen, wenn es zerstört wird.  
  
 `task_completion_event` verhält sich wie ein intelligenter Zeiger und sollte von einem Wert übergeben werden.  
  
## Vererbungshierarchie  
 `task_completion_event`  
  
## Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](assetId:///5389e8a5-5038-40b6-844a-55e9b58ad35f)