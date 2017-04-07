---
title: Source_block-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
caps.latest.revision: 20
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
ms.openlocfilehash: b31f02559da7e4396926ce7611a6907c32693121
ms.lasthandoff: 03/17/2017

---
# <a name="sourceblock-class"></a>source_block-Klasse
Die `source_block`-Klasse ist eine abstrakte Basisklasse ausschließlich für Quellblöcke. Die Klasse stellt grundlegende Linkmanagementfunktionalität sowie allgemeine Fehlerüberprüfungen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```  
  
#### <a name="parameters"></a>Parameter  
 `_TargetLinkRegistry`  
 Link-Registrierung verwendet werden, der die Ziellinks enthält.  
  
 `_MessageProcessorType`  
 Der Prozessortyp für die Verarbeitung.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`target_iterator`|Der Iterator zum Durchlaufen der verbundenen Ziele.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[source_block](#ctor)|Erstellt ein `source_block`-Objekt.|  
|[~ Source_block-Destruktor](#dtor)|Zerstört das `source_block`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[akzeptieren](#accept)|Akzeptiert eine Meldung, die von diesem angeboten wurde `source_block` Objekt überträgt den Besitz an den Aufrufer.|  
|[acquire_ref](#acquire_ref)|Ruft eine Verweisanzahl für dieses `source_block` -Objekt, um das Löschen zu verhindern.|  
|[Nutzen](#consume)|Nimmt eine Meldung, die zuvor von diesem angebotenen `source_block` -Objekt und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.|  
|[link_target](#link_target)|Verknüpft einen Zielblock mit diesem `source_block` Objekt.|  
|[release](#release)|Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[release_ref](#release_ref)|Gibt einen Verweiszähler für das `source_block` Objekt.|  
|[reserve](#reserve)|Reserviert eine Meldung, die zuvor von diesem angebotenen `source_block` Objekt.|  
|[unlink_target](#unlink_target)|Hebt die Verknüpfung mit einem Zielblock aus diesem `source_block` Objekt.|  
|[unlink_targets](#unlink_targets)|Hebt die Verknüpfung aller Zielblöcke mit diesem `source_block` Objekt. (Überschreibt [ISource:: Unlink_targets](isource-class.md#unlink_targets).)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accept_message](#accept_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine angebotene Nachricht von der Quelle. Meldungsblöcke sollten überschreiben diese Methode zum Überprüfen der `_MsgId` und eine Meldung zurückgegeben.|  
|[async_send](#async_send)|Asynchron Warteschlangen Nachrichten und eine Weiterleitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde|  
|[consume_message](#consume_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse nimmt eine Meldung, die zuvor reserviert wurde.|  
|[enable_batched_processing](#enable_batched_processing)|Für diesen Block verarbeiten Batch aktiviert.|  
|[initialize_source](#initialize_source)|Initialisiert die `message_propagator` innerhalb dieses `source_block`.|  
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `source_block` Objekt.|  
|[process_input_messages](#process_input_messages)|Eingabe verarbeiten von Nachrichten. Dies ist nur nützlich für weitergabeblöcke, die von Source_block abgeleitet werden|  
|[propagate_output_messages](#propagate_output_messages)|Weitergabe von Nachrichten an Ziele.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Ruft beim Überschreiben in einer abgeleiteten Klasse wird die angegebene Nachricht oder alle verknüpften Zielen weitergegeben. Dies ist die wichtigste Weitergabe Routine für Meldungsblöcke.|  
|[release_message](#release_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Reservierung einer vorherigen Meldung frei.|  
|[remove_targets](#remove_targets)|Entfernt alle Ziellinks für diesen Quellblock. Dies sollte vom Destruktor aufgerufen werden.|  
|[reserve_message](#reserve_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse reserviert eine Meldung, die zuvor von diesem angebotenen `source_block` Objekt.|  
|[resume_propagation](#resume_propagation)|Beim Überschreiben in einer abgeleiteten Klasse setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde.|  
|[sync_send](#sync_send)|Synchrone Warteschlangen Nachrichten und eine Weiterleitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde.|  
|[unlink_target_notification](#unlink_target_notification)|Ein Rückruf, der benachrichtigt, dass ein Ziel aus dieser aufgehoben wurde `source_block` Objekt.|  
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Wartet, bis alle asynchrone Weitergaben abgeschlossen. Dieser Wartetyp Propagator-spezifische Drehfeld wird in Destruktoren Nachrichtenblöcke verwendet, um sicherzustellen, dass alle asynchrone Weitergaben Zeit vor dem Zerstören des Blocks beendet haben.|  
  
## <a name="remarks"></a>Hinweise  
 Nachrichtenblöcke sollte aus diesem Block zu nutzen und die Synchronisierung zur Verfügung gestellt, die von dieser Klasse abgeleitet werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 `source_block`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept"></a>akzeptieren 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `source_block` Objekt überträgt den Besitz an den Aufrufer.  
  
```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_PTarget` ist `NULL`.  
  
 Die `accept` Methode wird von einem Ziel aufgerufen, während eine Nachricht von diesem angeboten wird `ISource` Block. Der zurückgegebene möglicherweise nicht das Übergeben der `propagate` Methode der `ITarget` zu blockieren, wenn diese Quelle entscheidet, eine Kopie der Nachricht zu erstellen.  
  
##  <a name="accept_message"></a>accept_message 

 Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine angebotene Nachricht von der Quelle. Meldungsblöcke sollten überschreiben diese Methode zum Überprüfen der `_MsgId` und eine Meldung zurückgegeben.  
  
```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die Common Language Runtime-Objektidentität des der `message` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Um den Besitz übertragen, sollte der ursprünglichen Nachrichtenzeiger zurückgegeben werden. Um den Besitz beizubehalten, muss eine Kopie der Nachrichtennutzlast erstellt und zurückgegeben werden.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Ruft eine Verweisanzahl für dieses `source_block` -Objekt, um das Löschen zu verhindern.  
  
