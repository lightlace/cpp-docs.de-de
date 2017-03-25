---
title: Unbounded_buffer-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
dev_langs:
- C++
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 9a9c44985b1e9475b8760d835e2a8fd45361ea5a
ms.lasthandoff: 03/17/2017

---


Ein `unbounded_buffer`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine unbegrenzte Anzahl von Meldungen speichern kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   class             _Type  
>  
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Type`  
 Der Nutzlasttyp der Nachrichten gespeichert, und der Puffer weitergegeben.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[unbounded_buffer](#ctor)|Überladen. Erstellt ein `unbounded_buffer` Meldungsblocks.|  
|[~ Unbounded_buffer-Destruktor](#dtor)|Zerstört die `unbounded_buffer` Meldungsblocks.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Entfernen aus der Warteschlange](#dequeue)|Entfernt ein Element aus der `unbounded_buffer` Meldungsblocks.|  
|[in die Warteschlange einzureihen](#enqueue)|Fügt ein Element an der `unbounded_buffer` Meldungsblocks.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `unbounded_buffer` -Meldungsblock überträgt den Besitz an den Aufrufer.|  
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten der `unbounded_buffer` -Meldungsblock und vom Ziel überträgt den Besitz an den Aufrufer reserviert.|  
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `unbounded_buffer` Meldungsblocks.|  
|[process_input_messages](#process_input_messages)|Stellen die `message``_PMessage` in diesem `unbounded_buffer` -Meldungsblock und versucht, sie allen verknüpften Zielen anzubieten.|  
|[propagate_message](#propagate_message)|Übergibt eine Nachricht asynchron eine `ISource` -Block an diesen `unbounded_buffer` Meldungsblocks. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.|  
|[propagate_output_messages](#propagate_output_messages)|Stellen die `message``_PMessage` in diesem `unbounded_buffer` -Meldungsblock und versucht, sie allen verknüpften Zielen anzubieten. (Überschreibt [source_block:: propagate_output_messages](source-block-class.md#propagate_output_messages).)|  
|[release_message](#release_message)|Gibt die Reservierung einer vorherigen Meldung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `unbounded_buffer` Meldungsblocks. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|Übergibt synchron eine Meldung von einer `ISource` -Block an diesen `unbounded_buffer` Meldungsblocks. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.|  
|[supports_anonymous_source](#supports_anonymous_source)|Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block akzeptieren kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist. (Überschreibt [ITarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  

 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `unbounded_buffer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept_message"></a>accept_message 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `unbounded_buffer` -Meldungsblock überträgt den Besitz an den Aufrufer.  
  
```  
virtual message<_Type> * accept_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
##  <a name="consume_message"></a>consume_message 

 Nimmt eine Meldung, die zuvor von Angeboten der `unbounded_buffer` -Meldungsblock und vom Ziel überträgt den Besitz an den Aufrufer reserviert.  
  
```  
virtual message<_Type> * consume_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt verarbeitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie `accept`, steht aber immer nach einem Aufruf von ist `reserve`.  
  
##  <a name="dequeue"></a>Entfernen aus der Warteschlange 

 Entfernt ein Element aus der `unbounded_buffer` Meldungsblocks.  
  
```  
_Type dequeue();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Nutzlast der Nachricht entfernt aus der `unbounded_buffer`.  
  
##  <a name="enqueue"></a>in die Warteschlange einzureihen 

 Fügt ein Element an der `unbounded_buffer` Meldungsblocks.  
  
```  
bool enqueue(  
   _Type const&                 _Item  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Item`  
 Das Element, das hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn das Element akzeptiert wurde, `false` andernfalls.  
  
##  <a name="link_target_notification"></a>link_target_notification 

 Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem verknüpft wurde `unbounded_buffer` Meldungsblocks.  
  
```  
virtual void link_target_notification(  
   _Inout_ ITarget<_Type> *                 _PTarget  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf das neu verknüpfte Ziel.  
  
##  <a name="propagate_message"></a>propagate_message 

 Übergibt eine Nachricht asynchron eine `ISource` -Block an diesen `unbounded_buffer` Meldungsblocks. Wird aufgerufen, indem die `propagate` -Methode beim Aufruf durch einen Quellblock.  
  
```  
virtual message_status propagate_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md#message_status) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
##  <a name="propagate_output_messages"></a>propagate_output_messages 

 Stellen die `message``_PMessage` in diesem `unbounded_buffer` -Meldungsblock und versucht, sie allen verknüpften Zielen anzubieten.  
  
```  
virtual void propagate_output_messages();  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine andere Meldung bereits vor dieser im ist der `unbounded_buffer`, Weitergabe zu verknüpften Zielen werden erst alle früheren Meldungen akzeptiert wurden oder verarbeitet wurden. Das erste verknüpfte Ziel, um erfolgreich `accept` oder `consume` übernimmt die Nachricht, und kein anderes Ziel kann dann die Meldung abrufen.  
  
##  <a name="process_input_messages"></a>process_input_messages 

 Stellen die `message``_PMessage` in diesem `unbounded_buffer` -Meldungsblock und versucht, sie allen verknüpften Zielen anzubieten.  
  
```  
virtual void process_input_messages(  
   _Inout_ message<_Type> *                 _PMessage  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
  
##  <a name="release_message"></a>release_message 

 Gibt die Reservierung einer vorherigen Meldung frei.  
  
```  
virtual void release_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
##  <a name="reserve_message"></a>reserve_message 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `unbounded_buffer` Meldungsblocks.  
  
```  
virtual bool reserve_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt reserviert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem `reserve` wird aufgerufen, wenn die Rückgabe `true`, `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.  
  
##  <a name="resume_propagation"></a>resume_propagation 

 Setzt die Weitergabe fort, nachdem eine Reservierung freigegeben wurde.  
  
```  
virtual void resume_propagation();  
```  
  
##  <a name="send_message"></a>send_message 

 Übergibt synchron eine Meldung von einer `ISource` -Block an diesen `unbounded_buffer` Meldungsblocks. Wird aufgerufen, indem die `send` -Methode beim Aufruf durch einen Quellblock.  
  
```  
virtual message_status send_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md#message_status) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block akzeptieren kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist.  
  
```  
virtual bool supports_anonymous_source();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Da der Block nicht angebotene Nachrichten nicht verschieben.  
  
##  <a name="ctor"></a>unbounded_buffer 

 Erstellt ein `unbounded_buffer` Meldungsblocks.  
  
```  
unbounded_buffer();  
  
unbounded_buffer(  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler,  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup,  
   filter_method const&                 _Filter  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter`  
 Eine Filterfunktion, die bestimmt, ob die angebotene Nachrichten akzeptiert werden sollen.  
  
 `_PScheduler`  
 Das `Scheduler`-Objekt, in dem die Weiterleitungsaufgabe für den `unbounded_buffer`-Meldungsblock geplant ist.  
  
 `_PScheduleGroup`  
 Das `ScheduleGroup`-Objekt, in dem die Weiterleitungsaufgabe für den `unbounded_buffer`-Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.  
  
 Der Typ `filter_method` ist ein Funktionselement mit der Signatur `bool (_Type const &)` die aufgerufen wird, von diesem `unbounded_buffer` -Meldungsblock zu bestimmen, ob eine bereitgestellte Meldung akzeptiert werden sollen.  
  
##  <a name="dtor"></a>~ Unbounded_buffer 

 Zerstört die `unbounded_buffer` Meldungsblocks.  
  
```  
~unbounded_buffer();  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Overwrite_buffer-Klasse](overwrite-buffer-class.md)   
 [single_assignment-Klasse](single-assignment-class.md)



