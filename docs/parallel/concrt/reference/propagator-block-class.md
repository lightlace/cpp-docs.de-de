---
title: "propagator_block-Klasse"
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
  - "agents/concurrency::propagator_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propagator_block-Klasse"
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: 21
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# propagator_block-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `propagator_block`\-Klasse ist eine abstrakte Basisklasse für Meldungsblöcke, die sowohl Quelle als auch Ziel sind.  Kombiniert die Funktion der `source_block`\-Klasse mit der Funktion der `target_block`\-Klasse.  
  
## Syntax  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class propagator_block : public source_block<_TargetLinkRegistry, _MessageProcessorType>, public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### Parameter  
 `_TargetLinkRegistry`  
 Die Linkregistrierung, die zum Speichern der Ziellinks verwendet werden soll.  
  
 `_SourceLinkRegistry`  
 Die Linkregistrierung, die zum Speichern der Quelllinks verwendet werden soll.  
  
 `_MessageProcessorType`  
 Der Prozessortyp für die Meldungsverarbeitung.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`source_iterator`|Der Typ des Iterators für den `source_link_manager` für dieses `propagator_block`\-Objekt.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[propagator\_block::propagator\_block\-Konstruktor](../Topic/propagator_block::propagator_block%20Constructor.md)|Erstellt ein `propagator_block`\-Objekt.|  
|[propagator\_block::~propagator\_block\-Destruktor](../Topic/propagator_block::~propagator_block%20Destructor.md)|Zerstört ein `propagator_block`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[propagator\_block::propagate\-Methode](../Topic/propagator_block::propagate%20Method.md)|Übergibt eine Meldung asynchron von einem Quellblock an diesen Zielblock.|  
|[propagator\_block::send\-Methode](../Topic/propagator_block::send%20Method.md)|Initiiert synchron eine Meldung an diesen Block.  Wird von einem `ISource`\-Block aufgerufen.  Wenn diese Funktion abgeschlossen wird, wurde die Meldung bereits an den Block weitergegeben.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[propagator\_block::decline\_incoming\_messages\-Methode](../Topic/propagator_block::decline_incoming_messages%20Method.md)|Gibt für den Block an, dass diese neuen Meldungen abgelehnt werden sollen.|  
|[propagator\_block::initialize\_source\_and\_target\-Methode](../Topic/propagator_block::initialize_source_and_target%20Method.md)|Initialisiert das Basisobjekt.  Insbesondere muss das `message_processor`\-Objekt initialisiert werden.|  
|[propagator\_block::link\_source\-Methode](../Topic/propagator_block::link_source%20Method.md)|Verknüpft einen angegebenen Quellblock mit diesem `propagator_block`\-Objekt.|  
|[propagator\_block::process\_input\_messages\-Methode](../Topic/propagator_block::process_input_messages%20Method.md)|Prozesseingabemeldungen.  Dies ist für Weitergabeblöcke nur hilfreich, die vom source\_block berechnen \(Überschreibungen [source\_block::process\_input\_messages](../Topic/source_block::process_input_messages%20Method.md).\)|  
|[propagator\_block::propagate\_message\-Methode](../Topic/propagator_block::propagate_message%20Method.md)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Meldung von einem `ISource`\-Block an dieses `propagator_block`\-Objekt.  Wird bei Aufruf durch einen Quellblock von der `propagate`\-Methode aufgerufen.|  
|[propagator\_block::register\_filter\-Methode](../Topic/propagator_block::register_filter%20Method.md)|Registriert eine Filtermethode, die für jede Meldung aufgerufen wird, die empfangen wurde.|  
|[propagator\_block::remove\_network\_links\-Methode](../Topic/propagator_block::remove_network_links%20Method.md)|Entfernt alle Quell\- und Zielnetzwerklinks von diesem `propagator_block`\-Objekt.|  
|[propagator\_block::send\_message\-Methode](../Topic/propagator_block::send_message%20Method.md)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Meldung von einem `ISource`\-Block an dieses `propagator_block`\-Objekt.  Wird bei Aufruf durch einen Quellblock von der `send`\-Methode aufgerufen.|  
|[propagator\_block::unlink\_source\-Methode](../Topic/propagator_block::unlink_source%20Method.md)|Hebt die Verknüpfung eines angegebenen Quellblocks mit diesem `propagator_block`\-Objekt auf.|  
|[propagator\_block::unlink\_sources\-Methode](../Topic/propagator_block::unlink_sources%20Method.md)|Hebt die Verknüpfung aller Quellblöcke mit diesem `propagator_block`\-Objekt auf. \(Überschreibt [ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md).\)|  
  
## Hinweise  
 Um mehrfache Vererbung zu vermeiden, erbt die `propagator_block`\-Klasse von der `source_block`\-Klasse und der abstrakten `ITarget`\-Namespace.  Die meisten Funktionen der `target_block`\-Klasse werden hier repliziert.  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 `propagator_block`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [source\_block\-Klasse](../../../parallel/concrt/reference/source-block-class.md)   
 [ITarget\-Klasse](../../../parallel/concrt/reference/itarget-class.md)