```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, ist die `link_target` Methode.  
  
##  <a name="async_send"></a>async_send 

 Asynchron Warteschlangen Nachrichten und eine Weiterleitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde  
  
```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf ein `message` Objekt, das asynchron gesendet.  
  
##  <a name="consume"></a>Nutzen 

 Nimmt eine Meldung, die zuvor von diesem angebotenen `source_block` -Objekt und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.  
  
```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` des reservierten `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `consume` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_PTarget` ist `NULL`.  
  
 Die Methode löst eine [Bad_target](bad-target-class.md) Ausnahme wenn der Parameter `_PTarget` ist nicht das Ziel darstellt, die aufgerufen `reserve`.  
  
 Die `consume` Methode ähnelt `accept`, steht aber immer nach einem Aufruf werden müssen `reserve` zurückgegebenen `true`.  
  
##  <a name="consume_message"></a>consume_message 

 Ruft beim Überschreiben in einer abgeleiteten Klasse nimmt eine Meldung, die zuvor reserviert wurde.  
  
```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt verarbeitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie `accept`, steht aber immer nach einem Aufruf von ist `reserve`.  
  
##  <a name="enable_batched_processing"></a>enable_batched_processing 

 Für diesen Block verarbeiten Batch aktiviert.  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_source"></a>initialize_source 

 Initialisiert die `message_propagator` innerhalb dieses `source_block`.  
  
```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Der Planer zum Planen von Aufgaben verwendet werden.  
  
 `_PScheduleGroup`  
 Der Planungsgruppe zum Planen von Aufgaben verwendet werden.  
  
##  <a name="link_target"></a>link_target 

 Verknüpft einen Zielblock mit diesem `source_block` Objekt.  
  
```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Herstellen eines Links `source_block` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_PTarget` ist `NULL`.  
  
##  <a name="link_target_notification"></a>link_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `source_block` Objekt.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```  
  
