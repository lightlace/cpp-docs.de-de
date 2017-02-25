---
title: "timer-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::timer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timer-Klasse"
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# timer-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `timer`\-Meldungsblock ist ein `source_block` mit einem einzelnen Ziel, der nach Ablauf einer bestimmten Zeitspanne oder in bestimmten Intervallen eine Meldung an sein Ziel senden kann.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<_Type>>>;  
```  
  
#### Parameter  
 `_Type`  
 Der Nutzlasttyp der Ausgabemeldungen dieses Blocks.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[timer::timer\-Konstruktor](../Topic/timer::timer%20Constructor.md)|Überladen.  Erstellt einen `timer`\-Meldungsblock, der nach einem angegebenen Intervall eine angegebene Meldung auslöst.|  
|[timer::~timer\-Destruktor](../Topic/timer::~timer%20Destructor.md)|Zerstört einen `timer`\-Meldungsblock.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[timer::pause\-Methode](../Topic/timer::pause%20Method.md)|Beendet den `timer`\-Meldungsblock.  Wenn es ein wiederholender `timer`\-Meldungsblock ist, kann er mit einem nachfolgenden `start()`\-Aufruf neu gestartet werden.  Bei einmaligen Zeitgebern hat dies die gleichen Auswirkungen wie ein Aufruf von `stop`.|  
|[timer::start\-Methode](../Topic/timer::start%20Method.md)|Startet den `timer`\-Meldungsblock.  Nach der angegebenen Anzahl von Millisekunden nach dem Aufruf wird der angegebene Wert als `message` downstream weitergegeben.|  
|[timer::stop\-Methode](../Topic/timer::stop%20Method.md)|Beendet den `timer`\-Meldungsblock.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[timer::accept\_message\-Methode](../Topic/timer::accept_message%20Method.md)|Akzeptiert eine Meldung, die von diesem `timer`\-Meldungsblock angeboten wurde, und überträgt den Besitz an den Aufrufer.|  
|[timer::consume\_message\-Methode](../Topic/timer::consume_message%20Method.md)|Nimmt eine Meldung an, die zuvor von `timer` angeboten und vom Ziel reserviert wurde, und überträgt den Besitz an den Aufrufer.|  
|[timer::link\_target\_notification\-Methode](../Topic/timer::link_target_notification%20Method.md)|Ein Rückruf, der meldet, dass ein neues Ziel mit diesem `timer`\-Meldungsblock verknüpft wurde.|  
|[timer::propagate\_to\_any\_targets\-Methode](../Topic/timer::propagate_to_any_targets%20Method.md)|Versucht, die vom `timer`\-Block erzeugte Meldung allen verknüpften Zielen anzubieten.|  
|[timer::release\_message\-Methode](../Topic/timer::release_message%20Method.md)|Gibt die Reservierung einer vorherigen Meldung frei. \(Überschreibt [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[timer::reserve\_message\-Methode](../Topic/timer::reserve_message%20Method.md)|Reserviert eine Meldung, die zuvor von diesem `timer`\-Meldungsblock angeboten wurde. \(Überschreibt [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[timer::resume\_propagation\-Methode](../Topic/timer::resume_propagation%20Method.md)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. \(Überschreibt [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 `timer`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)