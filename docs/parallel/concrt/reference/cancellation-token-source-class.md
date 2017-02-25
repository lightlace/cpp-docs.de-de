---
title: "cancellation_token_source-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_source-Klasse"
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# cancellation_token_source-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Mit der `cancellation_token_source` \-Klasse kann ein abbrechbarer Vorgang abgebrochen werden.  
  
## Syntax  
  
```  
class cancellation_token_source;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token\_source::cancellation\_token\_source\-Konstruktor](../Topic/cancellation_token_source::cancellation_token_source%20Constructor.md)|Überladen.  Erstellt eine neue `cancellation_token_source`.  Die Quelle kann verwendet werden, um den Abbruch eines abbrechbaren Vorgangs zu kennzeichnen.|  
|[cancellation\_token\_source::~cancellation\_token\_source\-Destruktor](../Topic/cancellation_token_source::~cancellation_token_source%20Destructor.md)||  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token\_source::cancel\-Methode](../Topic/cancellation_token_source::cancel%20Method.md)|Bricht das Token ab.  Jede `task_group`, `structured_task_group` oder jeder `task`, der das Token nutzt, wird bei diesem Aufruf abgebrochen und löst eine Ausnahme am nächsten Unterbrechungspunkt aus.|  
|[cancellation\_token\_source::create\_linked\_source\-Methode](../Topic/cancellation_token_source::create_linked_source%20Method.md)|Überladen.  Erstellt eine `cancellation_token_source`, die abgebrochen wird, wenn das bereitgestellte Token abgebrochen wird.|  
|[cancellation\_token\_source::get\_token\-Methode](../Topic/cancellation_token_source::get_token%20Method.md)|Gibt ein Abbruchtoken zurück, das dieser Quelle zugeordnet ist.  Das zurückgegebene Token kann für einen Abbruch abgerufen werden oder einen Rückruf bereitstellen, wenn ein Abbruch auftritt.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token\_source::operator\!\=\-Operator](../Topic/cancellation_token_source::operator!=%20Operator.md)||  
|[cancellation\_token\_source::operator\=\-Operator](../Topic/cancellation_token_source::operator=%20Operator.md)||  
|[cancellation\_token\_source::operator\=\=\-Operator](../Topic/cancellation_token_source::operator==%20Operator.md)||  
  
## Vererbungshierarchie  
 `cancellation_token_source`  
  
## Anforderungen  
 **Header:** pplcancellation\_token.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)