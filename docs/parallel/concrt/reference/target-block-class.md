---
title: "target_block-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::target_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "target_block-Klasse"
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# target_block-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `target_block`\-Klasse ist eine abstrakte Basisklasse, mit der grundlegende Linkmanagementfunktionalität und Fehlerüberprüfung für Nur\-Ziel\-Blöcke bereitgestellt werden.  
  
## Syntax  
  
```  
template<  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>  
>  
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### Parameter  
 `_SourceLinkRegistry`  
 Die Linkregistrierung, die zum Speichern der Quelllinks verwendet werden soll.  
  
 `_MessageProcessorType`  
 Der Prozessortyp für die Meldungsverarbeitung.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`source_iterator`|Der Typ des Iterators für den `source_link_manager` für das `target_block`\-Objekt.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[target\_block::target\_block\-Konstruktor](../Topic/target_block::target_block%20Constructor.md)|Erstellt ein `target_block`\-Objekt.|  
|[target\_block::~target\_block\-Destruktor](../Topic/target_block::~target_block%20Destructor.md)|Zerstört das `target_block`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[target\_block::propagate\-Methode](../Topic/target_block::propagate%20Method.md)|Übergibt eine Meldung asynchron von einem Quellblock an diesen Zielblock.|  
|[target\_block::send\-Methode](../Topic/target_block::send%20Method.md)|Übergibt eine Meldung synchron von einem Quellblock an diesen Zielblock.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[target\_block::async\_send\-Methode](../Topic/target_block::async_send%20Method.md)|Sendet asynchron eine Meldung zur Verarbeitung.|  
|[target\_block::decline\_incoming\_messages\-Methode](../Topic/target_block::decline_incoming_messages%20Method.md)|Gibt für den Block an, dass diese neuen Meldungen abgelehnt werden sollen.|  
|[target\_block::enable\_batched\_processing\-Methode](../Topic/target_block::enable_batched_processing%20Method.md)|Aktiviert verarbeitete Verarbeitung für diesen Block als Batch.|  
|[target\_block::initialize\_target\-Methode](../Topic/target_block::initialize_target%20Method.md)|Initialisiert das Basisobjekt.  Insbesondere muss das `message_processor`\-Objekt initialisiert werden.|  
|[target\_block::link\_source\-Methode](../Topic/target_block::link_source%20Method.md)|Verknüpft einen angegebenen Quellblock mit diesem `target_block`\-Objekt.|  
|[target\_block::process\_input\_messages\-Methode](../Topic/target_block::process_input_messages%20Method.md)|Verarbeitet Meldungen, die als Eingaben empfangen werden.|  
|[target\_block::process\_message\-Methode](../Topic/target_block::process_message%20Method.md)|Wenn Sie in einer abgeleiteten Klasse, Prozesse eine Meldung überschrieben werden, die von diesem `target_block`\-Objekt akzeptiert wurde.|  
|[target\_block::propagate\_message\-Methode](../Topic/target_block::propagate_message%20Method.md)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Meldung von einem `ISource`\-Block an dieses `target_block`\-Objekt.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[target\_block::register\_filter\-Methode](../Topic/target_block::register_filter%20Method.md)|Registriert eine Filtermethode, die für jede Meldung aufgerufen wird, die empfangen wurde.|  
|[target\_block::remove\_sources\-Methode](../Topic/target_block::remove_sources%20Method.md)|Hebt die Verknüpfung aller Quellen auf, nachdem auf den Abschluss ausstehender asynchroner Sendevorgänge gewartet wurde.|  
|[target\_block::send\_message\-Methode](../Topic/target_block::send_message%20Method.md)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Meldung von einem `ISource`\-Block an dieses `target_block`\-Objekt.  Wird bei Aufruf durch einen Quellblock von der `send`\-Methode aufgerufen.|  
|[target\_block::sync\_send\-Methode](../Topic/target_block::sync_send%20Method.md)|Sendet synchron eine Meldung zur Verarbeitung.|  
|[target\_block::unlink\_source\-Methode](../Topic/target_block::unlink_source%20Method.md)|Hebt die Verknüpfung eines angegebenen Quellblocks mit diesem `target_block`\-Objekt auf.|  
|[target\_block::unlink\_sources\-Methode](../Topic/target_block::unlink_sources%20Method.md)|Hebt die Verknüpfung aller Quellblöcke mit diesem `target_block`\-Objekt auf. \(Überschreibt [ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md).\)|  
|[target\_block::wait\_for\_async\_sends\-Methode](../Topic/target_block::wait_for_async_sends%20Method.md)|Wartet, bis alle asynchrone Weitergaben abgeschlossen sind.|  
  
## Vererbungshierarchie  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 `target_block`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget\-Klasse](../../../parallel/concrt/reference/itarget-class.md)