##  <a name="process_input_messages"></a>process_input_messages 

 Eingabe verarbeiten von Nachrichten. Dies ist nur nützlich für weitergabeblöcke, die von Source_block abgeleitet werden  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
  
##  <a name="propagate_output_messages"></a>propagate_output_messages 

 Weitergabe von Nachrichten an Ziele.  
  
```
virtual void propagate_output_messages();
```  
  
##  <a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Ruft beim Überschreiben in einer abgeleiteten Klasse wird die angegebene Nachricht oder alle verknüpften Zielen weitergegeben. Dies ist die wichtigste Weitergabe Routine für Meldungsblöcke.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf die Meldung, die weitergeleitet werden soll.  
  
##  <a name="release"></a>Version 

 Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` des reservierten `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `release` Methode.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_PTarget` ist `NULL`.  
  
 Die Methode löst eine [Bad_target](bad-target-class.md) Ausnahme wenn der Parameter `_PTarget` ist nicht das Ziel darstellt, die aufgerufen `reserve`.  
  
##  <a name="release_message"></a>release_message 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Reservierung einer vorherigen Meldung frei.  
  
```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
##  <a name="release_ref"></a>release_ref 

 Gibt einen Verweiszähler für das `source_block` Objekt.  
  
```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierte Ressourcen freizugeben.  
  
##  <a name="remove_targets"></a>remove_targets 

 Entfernt alle Ziellinks für diesen Quellblock. Dies sollte vom Destruktor aufgerufen werden.  
  
```
void remove_targets();
```  
  
##  <a name="reserve"></a>Reservieren 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `source_block` Objekt.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können viele Ursachen haben, z. B. fehlschlagen: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, konnte die Quelle Reservierungen verweigern und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_PTarget` ist `NULL`.  
  
 Nach dem Aufruf von `reserve`, das erfolgreich ist, rufen Sie entweder `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="reserve_message"></a>reserve_message 

 Ruft beim Überschreiben in einer abgeleiteten Klasse reserviert eine Meldung, die zuvor von diesem angebotenen `source_block` Objekt.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt reserviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem `reserve` wird aufgerufen, wenn die Rückgabe `true`, `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.  
  
##  <a name="resume_propagation"></a>resume_propagation 

 Beim Überschreiben in einer abgeleiteten Klasse setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde.  
  
```
virtual void resume_propagation() = 0;
```  
  
##  <a name="ctor"></a>source_block 

 Erstellt ein `source_block`-Objekt.  
  
```
source_block();
```  
  
##  <a name="dtor"></a>~ Source_block 

 Zerstört das `source_block`-Objekt.  
  
```
virtual ~source_block();
```  
  
##  <a name="sync_send"></a>sync_send 

 Synchrone Warteschlangen Nachrichten und eine Weiterleitungsaufgabe beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf ein `message` Objekt, das synchron gesendet.  
  
##  <a name="unlink_target"></a>unlink_target 

 Hebt die Verknüpfung mit einem Zielblock aus diesem `source_block` Objekt.  
  
```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Aufheben der Verknüpfung von diesem `source_block` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_PTarget` ist `NULL`.  
  
##  <a name="unlink_target_notification"></a>unlink_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein Ziel aus dieser aufgehoben wurde `source_block` Objekt.  
  
```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Die `ITarget` Block, aufgehoben wurde.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Hebt die Verknüpfung aller Zielblöcke mit diesem `source_block` Objekt.  
  
```
virtual void unlink_targets();
```  
  
##  <a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends 

 Wartet, bis alle asynchrone Weitergaben abgeschlossen. Dieser Wartetyp Propagator-spezifische Drehfeld wird in Destruktoren Nachrichtenblöcke verwendet, um sicherzustellen, dass alle asynchrone Weitergaben Zeit vor dem Zerstören des Blocks beendet haben.  
  
```
void wait_for_outstanding_async_sends();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ISource-Klasse](isource-class.md)

