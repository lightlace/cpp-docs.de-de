---
title: Single_assignment-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::single_assignment
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: a2a500353b06219713c5d9f3e68f82b247c1604f
ms.lasthandoff: 02/24/2017

---
# <a name="singleassignment-class"></a>single_assignment-Klasse
Ein `single_assignment`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine einzelne, einmal beschreibbare `message` speichern kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Nutzlasttyp der Nachricht gespeichert und vom Puffer weitergegeben.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Single_assignment-Konstruktor](#ctor)|Überladen. Erstellt eine `single_assignment` Meldungsblocks.|  
|[~ Single_assignment-Destruktor](#dtor)|Zerstört die `single_assignment` Meldungsblocks.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Has_value-Methode](#has_value)|Überprüft, ob diese `single_assignment` -Meldungsblock noch mit einem Wert initialisiert wurde.|  
|[Wert-Methode](#value)|Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `single_assignment` Meldungsblocks.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accept_message-Methode](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `single_assignment` -Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.|  
|[Consume_message-Methode](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten der `single_assignment` und reservierte durch das Ziel, eine Kopie der Nachricht an den Aufrufer zurückgegeben.|  
|[Link_target_notification-Methode](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `single_assignment` Meldungsblocks.|  
|[Propagate_message-Methode](#propagate_message)|Übergibt eine Nachricht asynchron eine `ISource` -Block an diesen `single_assignment` Meldungsblocks. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.|  
|[Propagate_to_any_targets-Methode](#propagate_to_any_targets)|Stellen die `message``_PMessage` in diesem `single_assignment` -Meldungsblock ein und bietet sie allen verknüpften Zielen.|  
|[Release_message-Methode](#release_message)|Gibt die Reservierung einer vorherigen Meldung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|  
|[Reserve_message-Methode](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `single_assignment` Meldungsblocks. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[Resume_propagation-Methode](#resume_propagation)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
|[Send_message-Methode](#send_message)|Übergibt synchron eine Meldung von einer `ISource` -Block an diesen `single_assignment` Meldungsblocks. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `single_assignment` -Meldungsblock Eingabeelementen Kopien jedes Ziel der Nachricht.  
  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `single_assignment`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `single_assignment` -Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `single_assignment` -Meldungsblock gibt Kopien der Meldung an ihre Ziele, statt den Besitz der gerade vorliegenden Meldung zu übertragen.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Nimmt eine Meldung, die zuvor von Angeboten der `single_assignment` und reservierte durch das Ziel, eine Kopie der Nachricht an den Aufrufer zurückgegeben.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt verarbeitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie `accept`, steht aber immer nach einem Aufruf von ist `reserve`.  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 Überprüft, ob diese `single_assignment` -Meldungsblock noch mit einem Wert initialisiert wurde.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Block einen Wert empfangen hat `false` andernfalls.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `single_assignment` Meldungsblocks.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf das neu verknüpfte Ziel.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 Übergibt eine Nachricht asynchron eine `ISource` -Block an diesen `single_assignment` Meldungsblocks. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.  
  
```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Stellen die `message``_PMessage` in diesem `single_assignment` -Meldungsblock ein und bietet sie allen verknüpften Zielen.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf eine `message` , die von diesem `single_assignment` -Meldungsblock Besitz übernommen hat.  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Gibt die Reservierung einer vorherigen Meldung frei.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `single_assignment` Meldungsblocks.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt reserviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem `reserve` wird aufgerufen, wenn die Rückgabe `true`, `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 Übergibt synchron eine Meldung von einer `ISource` -Block an diesen `single_assignment` Meldungsblocks. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.  
  
```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
##  <a name="a-namectora-singleassignment"></a><a name="ctor"></a>single_assignment 

 Erstellt eine `single_assignment` Meldungsblocks.  
  
```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter`  
 Eine Filterfunktion, die bestimmt, ob die angebotene Nachrichten akzeptiert werden sollen.  
  
 `_PScheduler`  
 Das `Scheduler`-Objekt, in dem die Weiterleitungsaufgabe für den `single_assignment`-Meldungsblock geplant ist.  
  
 `_PScheduleGroup`  
 Das `ScheduleGroup`-Objekt, in dem die Weiterleitungsaufgabe für den `single_assignment`-Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.  
  
 Der Typ `filter_method` ist ein Funktionselement mit der Signatur `bool (T const &)` die aufgerufen wird, von diesem `single_assignment` -Meldungsblock zu bestimmen, ob eine bereitgestellte Meldung akzeptiert werden sollen.  
  
##  <a name="a-namedtora-singleassignment"></a><a name="dtor"></a>~ Single_assignment 

 Zerstört die `single_assignment` Meldungsblocks.  
  
```
~single_assignment();
```  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>Wert 

 Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `single_assignment` Meldungsblocks.  
  
```
T const& value();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Nutzlast der gespeicherten Meldung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wartet, bis eine Meldung eintrifft, wenn derzeit keine Meldung im gespeichert ist die `single_assignment` Meldungsblocks.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Overwrite_buffer-Klasse](overwrite-buffer-class.md)   
 [Unbounded_buffer-Klasse](unbounded-buffer-class.md)


