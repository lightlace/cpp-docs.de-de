---
title: "ordered_message_processor-Klasse"
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
  - "agents/concurrency::ordered_message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered_message_processor-Klasse"
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# ordered_message_processor-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `ordered_message_processor` ist ein `message_processor`, mit dem Meldungsblöcke Meldungen in der Reihenfolge verarbeiten können, in der sie empfangen wurden.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class ordered_message_processor : public message_processor<_Type>;  
```  
  
#### Parameter  
 `_Type`  
 Der Nutzlasttyp von durch den Prozessor behandelten Meldungen.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`type`|Ein Typalias für `_Type`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ordered\_message\_processor::ordered\_message\_processor\-Konstruktor](../Topic/ordered_message_processor::ordered_message_processor%20Constructor.md)|Erstellt ein `ordered_message_processor`\-Objekt.|  
|[ordered\_message\_processor::~ordered\_message\_processor\-Destruktor](../Topic/ordered_message_processor::~ordered_message_processor%20Destructor.md)|Zerstört das `ordered_message_processor`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ordered\_message\_processor::async\_send\-Methode](../Topic/ordered_message_processor::async_send%20Method.md)|Stellt asynchron Meldungen in die Warteschlange ein und startet eine Verarbeitungsaufgabe, wenn dies nicht bereits geschehen ist. \(Überschreibt [message\_processor::async\_send](../Topic/message_processor::async_send%20Method.md).\)|  
|[ordered\_message\_processor::initialize\-Methode](../Topic/ordered_message_processor::initialize%20Method.md)|Initialisiert das `ordered_message_processor`\-Objekt mit der entsprechenden Rückruffunktion, dem Planer und der Planungsgruppe.|  
|[ordered\_message\_processor::initialize\_batched\_processing\-Methode](../Topic/ordered_message_processor::initialize_batched_processing%20Method.md)|Initialize verarbeitete Meldungsverarbeitung von bei|  
|[ordered\_message\_processor::sync\_send\-Methode](../Topic/ordered_message_processor::sync_send%20Method.md)|Stellt synchron Meldungen in die Warteschlange ein und startet eine Verarbeitungsaufgabe, wenn dies nicht bereits geschehen ist. \(Überschreibt [message\_processor::sync\_send](../Topic/message_processor::sync_send%20Method.md).\)|  
|[ordered\_message\_processor::wait\-Methode](../Topic/ordered_message_processor::wait%20Method.md)|Ein prozessorspezifischer Spin\-Wait, der in Destruktoren von Meldungsblöcken verwendet wird, um sicherzustellen, dass alle asynchronen Verarbeitungsaufgaben genügend Zeit zum Beenden erhalten, bevor der Block zerstört wird. \(Überschreibt [message\_processor::wait](../Topic/message_processor::wait%20Method.md).\)|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ordered\_message\_processor::process\_incoming\_message\-Methode](../Topic/ordered_message_processor::process_incoming_message%20Method.md)|Die Verarbeitungsfunktion, die asynchron aufgerufen wird.  Entfernt Meldungen aus der Warteschlange und verarbeitet sie. \(Überschreibt [message\_processor::process\_incoming\_message](../Topic/message_processor::process_incoming_message%20Method.md).\)|  
  
## Vererbungshierarchie  
 [message\_processor](../../../parallel/concrt/reference/message-processor-class.md)  
  
 `ordered_message_processor`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)