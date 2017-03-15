---
title: Ordered_message_processor-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ordered_message_processor
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
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
ms.openlocfilehash: a9653c8eb5f05e56fd7812d334575e62dc101d63
ms.lasthandoff: 02/24/2017

---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor-Klasse
Ein `ordered_message_processor` ist ein `message_processor`, mit dem Meldungsblöcke Meldungen in der Reihenfolge verarbeiten können, in der sie empfangen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Nutzlasttyp der Nachrichten, die vom Prozessor verarbeitet.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Ordered_message_processor-Konstruktor](#ctor)|Erstellt ein `ordered_message_processor`-Objekt.|  
|[~ Ordered_message_processor-Destruktor](#dtor)|Zerstört das `ordered_message_processor`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Async_send-Methode](#async_send)|Asynchron Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde. (Überschreibt [message_processor:: async_send](message-processor-class.md#async_send).)|  
|[Initialize-Methode](#initialize)|Initialisiert das `ordered_message_processor` -Objekt mit der entsprechenden Rückruffunktion, dem Planer und Zeitplan.|  
|[Initialize_batched_processing-Methode](#initialize_batched_processing)|Initialisieren der Verarbeitung von Nachrichten im Batchmodus|  
|[Sync_send-Methode](#sync_send)|Synchrone Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde. (Überschreibt [message_processor:: sync_send](message-processor-class.md#sync_send).)|  
|[Wait-Methode](#wait)|Eine prozessorspezifische Spin-Wartezeit in Destruktoren Nachrichtenblöcke verwendet, um sicherzustellen, dass alle Vorgänge für die asynchrone Verarbeitung für die Ausführung vor dem Zerstören des Blocks haben. (Überschreibt [message_processor:: wait](message-processor-class.md#wait).)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Process_incoming_message-Methode](#process_incoming_message)|Die Verarbeitungsfunktion, die asynchron aufgerufen wird. Es entfernt Nachrichten und deren Verarbeitung beginnt. (Überschreibt [message_processor:: process_incoming_message](message-processor-class.md#process_incoming_message).)|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 Asynchron Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf eine Nachricht.  
  
##  <a name="a-nameinitializea-initialize"></a><a name="initialize"></a>Initialisieren 

 Initialisiert das `ordered_message_processor` -Objekt mit der entsprechenden Rückruffunktion, dem Planer und Zeitplan.  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>Parameter  
 `_PScheduler`  
 Ein Zeiger auf den Planer zum Planen von einfachen Aufgaben verwendet werden.  
  
 `_PScheduleGroup`  
 Ein Zeiger auf die Planungsgruppe zum Planen von einfachen Aufgaben verwendet werden.  
  
 `_Handler`  
 Der Handlerfunktionselement während des Rückrufs aufgerufen.  
  
##  <a name="a-nameinitializebatchedprocessinga-initializebatchedprocessing"></a><a name="initialize_batched_processing"></a>initialize_batched_processing 

 Initialisieren der Verarbeitung von Nachrichten im Batchmodus  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>Parameter  
 `_Processor`  
 Der Prozessor Funktionselement während des Rückrufs aufgerufen.  
  
 `_Propagator`  
 Das Propagator Funktionselement während des Rückrufs aufgerufen.  
  
##  <a name="a-namectora-orderedmessageprocessor"></a><a name="ctor"></a>ordered_message_processor 

 Erstellt ein `ordered_message_processor`-Objekt.  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese `ordered_message_processor` plant asynchrone oder synchrone Handler, bis die `initialize` -Funktion aufgerufen wird.  
  
##  <a name="a-namedtora-orderedmessageprocessor"></a><a name="dtor"></a>~ Ordered_message_processor 

 Zerstört das `ordered_message_processor`-Objekt.  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>Hinweise  
 Wartet, bis alle ausstehenden asynchronen Vorgänge vor dem Zerstören des Prozessors.  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 Die Verarbeitungsfunktion, die asynchron aufgerufen wird. Es entfernt Nachrichten und deren Verarbeitung beginnt.  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 Synchrone Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf eine Nachricht.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Warte 

 Eine prozessorspezifische Spin-Wartezeit in Destruktoren Nachrichtenblöcke verwendet, um sicherzustellen, dass alle Vorgänge für die asynchrone Verarbeitung für die Ausführung vor dem Zerstören des Blocks haben.  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

