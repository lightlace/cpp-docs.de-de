---
title: Timer-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42d77386350dab3e8714b00f8e55143b2a486e79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091659"
---
# <a name="timer-class"></a>Timer-Klasse
Ein `timer`-Meldungsblock ist ein `source_block` mit einem einzelnen Ziel, der nach Ablauf einer bestimmten Zeitspanne oder in bestimmten Intervallen eine Meldung an sein Ziel senden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>Parameter  
*T*<br/>
Der Nutzlasttyp der ausgabemeldungen dieses Blocks.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Timer](#ctor)|Überladen. Erstellt eine `timer` Meldungsblock, die eine bestimmte Nachricht nach einem angegebenen Intervall ausgelöst werden.|  
|[~ Timer-Destruktor](#dtor)|Zerstört eine `timer` Meldungsblock.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Anhalten](#pause)|Beendet die `timer` Meldungsblock. Ist dies eine wiederholte `timer` -Meldungsblock, es kann neu gestartet werden mit einer nachfolgenden `start()` aufrufen. Für nicht wiederholte Zeitgeber, dies hat dieselbe Wirkung wie ein `stop` aufrufen.|  
|[start](#start)|Startet die `timer` Meldungsblock. Die angegebene Anzahl von Millisekunden nach dem aufgerufen wird, wird der angegebene Wert wird übernommen downstream als eine `message`.|  
|[Beenden](#stop)|Beendet die `timer` Meldungsblock.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `timer` Meldungsblock, überträgt den Besitz an den Aufrufer.|  
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten die `timer` und vom Ziel übertragen des Besitzes an den Aufrufer reservierte.|  
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `timer` Meldungsblock.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Versucht, die Meldung bieten die `timer` Block, um alle verknüpften Ziele.|  
|[release_message](#release_message)|Gibt die nachrichtenreservierung einer vorherigen frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `timer` Meldungsblock. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
  
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

 Akzeptiert eine Meldung, die von diesem angeboten wurde `timer` Meldungsblock, überträgt den Besitz an den Aufrufer.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.  
  
##  <a name="consume_message"></a> consume_message 

 Nimmt eine Meldung, die zuvor von Angeboten die `timer` und vom Ziel übertragen des Besitzes an den Aufrufer reservierte.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von der `message` -Objekt verarbeitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie `accept`, steht aber immer durch einen Aufruf von ist `reserve`.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `timer` Meldungsblock.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_PTarget*<br/>
Ein Zeiger auf das neu verknüpften Ziel.  
  
##  <a name="pause"></a> Anhalten 

 Beendet die `timer` Meldungsblock. Ist dies eine wiederholte `timer` -Meldungsblock, es kann neu gestartet werden mit einer nachfolgenden `start()` aufrufen. Für nicht wiederholte Zeitgeber, dies hat dieselbe Wirkung wie ein `stop` aufrufen.  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Versucht, die Meldung bieten die `timer` Block, um alle verknüpften Ziele.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="release_message"></a> release_message 

 Gibt die nachrichtenreservierung einer vorherigen frei.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
##  <a name="reserve_message"></a> reserve_message 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `timer` Meldungsblock.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt reserviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem `reserve` aufgerufen wird, wenn zurückgegeben `true`, entweder `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.  
  
##  <a name="resume_propagation"></a> resume_propagation 

 Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="start"></a> Starten 

 Startet die `timer` Meldungsblock. Die angegebene Anzahl von Millisekunden nach dem aufgerufen wird, wird der angegebene Wert wird übernommen downstream als eine `message`.  
  
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
*_Ms*<br/>
Die Anzahl der Millisekunden, die verstreichen müssen, nach dem Aufruf starten, für die angegebene Nachricht downstream weitergegeben werden.  
  
*Wert*<br/>
Der Wert, der downstream weitergegeben wird, wenn der Zeitgeber abläuft.  
  
*_PTarget*<br/>
Das Ziel, an dem der Timer die die Meldung weitergegeben.  
  
*_Repeating*<br/>
True gibt an, dass der Zeitgeber, das in regelmäßigen Abständen ausgelöst werden alle `_Ms` Millisekunden.  
  
*_Scheduler*<br/>
Die `Scheduler` Objekt, in dem die Weiterleitungsaufgabe für, den `timer` -Meldungsblock geplant ist geplant ist.  
  
*_ScheduleGroup*<br/>
Das `ScheduleGroup`-Objekt, in dem die Weiterleitungsaufgabe für den `timer`-Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Laufzeit mithilfe des Standardplaners aus, wenn Sie keinen angeben der `_Scheduler` oder `_ScheduleGroup` Parameter.  
  
##  <a name="dtor"></a> ~ Timer 

 Zerstört eine `timer` Meldungsblock.  
  
```
~timer();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
