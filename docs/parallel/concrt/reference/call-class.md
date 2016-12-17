---
title: "call-Klasse"
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
  - "agents/concurrency::call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call-Klasse"
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
caps.latest.revision: 21
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# call-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `call`\-Meldungsblock ist ein geordneter `target_block` mit mehreren Quellen, der eine bestimmte Funktion aufruft, wenn eine Nachricht empfangen wird.  
  
## Syntax  
  
```  
template<  
   class _Type,  
   class _FunctorType = std::tr1::function<void(_Type const&)>  
>  
class call : public target_block<multi_link_registry<ISource<_Type>>>;  
```  
  
#### Parameter  
 `_Type`  
 Der Nutzlasttyp der Meldungen, die an diesen Block weitergegeben wurden.  
  
 `_FunctorType`  
 Die Signatur von Funktionen, die dieser Block akzeptieren kann.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[call::call\-Konstruktor](../Topic/call::call%20Constructor.md)|Überladen.  Erstellt einen `call`\-Meldungsblock.|  
|[call::~call\-Destruktor](../Topic/call::~call%20Destructor.md)|Zerstört den `call`\-Meldungsblock.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[call::process\_input\_messages\-Methode](../Topic/call::process_input_messages%20Method.md)|Führt \- Funktion auf den Eingabenachrichten aus.|  
|[call::process\_message\-Methode](../Topic/call::process_message%20Method.md)|Verarbeitet eine Meldung, die von diesem `call`\-Meldungsblock akzeptiert wurde.|  
|[call::propagate\_message\-Methode](../Topic/call::propagate_message%20Method.md)|Übergibt eine Meldung asynchron von einem `ISource`\-Block an diesen `call`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[call::send\_message\-Methode](../Topic/call::send_message%20Method.md)|Übergibt eine Meldung synchron von einem `ISource`\-Block an diesen `call`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `send`\-Methode aufgerufen.|  
|[call::supports\_anonymous\_source\-Methode](../Topic/call::supports_anonymous_source%20Method.md)|Überschreibt die `supports_anonymous_source`\-Methode, um anzugeben, dass der Block die Nachrichten verwenden kann, die es von einer Quelle bereitgestellt werden, die nicht verknüpft wird. Überschreibungen \( [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [target\_block](../../../parallel/concrt/reference/target-block-class.md)  
  
 `call`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [transformer\-Klasse](../../../parallel/concrt/reference/transformer-class.md)