---
title: Target_block-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 754bc6add99974ff204c977e47f35486cc830d95
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693977"
---
# <a name="targetblock-class"></a>target_block-Klasse
Die `target_block`-Klasse ist eine abstrakte Basisklasse, mit der grundlegende Linkmanagementfunktionalität und Fehlerüberprüfung für Nur-Ziel-Blöcke bereitgestellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>Parameter  
 `_SourceLinkRegistry`  
 Der Link-Registrierung für die Aufnahme der quellverknüpfungen verwendet werden.  
  
 `_MessageProcessorType`  
 Der Prozessortyp für die Nachrichtenverarbeitung.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`source_iterator`|Der Typ des Iterators für die `source_link_manager` dafür `target_block` Objekt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[target_block](#ctor)|Erstellt ein `target_block`-Objekt.|  
|[~ Target_block-Destruktor](#dtor)|Zerstört das `target_block`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[propagate](#propagate)|Übergibt eine Meldung asynchron aus ein Quellblock an diesen Zielblock.|  
|[Senden](#send)|Übergibt eine Meldung synchron aus ein Quellblock an diesen Zielblock.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[async_send](#async_send)|Sendet asynchron eine Nachricht zur Verarbeitung.|  
|[decline_incoming_messages](#decline_incoming_messages)|Zeigt den Block an, dass neue Nachrichten abgelehnt werden sollte.|  
|[enable_batched_processing](#enable_batched_processing)|Ermöglicht die Verarbeitung für diesen Block in einem Batch verarbeitet.|  
|[initialize_target](#initialize_target)|Initialisiert das Basisobjekt. Insbesondere die `message_processor` Objekt muss initialisiert werden.|  
|[link_source](#link_source)|Verknüpft einen angegebenen Quellblock mit diesem `target_block` Objekt.|  
|[process_input_messages](#process_input_messages)|Verarbeitet Nachrichten, die als Eingaben empfangen wurden.|  
|[process_message](#process_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse verarbeitet eine Nachricht, die von diesem akzeptiert wurde `target_block` Objekt.|  
|[propagate_message](#propagate_message)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Nachricht von einer `ISource` Block dieser `target_block` Objekt. Wird aufgerufen, indem die `propagate` Methode, wenn von ein Quellblock aufgerufen wird.|  
|[register_filter](#register_filter)|Registriert eine Filtermethode, die bei jeder empfangenen Nachricht aufgerufen wird.|  
|[remove_sources](#remove_sources)|Hebt die Verknüpfung aller Quellen nach einer Wartezeit von ausstehenden asynchronen Sendevorgang Vorgänge abgeschlossen.|  
|[send_message](#send_message)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Meldung von einer `ISource` Block dieser `target_block` Objekt. Wird aufgerufen, indem die `send` Methode, wenn von ein Quellblock aufgerufen wird.|  
|[sync_send](#sync_send)|Senden Sie eine Nachricht für die Verarbeitung synchron.|  
|[unlink_source](#unlink_source)|Hebt die Verknüpfung mit einer angegebenen Quellblock aus diesem `target_block` Objekt.|  
|[unlink_sources](#unlink_sources)|Hebt die Verknüpfung von diesem alle Quellblöcke `target_block` Objekt. (Überschreibt [ITarget:: Unlink_sources](itarget-class.md#unlink_sources).)|  
|[wait_for_async_sends](#wait_for_async_sends)|Wartet, bis alle asynchrone Weitergaben abgeschlossen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ITarget](itarget-class.md)  
  
 `target_block`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="async_send"></a> async_send 

 Sendet asynchron eine Nachricht zur Verarbeitung.  
  
```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf die zu sendende Nachricht.  
  
##  <a name="decline_incoming_messages"></a> decline_incoming_messages 

 Zeigt den Block an, dass neue Nachrichten abgelehnt werden sollte.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch den Destruktor, um sicherzustellen, dass neue Nachrichten abgelehnt werden, während Zerstörung ausgeführt wird.  
  
##  <a name="enable_batched_processing"></a> enable_batched_processing 

 Ermöglicht die Verarbeitung für diesen Block in einem Batch verarbeitet.  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_target"></a> initialize_target 

 Initialisiert das Basisobjekt. Insbesondere die `message_processor` Objekt muss initialisiert werden.  
  
```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Der Planer zum Planen von Aufgaben verwendet werden soll.  
  
 `_PScheduleGroup`  
 Der Planungsgruppe zum Planen von Aufgaben verwendet werden soll.  
  
##  <a name="link_source"></a> link_source 

 Verknüpft einen angegebenen Quellblock mit diesem `target_block` Objekt.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Ein Zeiger auf die `ISource` Block, der verknüpft werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `target_block` Objekt. Blöcke über miteinander verbunden werden soll die `link_target` Methode auf `ISource` -Blöcken, die aufgerufen wird, werden die `link_source` Methode auf dem entsprechenden Ziel.  
  
##  <a name="process_input_messages"></a> process_input_messages 

 Verarbeitet Nachrichten, die als Eingaben empfangen wurden.  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
  
##  <a name="process_message"></a> process_message 

 Ruft beim Überschreiben in einer abgeleiteten Klasse verarbeitet eine Nachricht, die von diesem akzeptiert wurde `target_block` Objekt.  
  
```
virtual void process_message(message<_Source_type> *);
```  
  
##  <a name="propagate"></a> weitergeben 

 Übergibt eine Meldung asynchron aus ein Quellblock an diesen Zielblock.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger auf der Quellblock die Nachricht anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, mit der Nachricht geschehen soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
##  <a name="propagate_message"></a> propagate_message 

 Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Nachricht von einer `ISource` Block dieser `target_block` Objekt. Wird aufgerufen, indem die `propagate` Methode, wenn von ein Quellblock aufgerufen wird.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger auf der Quellblock die Nachricht anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, mit der Nachricht geschehen soll.  
  
##  <a name="register_filter"></a> register_filter 

 Registriert eine Filtermethode, die bei jeder empfangenen Nachricht aufgerufen wird.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter`  
 Die Filtermethode.  
  
##  <a name="remove_sources"></a> remove_sources 

 Hebt die Verknüpfung aller Quellen nach einer Wartezeit von ausstehenden asynchronen Sendevorgang Vorgänge abgeschlossen.  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle Zielblöcke sollten diese Routine zum Entfernen von Quellen in ihrem Destruktor aufrufen.  
  
##  <a name="send"></a> Senden 

 Übergibt eine Meldung synchron aus ein Quellblock an diesen Zielblock.  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger auf der Quellblock die Nachricht anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, mit der Nachricht geschehen soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
 Mithilfe der `send` Methode außerhalb Nachrichteninitiierung und zur Weitergabe von Nachrichten innerhalb eines Netzwerks ist riskant und kann zu Deadlocks führen.  
  
 Wenn `send` zurückgibt, wurde die Nachricht entweder bereits akzeptiert und an den Zielblock übertragen, oder es wurde vom Ziel abgelehnt.  
  
##  <a name="send_message"></a> send_message 

 Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Meldung von einer `ISource` Block dieser `target_block` Objekt. Wird aufgerufen, indem die `send` Methode, wenn von ein Quellblock aufgerufen wird.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, mit der Nachricht geschehen soll.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt dieser Block `declined` , sofern nicht durch eine abgeleitete Klasse überschrieben.  
  
##  <a name="sync_send"></a> sync_send 

 Senden Sie eine Nachricht für die Verarbeitung synchron.  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf die zu sendende Nachricht.  
  
##  <a name="ctor"></a> target_block 

 Erstellt ein `target_block`-Objekt.  
  
```
target_block();
```  
  
##  <a name="dtor"></a> ~ Target_block 

 Zerstört das `target_block`-Objekt.  
  
```
virtual ~target_block();
```  
  
##  <a name="unlink_source"></a> unlink_source 

 Hebt die Verknüpfung mit einer angegebenen Quellblock aus diesem `target_block` Objekt.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Ein Zeiger auf die `ISource` Block, der aufgehoben werden soll.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 Hebt die Verknüpfung von diesem alle Quellblöcke `target_block` Objekt.  
  
```
virtual void unlink_sources();
```  
  
##  <a name="wait_for_async_sends"></a> wait_for_async_sends 

 Wartet, bis alle asynchrone Weitergaben abgeschlossen.  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Message-Block Destruktoren verwendet, um sicherzustellen, dass alle asynchronen Vorgänge Zeit vor dem Löschen des Blocks abgeschlossen hatten.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ITarget-Klasse](itarget-class.md)
