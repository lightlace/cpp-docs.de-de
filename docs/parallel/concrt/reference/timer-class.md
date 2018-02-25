---
title: Timer-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5263c8bf156f190ba5572eacd8ff327be5e3f7a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="timer-class"></a>Timer-Klasse
Ein `timer`-Meldungsblock ist ein `source_block` mit einem einzelnen Ziel, der nach Ablauf einer bestimmten Zeitspanne oder in bestimmten Intervallen eine Meldung an sein Ziel senden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Nutzlasttyp der ausgabemeldungen dieses Blocks.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[timer](#ctor)|Überladen. Erstellt eine `timer` Meldungsblock, die eine bestimmte Nachricht nach einem angegebenen Intervall ausgelöst werden.|  
|[~timer Destructor](#dtor)|Zerstört ein `timer` Meldungsblock.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[pause](#pause)|Beendet die `timer` Meldungsblock. Wenn sie wiederholte ist `timer` -Meldungsblock, er kann neu gestartet werden mit einem nachfolgenden `start()` aufrufen. Für nicht wiederholte Zeitgeber, hat dies denselben Effekt wie ein `stop` aufrufen.|  
|[start](#start)|Startet die `timer` Meldungsblock. Die angegebene Anzahl von Millisekunden, die danach aufgerufen wird, wird der angegebene Wert weitergegeben werden als downstream eine `message`.|  
|[stop](#stop)|Beendet die `timer` Meldungsblock.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `timer` -Meldungsblock übertragen des Besitzes an den Aufrufer.|  
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten die `timer` und vom Ziel übertragen des Besitzes an den Aufrufer reserviert.|  
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `timer` Meldungsblock.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Versucht, die Nachricht von erzeugten bieten die `timer` Block, um alle verknüpften Ziele.|  
|[release_message](#release_message)|Eine vorherige nachrichtenreservierung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `timer` Meldungsblock. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept_message"></a> accept_message 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `timer` -Meldungsblock übertragen des Besitzes an den Aufrufer.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` -Objekt, dass der Aufrufer nun den Besitz von aufweist.  
  
##  <a name="consume_message"></a> consume_message 

 Nimmt eine Meldung, die zuvor von Angeboten die `timer` und vom Ziel übertragen des Besitzes an den Aufrufer reserviert.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` konsumiert-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` -Objekt, dass der Aufrufer nun den Besitz von aufweist.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie `accept`, steht aber immer durch einen Aufruf von ist `reserve`.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `timer` Meldungsblock.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf das neu verknüpfte Ziel.  
  
##  <a name="pause"></a> Anhalten 

 Beendet die `timer` Meldungsblock. Wenn sie wiederholte ist `timer` -Meldungsblock, er kann neu gestartet werden mit einem nachfolgenden `start()` aufrufen. Für nicht wiederholte Zeitgeber, hat dies denselben Effekt wie ein `stop` aufrufen.  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Versucht, die Nachricht von erzeugten bieten die `timer` Block, um alle verknüpften Ziele.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="release_message"></a> release_message 

 Eine vorherige nachrichtenreservierung frei.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
##  <a name="reserve_message"></a> reserve_message 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `timer` Meldungsblock.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt reserviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem `reserve` aufgerufen wird, wenn er zurückgibt `true`, entweder `consume` oder `release` aufgerufen werden, um entweder übernehmen oder den Besitz der Nachricht.  
  
##  <a name="resume_propagation"></a> resume_propagation 

 Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="start"></a> Starten 

 Startet die `timer` Meldungsblock. Die angegebene Anzahl von Millisekunden, die danach aufgerufen wird, wird der angegebene Wert weitergegeben werden als downstream eine `message`.  
  
```
void start();
```  
  
##  <a name="stop"></a> Beenden 

 Beendet die `timer` Meldungsblock.  
  
```
void stop();
```  
  
##  <a name="ctor"></a> Timer 

 Erstellt eine `timer` Meldungsblock, die eine bestimmte Nachricht nach einem angegebenen Intervall ausgelöst werden.  
  
```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```  
  
### <a name="parameters"></a>Parameter  
 `_Ms`  
 Die Anzahl der Millisekunden, die verstreichen müssen, nach dem Aufruf von start für die angegebene Nachricht downstream weitergegeben werden.  
  
 `value`  
 Der Wert, der downstream weitergegeben wird, wenn der Zeitgeber abläuft.  
  
 `_PTarget`  
 Das Ziel, zu dem der Zeitgeber ihre Nachricht weitergegeben werden.  
  
 `_Repeating`  
 Bei "true", gibt an, dass der Zeitgeber in regelmäßigen Abständen ausgelöst werden, wird jede `_Ms` Millisekunden.  
  
 `_Scheduler`  
 Die `Scheduler` Objekt, in dem die Weiterleitungsaufgabe für, den `timer` -Meldungsblock geplant ist geplant ist.  
  
 `_ScheduleGroup`  
 Das `ScheduleGroup`-Objekt, in dem die Weiterleitungsaufgabe für den `timer`-Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Laufzeit mithilfe des Standardplaners aus, wenn Sie keinen angeben der `_Scheduler` oder `_ScheduleGroup` Parameter.  
  
##  <a name="dtor"></a> ~ Timer 

 Zerstört ein `timer` Meldungsblock.  
  
```
~timer();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
