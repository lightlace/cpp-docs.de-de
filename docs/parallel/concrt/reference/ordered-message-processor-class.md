---
title: Ordered_message_processor-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 1c3147001db16b610992d2501ed12ad4bd001fc9
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
|[ordered_message_processor](#ctor)|Erstellt ein `ordered_message_processor`-Objekt.|  
|[~ Ordered_message_processor-Destruktor](#dtor)|Zerstört das `ordered_message_processor`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[async_send](#async_send)|Asynchron Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde. (Überschreibt [message_processor:: async_send](message-processor-class.md#async_send).)|  
|[Initialisieren](#initialize)|Initialisiert das `ordered_message_processor` -Objekt mit der entsprechenden Rückruffunktion, dem Planer und Zeitplan.|  
|[initialize_batched_processing](#initialize_batched_processing)|Initialisieren der Verarbeitung von Nachrichten im Batchmodus|  
|[sync_send](#sync_send)|Synchrone Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde. (Überschreibt [message_processor:: sync_send](message-processor-class.md#sync_send).)|  
|[Warte](#wait)|Eine prozessorspezifische Spin-Wartezeit in Destruktoren Nachrichtenblöcke verwendet, um sicherzustellen, dass alle Vorgänge für die asynchrone Verarbeitung für die Ausführung vor dem Zerstören des Blocks haben. (Überschreibt [message_processor:: wait](message-processor-class.md#wait).)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|Die Verarbeitungsfunktion, die asynchron aufgerufen wird. Es entfernt Nachrichten und deren Verarbeitung beginnt. (Überschreibt [message_processor:: process_incoming_message](message-processor-class.md#process_incoming_message).)|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="async_send"></a>async_send 

 Asynchron Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf eine Nachricht.  
  
##  <a name="initialize"></a>Initialisieren 

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
  
##  <a name="initialize_batched_processing"></a>initialize_batched_processing 

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
  
##  <a name="ctor"></a>ordered_message_processor 

 Erstellt ein `ordered_message_processor`-Objekt.  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese `ordered_message_processor` plant asynchrone oder synchrone Handler, bis die `initialize` -Funktion aufgerufen wird.  
  
##  <a name="dtor"></a>~ Ordered_message_processor 

 Zerstört das `ordered_message_processor`-Objekt.  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>Hinweise  
 Wartet, bis alle ausstehenden asynchronen Vorgänge vor dem Zerstören des Prozessors.  
  
##  <a name="process_incoming_message"></a>process_incoming_message 

 Die Verarbeitungsfunktion, die asynchron aufgerufen wird. Es entfernt Nachrichten und deren Verarbeitung beginnt.  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="sync_send"></a>sync_send 

 Synchrone Warteschlangen Nachrichten und eine Verarbeitungsaufgabe, die beginnt, wenn dies nicht bereits ausgeführt wurde.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein Zeiger auf eine Nachricht.  
  
##  <a name="wait"></a>Warte 

 Eine prozessorspezifische Spin-Wartezeit in Destruktoren Nachrichtenblöcke verwendet, um sicherzustellen, dass alle Vorgänge für die asynchrone Verarbeitung für die Ausführung vor dem Zerstören des Blocks haben.  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

