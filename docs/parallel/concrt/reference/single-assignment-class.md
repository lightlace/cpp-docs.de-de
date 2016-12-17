---
title: "single_assignment-Klasse"
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
  - "agents/concurrency::single_assignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_assignment-Klasse"
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
caps.latest.revision: 21
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# single_assignment-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `single_assignment`\-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine einzelne, einmal beschreibbare `message` speichern kann.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class single_assignment : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Parameter  
 `_Type`  
 Der Nutzlasttyp der Meldung, die vom Puffer gespeichert und weitergegeben wurde.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[single\_assignment::single\_assignment\-Konstruktor](../Topic/single_assignment::single_assignment%20Constructor.md)|Überladen.  Erstellt einen `single_assignment`\-Meldungsblock.|  
|[single\_assignment::~single\_assignment\-Destruktor](../Topic/single_assignment::~single_assignment%20Destructor.md)|Zerstört den `single_assignment`\-Meldungsblock.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[single\_assignment::has\_value\-Methode](../Topic/single_assignment::has_value%20Method.md)|Überprüft, ob dieser `single_assignment`\-Meldungsblock bereits mit einem Wert initialisiert wurde.|  
|[single\_assignment::value\-Methode](../Topic/single_assignment::value%20Method.md)|Ruft einen Verweis auf die aktuelle Nutzlast der Meldung ab, die im `single_assignment`\-Meldungsblock gespeichert ist.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[single\_assignment::accept\_message\-Methode](../Topic/single_assignment::accept_message%20Method.md)|Akzeptiert eine Meldung, die von diesem `single_assignment`\-Meldungsblock angeboten wurde, und gibt eine Kopie der Meldung an den Aufrufer zurück.|  
|[single\_assignment::consume\_message\-Methode](../Topic/single_assignment::consume_message%20Method.md)|Nimmt eine Meldung an, die zuvor von `single_assignment` angeboten und vom Ziel reserviert wurde, und gibt eine Kopie der Meldung an den Aufrufer zurück.|  
|[single\_assignment::link\_target\_notification\-Methode](../Topic/single_assignment::link_target_notification%20Method.md)|Ein Rückruf, der meldet, dass ein neues Ziel mit diesem `single_assignment`\-Meldungsblock verknüpft wurde.|  
|[single\_assignment::propagate\_message\-Methode](../Topic/single_assignment::propagate_message%20Method.md)|Übergibt eine Meldung asynchron von einem `ISource`\-Block an diesen `single_assignment`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[single\_assignment::propagate\_to\_any\_targets\-Methode](../Topic/single_assignment::propagate_to_any_targets%20Method.md)|Fügt `message``_PMessage` in diesen `single_assignment`\-Meldungsblock ein und bietet sie allen verknüpften Zielen an.|  
|[single\_assignment::release\_message\-Methode](../Topic/single_assignment::release_message%20Method.md)|Gibt die Reservierung einer vorherigen Meldung frei. \(Überschreibt [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[single\_assignment::reserve\_message\-Methode](../Topic/single_assignment::reserve_message%20Method.md)|Reserviert eine Meldung, die zuvor von diesem `single_assignment`\-Meldungsblock angeboten wurde. \(Überschreibt [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[single\_assignment::resume\_propagation\-Methode](../Topic/single_assignment::resume_propagation%20Method.md)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. \(Überschreibt [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
|[single\_assignment::send\_message\-Methode](../Topic/single_assignment::send_message%20Method.md)|Übergibt eine Meldung synchron von einem `ISource`\-Block an diesen `single_assignment`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `send`\-Methode aufgerufen.|  
  
## Hinweise  
 Ein `single_assignment`\-Meldungsblock gibt Kopien seiner Meldungen an jedes Ziel weiter.  
  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `single_assignment`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [overwrite\_buffer\-Klasse](../../../parallel/concrt/reference/overwrite-buffer-class.md)   
 [unbounded\_buffer\-Klasse](../Topic/unbounded_buffer%20Class.md)