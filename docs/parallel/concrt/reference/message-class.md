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
- agents/concurrency::message
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 08d67f2899f27a92250d6fedbf755a5413e01ebd
ms.lasthandoff: 02/24/2017

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
|[Message-Konstruktor](#ctor)|Überladen. Erstellt ein `message`-Objekt.|  
|[~ message-Destruktor](#dtor)|Zerstört das `message`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Add_ref-Methode](#add_ref)|Fügt der Verweisanzahl für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.|  
|[Msg_id-Methode](#msg_id)|Gibt die ID des dem `message` Objekt.|  
|[Remove_ref-Methode](#remove_ref)|Wird von den Verweiszähler für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Nutzlast-Datenmember](#payload)|Die Nutzlast der `message` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `message`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameaddrefa-addref"></a><a name="add_ref"></a>add_ref 

 Fügt der Verweisanzahl für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.  
  
```
long add_ref();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Wert des Verweiszählers.  
  
##  <a name="a-namectora-message"></a><a name="ctor"></a>Nachricht 

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
  
##  <a name="a-namedtora-message"></a><a name="dtor"></a>~ Nachricht 

 Zerstört das `message`-Objekt.  
  
```
virtual ~message();
```  
  
##  <a name="a-namemsgida-msgid"></a><a name="msg_id"></a>msg_id 

 Gibt die ID des dem `message` Objekt.  
  
```
runtime_object_identity msg_id() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `runtime_object_identity` von der `message` Objekt.  
  
##  <a name="a-namepayloada-payload"></a><a name="payload"></a>Nutzlast 

 Die Nutzlast der `message` Objekt.  
  
```
T const payload;
```  
  
##  <a name="a-nameremoverefa-removeref"></a><a name="remove_ref"></a>remove_ref 

 Wird von den Verweiszähler für das `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Nachricht zu ermitteln.  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Wert des Verweiszählers.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

