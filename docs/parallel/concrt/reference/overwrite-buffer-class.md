---
title: "overwrite_buffer-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::overwrite_buffer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overwrite_buffer-Klasse"
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# overwrite_buffer-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `overwrite_buffer`\-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der jeweils eine einzelne Meldung speichern kann.  Neue Meldungen überschreiben zuvor Gespeicherte.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Parameter  
 `_Type`  
 Der Nutzlasttyp der Meldungen, die vom Puffer gespeichert und weitergegeben wurden.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[overwrite\_buffer::overwrite\_buffer\-Konstruktor](../Topic/overwrite_buffer::overwrite_buffer%20Constructor.md)|Überladen.  Erstellt einen `overwrite_buffer`\-Meldungsblock.|  
|[overwrite\_buffer::~overwrite\_buffer\-Destruktor](../Topic/overwrite_buffer::~overwrite_buffer%20Destructor.md)|Zerstört den `overwrite_buffer`\-Meldungsblock.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[overwrite\_buffer::has\_value\-Methode](../Topic/overwrite_buffer::has_value%20Method.md)|Überprüft, ob dieser `overwrite_buffer`\-Meldungsblock bereits über einen Wert verfügt.|  
|[overwrite\_buffer::value\-Methode](../Topic/overwrite_buffer::value%20Method.md)|Ruft einen Verweis auf die aktuelle Nutzlast der Meldung ab, die im `overwrite_buffer`\-Meldungsblock gespeichert ist.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[overwrite\_buffer::accept\_message\-Methode](../Topic/overwrite_buffer::accept_message%20Method.md)|Akzeptiert eine Meldung, die von diesem `overwrite_buffer`\-Meldungsblock angeboten wurde, und gibt eine Kopie der Meldung an den Aufrufer zurück.|  
|[overwrite\_buffer::consume\_message\-Methode](../Topic/overwrite_buffer::consume_message%20Method.md)|Nimmt eine Meldung an, die zuvor vom `overwrite_buffer`\-Meldungsblock angeboten und vom Ziel reserviert wurde, und gibt eine Kopie der Meldung an den Aufrufer zurück.|  
|[overwrite\_buffer::link\_target\_notification\-Methode](../Topic/overwrite_buffer::link_target_notification%20Method.md)|Ein Rückruf, der meldet, dass ein neues Ziel mit diesem `overwrite_buffer`\-Meldungsblock verknüpft wurde.|  
|[overwrite\_buffer::propagate\_message\-Methode](../Topic/overwrite_buffer::propagate_message%20Method.md)|Übergibt eine Meldung asynchron von einem `ISource`\-Block an diesen `overwrite_buffer`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[overwrite\_buffer::propagate\_to\_any\_targets\-Methode](../Topic/overwrite_buffer::propagate_to_any_targets%20Method.md)|Fügt `message``_PMessage` in diesen `overwrite_buffer`\-Meldungsblock ein und bietet sie allen verknüpften Zielen an.|  
|[overwrite\_buffer::release\_message\-Methode](../Topic/overwrite_buffer::release_message%20Method.md)|Gibt die Reservierung einer vorherigen Meldung frei. \(Überschreibt [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[overwrite\_buffer::reserve\_message\-Methode](../Topic/overwrite_buffer::reserve_message%20Method.md)|Reserviert eine Meldung, die zuvor von diesem `overwrite_buffer`\-Meldungsblock angeboten wurde. \(Überschreibt [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[overwrite\_buffer::resume\_propagation\-Methode](../Topic/overwrite_buffer::resume_propagation%20Method.md)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. \(Überschreibt [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
|[overwrite\_buffer::send\_message\-Methode](../Topic/overwrite_buffer::send_message%20Method.md)|Übergibt eine Meldung synchron von einem `ISource`\-Block an diesen `overwrite_buffer`\-Meldungsblock.  Wird bei Aufruf durch einen Quellblock von der `send`\-Methode aufgerufen.|  
|[overwrite\_buffer::supports\_anonymous\_source\-Methode](../Topic/overwrite_buffer::supports_anonymous_source%20Method.md)|Überschreibt die `supports_anonymous_source`\-Methode, um anzugeben, dass der Block die Nachrichten verwenden kann, die es von einer Quelle bereitgestellt werden, die nicht verknüpft wird. Überschreibungen \( [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Hinweise  
 Ein `overwrite_buffer`\-Meldungsblock gibt Kopien der gespeicherten Meldungen an jedes Ziel weiter.  
  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [unbounded\_buffer\-Klasse](../Topic/unbounded_buffer%20Class.md)   
 [single\_assignment\-Klasse](../../../parallel/concrt/reference/single-assignment-class.md)