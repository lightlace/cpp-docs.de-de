---
title: "join-Klasse"
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
  - "agents/concurrency::join"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "join-Klasse"
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# join-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `join`\-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Quellen und einem einzelnen Ziel, der Meldungen vom Typ `_Type` aus allen Quellen kombiniert.  
  
## Syntax  
  
```  
template<  
   class _Type,  
   join_type _Jtype = non_greedy  
>  
class join : public propagator_block<single_link_registry<ITarget<std::vector<_Type>>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Parameter  
 `_Type`  
 Der Nutzlasttyp der Meldungen, die vom Block zusammengeführt und weitergegeben wurden.  
  
 `_Jtype`  
 Die Art des `join`\-Blocks, entweder `greedy` oder `non_greedy`.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[join::join\-Konstruktor](../Topic/join::join%20Constructor.md)|Überladen.  Erstellt einen `join`\-Meldungsblock.|  
|[join::~join\-Destruktor](../Topic/join::~join%20Destructor.md)|Zerstört den `join`\-Block.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[join::accept\_message\-Methode](../Topic/join::accept_message%20Method.md)|Akzeptiert eine Meldung, die von diesem `join`\-Meldungsblock angeboten wurde, und überträgt den Besitz an den Aufrufer.|  
|[join::consume\_message\-Methode](../Topic/join::consume_message%20Method.md)|Nimmt eine Meldung an, die zuvor vom `join`\-Meldungsblock angeboten und vom Ziel reserviert wurde, und überträgt den Besitz an den Aufrufer.|  
|[join::link\_target\_notification\-Methode](../Topic/join::link_target_notification%20Method.md)|Ein Rückruf, der meldet, dass ein neues Ziel mit diesem `join`\-Meldungsblock verknüpft wurde.|  
|[join::propagate\_message\-Methode](../Topic/join::propagate_message%20Method.md)|Übergibt eine Meldung asynchron von einem `ISource`\-Block an diesen `join`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[join::propagate\_to\_any\_targets\-Methode](../Topic/join::propagate_to_any_targets%20Method.md)|Erstellt eine Ausgabemeldung, die eine Eingabemeldung von jeder Quelle enthält, wenn alle Quellen eine Meldung weitergegeben haben.  Sendet diese Ausgabemeldung an jedes der Ziele.|  
|[join::release\_message\-Methode](../Topic/join::release_message%20Method.md)|Gibt die Reservierung einer vorherigen Meldung frei. \(Überschreibt [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[join::reserve\_message\-Methode](../Topic/join::reserve_message%20Method.md)|Reserviert eine Meldung, die zuvor von diesem `join`\-Meldungsblock angeboten wurde. \(Überschreibt [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[join::resume\_propagation\-Methode](../Topic/join::resume_propagation%20Method.md)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. \(Überschreibt [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `join`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [choice\-Klasse](../../../parallel/concrt/reference/choice-class.md)   
 [multitype\_join\-Klasse](../../../parallel/concrt/reference/multitype-join-class.md)   
 [join\_type\-Enumeration](../Topic/join_type%20Enumeration.md)