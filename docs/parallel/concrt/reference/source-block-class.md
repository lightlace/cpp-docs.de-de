---
title: "source_block-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::source_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source_block-Klasse"
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# source_block-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `source_block`\-Klasse ist eine abstrakte Basisklasse ausschließlich für Quellblöcke.  Die Klasse stellt grundlegende Linkmanagementfunktionalität sowie allgemeine Fehlerüberprüfungen bereit.  
  
## Syntax  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;  
```  
  
#### Parameter  
 `_TargetLinkRegistry`  
 Linkregistrierung, die zum Speichern der Ziellinks verwendet werden soll.  
  
 `_MessageProcessorType`  
 Prozessortyp zur Meldungsverarbeitung.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`target_iterator`|Der Iterator zum Durchlaufen der verbundenen Ziele.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[source\_block::source\_block\-Konstruktor](../Topic/source_block::source_block%20Constructor.md)|Erstellt ein `source_block`\-Objekt.|  
|[source\_block::~source\_block\-Destruktor](../Topic/source_block::~source_block%20Destructor.md)|Zerstört das `source_block`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[source\_block::accept\-Methode](../Topic/source_block::accept%20Method.md)|Akzeptiert eine Meldung, die von diesem `source_block`\-Objekt angeboten wurde, und überträgt den Besitz an den Aufrufer.|  
|[source\_block::acquire\_ref\-Methode](../Topic/source_block::acquire_ref%20Method.md)|Ruft eine Verweisanzahl für dieses `source_block`\-Objekt ab, um das Löschen zu verhindern.|  
|[source\_block::consume\-Methode](../Topic/source_block::consume%20Method.md)|Nimmt eine Meldung an, die zuvor von diesem `source_block`\-Objekt angeboten und vom Ziel erfolgreich reserviert wurde, und überträgt den Besitz an den Aufrufer.|  
|[source\_block::link\_target\-Methode](../Topic/source_block::link_target%20Method.md)|Verknüpft einen Zielblock mit diesem `source_block`\-Objekt.|  
|[source\_block::release\-Methode](../Topic/source_block::release%20Method.md)|Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[source\_block::release\_ref\-Methode](../Topic/source_block::release_ref%20Method.md)|Gibt auf diesem `source_block`\-Objekt einen Verweiszähler frei.|  
|[source\_block::reserve\-Methode](../Topic/source_block::reserve%20Method.md)|Reserviert eine Meldung, die zuvor von diesem `source_block`\-Objekt angeboten wurde.|  
|[source\_block::unlink\_target\-Methode](../Topic/source_block::unlink_target%20Method.md)|Hebt die Verknüpfung eines Zielblocks mit diesem `source_block`\-Objekt auf.|  
|[source\_block::unlink\_targets\-Methode](../Topic/source_block::unlink_targets%20Method.md)|Hebt die Verknüpfung aller Zielblöcke mit diesem `source_block`\-Objekt auf. \(Überschreibt [ISource::unlink\_targets](../Topic/ISource::unlink_targets%20Method.md).\)|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[source\_block::accept\_message\-Methode](../Topic/source_block::accept_message%20Method.md)|Akzeptiert beim Überschreiben in einer abgeleiteten Klasse eine von der Quelle akzeptierte Meldung.  Meldungsblöcke sollten diese Methode überschreiben, um `_MsgId` zu überprüfen und eine Meldung zurückzugeben.|  
|[source\_block::async\_send\-Methode](../Topic/source_block::async_send%20Method.md)|Stellt asynchron Meldungen in die Warteschlange ein und startet eine Weiterleitungsaufgabe, wenn dies nicht bereits geschehen ist.|  
|[source\_block::consume\_message\-Methode](../Topic/source_block::consume_message%20Method.md)|Verwendet beim Überschreiben in einer abgeleiteten Klasse eine Meldung, die zuvor reserviert wurde.|  
|[source\_block::enable\_batched\_processing\-Methode](../Topic/source_block::enable_batched_processing%20Method.md)|Aktiviert verarbeitete Verarbeitung für diesen Block als Batch.|  
|[source\_block::initialize\_source\-Methode](../Topic/source_block::initialize_source%20Method.md)|Initialisiert `message_propagator` in diesem `source_block`.|  
|[source\_block::link\_target\_notification\-Methode](../Topic/source_block::link_target_notification%20Method.md)|Ein Rückruf, der meldet, dass ein neues Ziel mit diesem `source_block`\-Objekt verknüpft wurde.|  
|[source\_block::process\_input\_messages\-Methode](../Topic/source_block::process_input_messages%20Method.md)|Prozesseingabemeldungen.  Dies ist für Weitergabeblöcke nur hilfreich, die vom source\_block abgeleitet werden|  
|[source\_block::propagate\_output\_messages\-Methode](../Topic/source_block::propagate_output_messages%20Method.md)|Weiten Sie Meldungen in Ziele.|  
|[source\_block::propagate\_to\_any\_targets\-Methode](../Topic/source_block::propagate_to_any_targets%20Method.md)|Gibt beim Überschreiben in einer abgeleiteten Klasse die angegebene Meldung an ein oder alle verknüpfte Ziele weiter.  Dies ist die Hauptweitergaberoutine für Meldungsblöcke.|  
|[source\_block::release\_message\-Methode](../Topic/source_block::release_message%20Method.md)|Gibt beim Überschreiben in einer abgeleiteten Klasse eine frühere Meldungsreservierung frei.|  
|[source\_block::remove\_targets\-Methode](../Topic/source_block::remove_targets%20Method.md)|Entfernt alle Ziellinks für diesen Quellblock.  Dies sollte vom Destruktor aufgerufen werden.|  
|[source\_block::reserve\_message\-Methode](../Topic/source_block::reserve_message%20Method.md)|Reserviert beim Überschreiben in einer abgeleiteten Klasse eine Meldung, die von diesem `source_block`\-Objekt angeboten wurde.|  
|[source\_block::resume\_propagation\-Methode](../Topic/source_block::resume_propagation%20Method.md)|Setzt beim Überschreiben in einer abgeleiteten Klasse die Weiterleitung nach der Freigabe einer Reservierung fort.|  
|[source\_block::sync\_send\-Methode](../Topic/source_block::sync_send%20Method.md)|Stellt synchron Meldungen in die Warteschlange ein und startet eine Weiterleitungsaufgabe, wenn dies nicht bereits geschehen ist.|  
|[source\_block::unlink\_target\_notification\-Methode](../Topic/source_block::unlink_target_notification%20Method.md)|Ein Rückruf, der meldet, dass eine Zielverknüpfung von diesem `source_block`\-Objekt entfernt wurde.|  
|[source\_block::wait\_for\_outstanding\_async\_sends\-Methode](../Topic/source_block::wait_for_outstanding_async_sends%20Method.md)|Wartet, bis alle asynchrone Weitergaben abgeschlossen sind.  Dieser weiterleitungsspezifischer Spin\-Wait wird in Destruktoren von Meldungsblöcken verwendet, um sicherzustellen, dass alle asynchronen Weiterleitungen genügend Zeit zum Beenden erhalten, bevor der Block zerstört wird.|  
  
## Hinweise  
 Meldungsblöcke sollten von diesem Block abgeleitet werden, um das Linkmanagement und die Synchronisierung nutzen zu können, die von dieser Klasse bereitgestellt werden.  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `source_block`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource\-Klasse](../../../parallel/concrt/reference/isource-class.md)