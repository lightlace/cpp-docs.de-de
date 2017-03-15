---
title: Message_processor-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::message_processor
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
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
ms.openlocfilehash: 98f1c1072916c4cf3670e40ce0c6ddd1a17f1b63
ms.lasthandoff: 02/24/2017

---
# <a name="messageprocessor-class"></a>message_processor-Klasse
Die `message_processor`-Klasse ist die abstrakte Basisklasse für die Verarbeitung von `message`-Objekten. Für die Reihenfolge der Meldungen besteht keine Garantie.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Nutzlast in Nachrichten von diesem verarbeitet `message_processor` Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Async_send-Methode](#async_send)|Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten asynchron in den Block.|  
|[Sync_send-Methode](#sync_send)|Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten synchron in den Block.|  
|[Wait-Methode](#wait)|Ruft beim Überschreiben in einer abgeleiteten Klasse wartet, bis alle asynchronen Vorgänge abgeschlossen.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Process_incoming_message-Methode](#process_incoming_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse führt die forward-Verarbeitung von Nachrichten in den Block. Jedes Mal, wenn eine neue Nachricht hinzugefügt wird und die Warteschlange leer gefunden wird einmal aufgerufen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `message_processor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten asynchron in den Block.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein `message` Objekt, das asynchron gesendet.  
  
### <a name="remarks"></a>Hinweise  
 Prozessor-Implementierungen sollten diese Methode überschreiben.  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 Ruft beim Überschreiben in einer abgeleiteten Klasse führt die forward-Verarbeitung von Nachrichten in den Block. Jedes Mal, wenn eine neue Nachricht hinzugefügt wird und die Warteschlange leer gefunden wird einmal aufgerufen.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Message Block-Implementierungen sollten diese Methode überschreiben.  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 Ruft beim Überschreiben in einer abgeleiteten Klasse legt Nachrichten synchron in den Block.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Msg`  
 Ein `message` Objekt, das synchron gesendet.  
  
### <a name="remarks"></a>Hinweise  
 Prozessor-Implementierungen sollten diese Methode überschreiben.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Warte 

 Ruft beim Überschreiben in einer abgeleiteten Klasse wartet, bis alle asynchronen Vorgänge abgeschlossen.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Prozessor-Implementierungen sollten diese Methode überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Ordered_message_processor-Klasse](ordered-message-processor-class.md)

