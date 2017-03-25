---
title: Message-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
dev_langs:
- C++
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: c6cc72c1fe9385eabe86194031913b7363d602ff
ms.lasthandoff: 03/17/2017

---
# <a name="message-class"></a>message-Klasse
Der grundlegende Nachrichtenumschlag, der die zwischen den Meldungsblöcken übergebene Datennutzlast enthält.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Nutzlast in der Nachricht.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[message](#ctor)|Überladen. Erstellt ein `message`-Objekt.|  
|[~ message-Destruktor](#dtor)|Zerstört das `message`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[add_ref](#add_ref)|Fügt der Verweisanzahl für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.|  
|[msg_id](#msg_id)|Gibt die ID des dem `message` Objekt.|  
|[remove_ref](#remove_ref)|Wird von den Verweiszähler für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Nutzlast](#payload)|Die Nutzlast der `message` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `message`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="add_ref"></a>add_ref 

 Fügt der Verweisanzahl für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.  
  
```
long add_ref();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Wert des Verweiszählers.  
  
##  <a name="ctor"></a>Nachricht 

 Erstellt ein `message`-Objekt.  
  
```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```  
  
### <a name="parameters"></a>Parameter  
 `_P`  
 Die Nutzlast dieser Nachricht.  
  
 `_Id`  
 Die eindeutige ID dieser Nachricht.  
  
 `_Msg`  
 Ein Verweis oder Zeiger auf ein `message` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Dem Konstruktor, einen Zeiger auf eine `message` -Objekt als Argument löst ein [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_Msg` ist `NULL`.  
  
##  <a name="dtor"></a>~ Nachricht 

 Zerstört das `message`-Objekt.  
  
```
virtual ~message();
```  
  
##  <a name="msg_id"></a>msg_id 

 Gibt die ID des dem `message` Objekt.  
  
```
runtime_object_identity msg_id() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `runtime_object_identity` von der `message` Objekt.  
  
##  <a name="payload"></a>Nutzlast 

 Die Nutzlast der `message` Objekt.  
  
```
T const payload;
```  
  
##  <a name="remove_ref"></a>remove_ref 

 Wird von den Verweiszähler für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Wert des Verweiszählers.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

