---
title: ISource-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
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
ms.openlocfilehash: b5545f666dccb251152dc6c9a83101662848be1c
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="isource-class"></a>ISource-Klasse
Die `ISource`-Klasse ist die Schnittstelle für alle Quellblöcke. Quellblöcke geben Meldungen an `ITarget`-Blöcke weiter.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Nutzlast in den Nachrichten vom Quellblock erzeugt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`source_type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ ISource-Destruktor](#dtor)|Zerstört das `ISource`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[akzeptieren](#accept)|Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine Nachricht, die von diesem angeboten wurde `ISource` Block überträgt den Besitz an den Aufrufer.|  
|[acquire_ref](#acquire_ref)|Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für diesen `ISource` Block, um das Löschen zu verhindern.|  
|[Nutzen](#consume)|Ruft beim Überschreiben in einer abgeleiteten Klasse nimmt eine Meldung, die zuvor von diesem angebotenen `ISource` blockieren und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.|  
|[link_target](#link_target)|Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen Zielblock mit diesem `ISource` Block.|  
|[release](#release)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[release_ref](#release_ref)|Ruft beim Überschreiben in einer abgeleiteten Klasse einen Verweiszähler für diese frei `ISource` Block.|  
|[reserve](#reserve)|Ruft beim Überschreiben in einer abgeleiteten Klasse reserviert eine Meldung, die zuvor von diesem angebotenen `ISource` Block.|  
|[unlink_target](#unlink_target)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem Zielblock aus diesem `ISource` zu blockieren, wenn zuvor Verknüpfung.|  
|[unlink_targets](#unlink_targets)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Zielblöcke mit diesem `ISource` Block.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept"></a>akzeptieren 

 Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine Nachricht, die von diesem angeboten wurde `ISource` Block überträgt den Besitz an den Aufrufer.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `accept` Methode wird von einem Ziel aufgerufen, während eine Nachricht von diesem angeboten wird `ISource` Block. Der zurückgegebene möglicherweise nicht das Übergeben der `propagate` Methode der `ITarget` zu blockieren, wenn diese Quelle entscheidet, eine Kopie der Nachricht zu erstellen.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für diesen `ISource` Block, um das Löschen zu verhindern.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, ist die `link_target` Methode.  
  
##  <a name="consume"></a>Nutzen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse nimmt eine Meldung, die zuvor von diesem angebotenen `ISource` blockieren und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` des reservierten `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `consume` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, das der Aufrufer nun Eigentümer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `consume` Methode ähnelt `accept`, steht aber immer nach einem Aufruf werden müssen `reserve` zurückgegebenen `true`.  
  
##  <a name="dtor"></a>~ ISource 

 Zerstört das `ISource`-Objekt.  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a>link_target 

 Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen Zielblock mit diesem `ISource` Block.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der mit dieser verknüpft `ISource` Block.  
  
##  <a name="release"></a>Version 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` des reservierten `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `release` Methode.  
  
##  <a name="release_ref"></a>release_ref 

 Ruft beim Überschreiben in einer abgeleiteten Klasse einen Verweiszähler für diese frei `ISource` Block.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierte Ressourcen freizugeben.  
  
##  <a name="reserve"></a>Reservieren 

 Ruft beim Überschreiben in einer abgeleiteten Klasse reserviert eine Meldung, die zuvor von diesem angebotenen `ISource` Block.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können viele Ursachen haben, z. B. fehlschlagen: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, konnte die Quelle Reservierungen verweigern und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von `reserve`, das erfolgreich ist, rufen Sie entweder `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="unlink_target"></a>unlink_target 

 Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem Zielblock aus diesem `ISource` zu blockieren, wenn zuvor Verknüpfung.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der von diesem aufgehoben wird `ISource` Block.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Zielblöcke mit diesem `ISource` Block.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ITarget-Klasse](itarget-class.md)

