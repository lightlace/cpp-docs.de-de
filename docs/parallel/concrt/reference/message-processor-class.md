---
title: "message_processor-Klasse"
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
  - "agents/concurrency::message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_processor-Klasse"
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# message_processor-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `message_processor`\-Klasse ist die abstrakte Basisklasse für die Verarbeitung von `message`\-Objekten.  Für die Reihenfolge der Meldungen besteht keine Garantie.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class message_processor;  
```  
  
#### Parameter  
 `_Type`  
 Der Datentyp der Nutzlast innerhalb der Meldungen wird von diesem `message_processor`\-Objekt behandelt.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`type`|Ein Typalias für `_Type`.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[message\_processor::async\_send\-Methode](../Topic/message_processor::async_send%20Method.md)|Platziert beim Überschreiben in einer abgeleiteten Klasse Meldungen asynchron in den Block.|  
|[message\_processor::sync\_send\-Methode](../Topic/message_processor::sync_send%20Method.md)|Platziert beim Überschreiben in einer abgeleiteten Klasse Meldungen synchron in den Block.|  
|[message\_processor::wait\-Methode](../Topic/message_processor::wait%20Method.md)|Wartet beim Überschreiben in einer abgeleiteten Klasse auf das Beenden aller synchronen Vorgänge.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[message\_processor::process\_incoming\_message\-Methode](../Topic/message_processor::process_incoming_message%20Method.md)|Führt beim Überschreiben in einer abgeleiteten Klasse die Vorwärtsverarbeitung von Meldungen in den Block aus.  Wird jedes Mal aufgerufen, wenn eine neue Meldung hinzugefügt wird und die Warteschlange leer ist.|  
  
## Vererbungshierarchie  
 `message_processor`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ordered\_message\_processor\-Klasse](../../../parallel/concrt/reference/ordered-message-processor-class.md)