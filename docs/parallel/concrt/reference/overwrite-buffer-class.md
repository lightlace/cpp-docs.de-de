---
title: Overwrite_buffer-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::overwrite_buffer
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 22
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
ms.openlocfilehash: 02a4968ef88d8a6181a4d5412f894dce100ba7b3
ms.lasthandoff: 02/24/2017

---
# <a name="overwritebuffer-class"></a>overwrite_buffer-Klasse
Ein `overwrite_buffer`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der jeweils eine einzelne Meldung speichern kann. Neue Meldungen überschreiben zuvor Gespeicherte.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Nutzlasttyp der Nachrichten gespeichert, und der Puffer weitergegeben.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Overwrite_buffer-Konstruktor](#ctor)|Überladen. Erstellt ein `overwrite_buffer` Meldungsblocks.|  
|[~ Overwrite_buffer-Destruktor](#dtor)|Zerstört die `overwrite_buffer` Meldungsblocks.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Has_value-Methode](#has_value)|Überprüft, ob diese `overwrite_buffer` -Meldungsblock ist einen Wert noch nicht.|  
|[Wert-Methode](#value)|Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `overwrite_buffer` Meldungsblocks.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accept_message-Methode](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `overwrite_buffer` -Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.|  
|[Consume_message-Methode](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten der `overwrite_buffer` -Meldungsblock und reserviert durch das Ziel, eine Kopie der Nachricht an den Aufrufer zurückgegeben.|  
|[Link_target_notification-Methode](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `overwrite_buffer` Meldungsblocks.|  
|[Propagate_message-Methode](#propagate_message)|Übergibt eine Nachricht asynchron eine `ISource` -Block an diesen `overwrite_buffer` Meldungsblocks. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.|  
|[Propagate_to_any_targets-Methode](#propagate_to_any_targets)|Stellen die `message``_PMessage` in diesem `overwrite_buffer` -Meldungsblock ein und bietet sie allen verknüpften Zielen.|  
|[Release_message-Methode](#release_message)|Gibt die Reservierung einer vorherigen Meldung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|  
|[Reserve_message-Methode](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `overwrite_buffer` Meldungsblocks. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[Resume_propagation-Methode](#resume_propagation)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
|[Send_message-Methode](#send_message)|Übergibt synchron eine Meldung von einer `ISource` -Block an diesen `overwrite_buffer` Meldungsblocks. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.|  
|[Supports_anonymous_source-Methode](#supports_anonymous_source)|Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block akzeptieren kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist. (Überschreibt [ITarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>Hinweise  
 Ein `overwrite_buffer` -Meldungsblock gibt Kopien der gespeicherten Nachricht an die einzelnen Ziele weiter.  
  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `overwrite_buffer` -Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `overwrite_buffer` -Meldungsblock gibt Kopien der Meldung an ihre Ziele, statt den Besitz der gerade vorliegenden Meldung zu übertragen.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Nimmt eine Meldung, die zuvor von Angeboten der `overwrite_buffer` -Meldungsblock und reserviert durch das Ziel, eine Kopie der Nachricht an den Aufrufer zurückgegeben.  
  
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

 Überprüft, ob diese `overwrite_buffer` -Meldungsblock ist einen Wert noch nicht.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Block einen Wert empfangen hat `false` andernfalls.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `overwrite_buffer` Meldungsblocks.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf das neu verknüpfte Ziel.  
  
##  <a name="a-namedtora-overwritebuffer"></a><a name="dtor"></a>~ Overwrite_buffer 

 Zerstört die `overwrite_buffer` Meldungsblocks.  
  
```
~overwrite_buffer();
```  
  
##  <a name="a-namectora-overwritebuffer"></a><a name="ctor"></a>overwrite_buffer 

 Erstellt ein `overwrite_buffer` Meldungsblocks.  
  
```
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter`  
 Eine Filterfunktion, die bestimmt, ob die angebotene Nachrichten akzeptiert werden sollen.  
  
 `_PScheduler`  
 Das `Scheduler`-Objekt, in dem die Weiterleitungsaufgabe für den `overwrite_buffer`-Meldungsblock geplant ist.  
  
 `_PScheduleGroup`  
 Das `ScheduleGroup`-Objekt, in dem die Weiterleitungsaufgabe für den `overwrite_buffer`-Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.  
  
 Der Typ `filter_method` ist ein Funktionselement mit der Signatur `bool (T const &)` die aufgerufen wird, von diesem `overwrite_buffer` -Meldungsblock zu bestimmen, ob eine bereitgestellte Meldung akzeptiert werden sollen.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 Übergibt eine Nachricht asynchron eine `ISource` -Block an diesen `overwrite_buffer` Meldungsblocks. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.  
  
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

 Stellen die `message``_PMessage` in diesem `overwrite_buffer` -Meldungsblock ein und bietet sie allen verknüpften Zielen.  
  
```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf eine `message` Objekt, das dieses `overwrite_buffer` Besitz an übergegangen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die aktuelle Meldung in der `overwrite_buffer` mit der neu akzeptierten Meldung `_PMessage`.  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 Übergibt synchron eine Meldung von einer `ISource` -Block an diesen `overwrite_buffer` Meldungsblocks. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.  
  
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
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block akzeptieren kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Da der Block nicht angebotene Nachrichten nicht verschieben.  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Gibt die Reservierung einer vorherigen Meldung frei.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `overwrite_buffer` Meldungsblocks.  
  
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
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>Wert 

 Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `overwrite_buffer` Meldungsblocks.  
  
```
T value();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Nutzlast der derzeit gespeicherten Meldung.  
  
### <a name="remarks"></a>Hinweise  
 In gespeicherte Wert dem `overwrite_buffer` konnte sofort ändern, nachdem diese Methode zurückgibt. Diese Methode wartet, bis eine Meldung eintrifft, wenn derzeit keine Meldung im gespeichert ist die `overwrite_buffer`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Unbounded_buffer-Klasse](unbounded-buffer-class.md)   
 [Single_assignment-Klasse](single-assignment-class.md)

