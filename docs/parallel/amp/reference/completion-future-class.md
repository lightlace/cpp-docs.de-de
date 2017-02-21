---
title: "completion_future-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::completion_future"
dev_langs: 
  - "C++"
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# completion_future-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt ein "future"\-Objekt dar, das einer asynchronen C\+\+ AMP\-Operation entspricht.  
  
## Syntax  
  
```  
class completion_future;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[completion\_future::completion\_future\-Konstruktor](../Topic/completion_future::completion_future%20Constructor.md)|Initialisiert eine neue Instanz der `completion_future`\-Klasse.|  
|[completion\_future::~completion\_future\-Destruktor](../Topic/completion_future::~completion_future%20Destructor.md)|Zerstört das `completion_future`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[completion\_future::get\-Methode](../Topic/completion_future::get%20Method.md)|Wartet, bis der zugeordnete asynchrone Vorgang beendet ist.|  
|[completion\_future::then\-Methode](../Topic/completion_future::then%20Method.md)|Verkettet ein Rückruffunktionsobjekt mit dem `completion_future`\-Objekt, das ausgeführt werden soll, wenn der zugeordnete asynchrone Vorgang beendet wird.|  
|[completion\_future::to\_task\-Methode](../Topic/completion_future::to_task%20Method.md)|Gibt ein `task`\-Objekt zurück, das dem zugeordneten asynchronen Vorgang entspricht.|  
|[completion\_future::valid\-Methode](../Topic/completion_future::valid%20Method.md)|Ruft einen booleschen Wert ab, der angibt, ob das Objekt einem asynchronen Vorgang zugeordnet ist.|  
|[completion\_future::wait\-Methode](../Topic/completion_future::wait%20Method.md)|Blockiert, bis der zugeordnete asynchrone Vorgang beendet ist.|  
|[completion\_future::wait\_for\-Methode](../Topic/completion_future::wait_for%20Method.md)|Blockiert, bis der zugeordnete asynchrone Vorgang beendet oder die Zeit, die von `_Rel_time` angegeben wird, abgelaufen ist.|  
|[completion\_future::wait\_until\-Methode](../Topic/completion_future::wait_until%20Method.md)|Blockiert, bis der zugeordnete asynchrone Vorgang beendet ist oder die aktuelle Uhrzeit den von `_Abs_time` angegebenen Wert überschreitet.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[completion\_future::operator std::shared\_future\<void\>\-Operator](../Topic/completion_future::operator%20std::shared_future%3Cvoid%3E%20Operator.md)|Konvertiert implizit das `completion_future`\-Objekt zu einem `std::shared_future`\-Objekt.|  
|[completion\_future::operator\=\-Operator](../Topic/completion_future::operator=%20Operator.md)|Kopiert den Inhalt des angegebenen `completion_future`\-Objekts in dieses Objekt.|  
  
## Vererbungshierarchie  
 `completion_future`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)