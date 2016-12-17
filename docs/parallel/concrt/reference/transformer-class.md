---
title: "transformer-Klasse"
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
  - "agents/concurrency::transformer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transformer-Klasse"
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
caps.latest.revision: 22
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# transformer-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `transformer`\-Meldungsblock ist ein geordneter `propagator_block` mit einem einzelnen Ziel und mehreren Quellen, der Meldungen eines Typs akzeptieren und eine unbegrenzte Anzahl von Meldungen eines anderen Typs speichern kann.  
  
## Syntax  
  
```  
template<  
   class _Input,  
   class _Output  
>  
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>, multi_link_registry<ISource<_Input>>>;  
```  
  
#### Parameter  
 `_Input`  
 Der Nutzlasttyp von vom Puffer akzeptierten Meldungen.  
  
 `_Output`  
 Der Nutzlasttyp der Meldungen, die vom Puffer gespeichert und weitergegeben wurden.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[transformer::transformer\-Konstruktor](../Topic/transformer::transformer%20Constructor.md)|Überladen.  Erstellt einen `transformer`\-Meldungsblock.|  
|[transformer::~transformer\-Destruktor](../Topic/transformer::~transformer%20Destructor.md)|Zerstört den `transformer`\-Meldungsblock.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[transformer::accept\_message\-Methode](../Topic/transformer::accept_message%20Method.md)|Akzeptiert eine Meldung, die von diesem `transformer`\-Meldungsblock angeboten wurde, und überträgt den Besitz an den Aufrufer.|  
|[transformer::consume\_message\-Methode](../Topic/transformer::consume_message%20Method.md)|Nimmt eine Meldung an, die zuvor von `transformer` angeboten und vom Ziel reserviert wurde, und überträgt den Besitz an den Aufrufer.|  
|[transformer::link\_target\_notification\-Methode](../Topic/transformer::link_target_notification%20Method.md)|Ein Rückruf, der meldet, dass ein neues Ziel mit diesem `transformer`\-Meldungsblock verknüpft wurde.|  
|[transformer::propagate\_message\-Methode](../Topic/transformer::propagate_message%20Method.md)|Übergibt eine Meldung asynchron von einem `ISource`\-Block an diesen `transformer`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[transformer::propagate\_to\_any\_targets\-Methode](../Topic/transformer::propagate_to_any_targets%20Method.md)|Listet die auf den Transformatorfunktion Eingabenachrichten aus.|  
|[transformer::release\_message\-Methode](../Topic/transformer::release_message%20Method.md)|Gibt die Reservierung einer vorherigen Meldung frei. \(Überschreibt [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[transformer::reserve\_message\-Methode](../Topic/transformer::reserve_message%20Method.md)|Reserviert eine Meldung, die zuvor von diesem `transformer`\-Meldungsblock angeboten wurde. \(Überschreibt [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[transformer::resume\_propagation\-Methode](../Topic/transformer::resume_propagation%20Method.md)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. \(Überschreibt [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
|[transformer::send\_message\-Methode](../Topic/transformer::send_message%20Method.md)|Übergibt eine Meldung synchron von einem `ISource`\-Block an diesen `transformer`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `send`\-Methode aufgerufen.|  
|[transformer::supports\_anonymous\_source\-Methode](../Topic/transformer::supports_anonymous_source%20Method.md)|Überschreibt die `supports_anonymous_source`\-Methode, um anzugeben, dass der Block die Nachrichten verwenden kann, die es von einer Quelle bereitgestellt werden, die nicht verknüpft wird. Überschreibungen \( [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `transformer`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [call\-Klasse](../../../parallel/concrt/reference/call-class.md)