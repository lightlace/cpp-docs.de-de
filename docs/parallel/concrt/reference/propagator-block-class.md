---
title: Propagator_block-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
dev_langs:
- C++
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a34d127baf13434435c9ab359cf75b7b93c21f6d
ms.lasthandoff: 03/17/2017

---
# <a name="propagatorblock-class"></a>propagator_block-Klasse
Die `propagator_block`-Klasse ist eine abstrakte Basisklasse für Meldungsblöcke, die sowohl Quelle als auch Ziel sind. Kombiniert die Funktion der `source_block`-Klasse mit der Funktion der `target_block`-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
 public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>Parameter  
 `_TargetLinkRegistry`  
 Der Link-Registrierung verwendet werden, der die Ziellinks enthält.  
  
 `_SourceLinkRegistry`  
 Der Link-Registrierung für die Aufnahme der quellverknüpfungen verwendet werden.  
  
 `_MessageProcessorType`  
 Der Prozessortyp für die Verarbeitung.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`source_iterator`|Der Typ des Iterators für die `source_link_manager` für dieses `propagator_block`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[propagator_block](#ctor)|Erstellt ein `propagator_block`-Objekt.|  
|[~ Propagator_block-Destruktor](#dtor)|Zerstört ein `propagator_block`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[weitergeben](#propagate)|Übergibt eine Meldung asynchron von einem Quellblock an diesen Zielblock.|  
|[Senden](#send)|Initiiert synchron eine Meldung an diesen Block. Aufgerufen, indem eine `ISource` Block. Wenn diese Funktion abgeschlossen ist, wird die Nachricht bereits in den Block weitergegeben wurden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[decline_incoming_messages](#decline_incoming_messages)|Gibt den Block, dass neue Nachrichten abgelehnt werden sollte.|  
|[initialize_source_and_target](#initialize_source_and_target)|Initialisiert das Basisobjekt. Insbesondere das `message_processor` Objekt muss initialisiert werden.|  
|[link_source](#link_source)|Verknüpft einen angegebenen Quellblock mit diesem `propagator_block` Objekt.|  
|[process_input_messages](#process_input_messages)|Eingabe verarbeiten von Nachrichten. Dies ist nur nützlich für weitergabeblöcke, die von Source_block abgeleitet werden (überschreibt [source_block:: process_input_messages](source-block-class.md#process_input_messages).)|  
|[propagate_message](#propagate_message)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Nachricht von einer `ISource` -Block an diesen `propagator_block` Objekt. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.|  
|[register_filter](#register_filter)|Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.|  
|[remove_network_links](#remove_network_links)|Entfernt alle Quell- und Netzwerklinks aus diesem `propagator_block` Objekt.|  
|[send_message](#send_message)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Meldung von einer `ISource` -Block an diesen `propagator_block` Objekt. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.|  
|[unlink_source](#unlink_source)|Quellblocks einer angegebenen dies `propagator_block` Objekt.|  
|[unlink_sources](#unlink_sources)|Hebt die Verknüpfung aller Quellblöcke dies `propagator_block` Objekt. (Überschreibt [ITarget:: Unlink_sources](itarget-class.md#unlink_sources).)|  
  
## <a name="remarks"></a>Hinweise  
 Um mehrfache Vererbung zu vermeiden der `propagator_block` Klasse erbt von der `source_block` Klasse und `ITarget` abstrakte Klasse. Die meisten Funktionen in der `target_block` -Klasse werden hier repliziert.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 `propagator_block`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="decline_incoming_messages"></a>decline_incoming_messages 

 Gibt den Block, dass neue Nachrichten abgelehnt werden sollte.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch den Destruktor, um sicherzustellen, dass neue Nachrichten abgelehnt werden, während Zerstörung ausgeführt wird.  
  
##  <a name="initialize_source_and_target"></a>initialize_source_and_target 

 Initialisiert das Basisobjekt. Insbesondere das `message_processor` Objekt muss initialisiert werden.  
  
```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Der Planer zum Planen von Aufgaben verwendet werden.  
  
 `_PScheduleGroup`  
 Der Planungsgruppe zum Planen von Aufgaben verwendet werden.  
  
##  <a name="link_source"></a>link_source 

 Verknüpft einen angegebenen Quellblock mit diesem `propagator_block` Objekt.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Ein Zeiger auf die `ISource` -Block, der verknüpft werden soll.  
  
##  <a name="process_input_messages"></a>process_input_messages 

 Eingabe verarbeiten von Nachrichten. Dies ist nur nützlich für weitergabeblöcke, die von Source_block abgeleitet werden  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
  
##  <a name="propagate"></a>weitergeben 

 Übergibt eine Meldung asynchron von einem Quellblock an diesen Zielblock.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
### <a name="remarks"></a>Hinweise  
 Die `propagate` -Methode für die von einem verknüpften Quellblock Zielblock aufgerufen wird. Stellt eine asynchrone Aufgabe, die Nachricht zu behandeln, wenn nicht bereits in der Warteschlange steht oder ausführen.  
  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder der `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
##  <a name="propagate_message"></a>propagate_message 

 Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Nachricht von einer `ISource` -Block an diesen `propagator_block` Objekt. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
##  <a name="ctor"></a>propagator_block 

 Erstellt ein `propagator_block`-Objekt.  
  
```
propagator_block();
```  
  
##  <a name="dtor"></a>~ Propagator_block 

 Zerstört ein `propagator_block`-Objekt.  
  
```
virtual ~propagator_block();
```  
  
##  <a name="register_filter"></a>register_filter 

 Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter`  
 Die Filtermethode.  
  
##  <a name="remove_network_links"></a>remove_network_links 

 Entfernt alle Quell- und Netzwerklinks aus diesem `propagator_block` Objekt.  
  
```
void remove_network_links();
```  
  
##  <a name="send"></a>Senden 

 Initiiert synchron eine Meldung an diesen Block. Aufgerufen, indem eine `ISource` Block. Wenn diese Funktion abgeschlossen ist, wird die Nachricht bereits in den Block weitergegeben wurden.  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder der `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
##  <a name="send_message"></a>send_message 

 Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Meldung von einer `ISource` -Block an diesen `propagator_block` Objekt. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt dieser Block `declined` , sofern nicht durch eine abgeleitete Klasse überschrieben.  
  
##  <a name="unlink_source"></a>unlink_source 

 Quellblocks einer angegebenen dies `propagator_block` Objekt.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Ein Zeiger auf die `ISource` -Block, der aufgehoben werden soll.  
  
##  <a name="unlink_sources"></a>unlink_sources 

 Hebt die Verknüpfung aller Quellblöcke dies `propagator_block` Objekt.  
  
```
virtual void unlink_sources();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Source_block-Klasse](source-block-class.md)   
 [ITarget-Klasse](itarget-class.md)

