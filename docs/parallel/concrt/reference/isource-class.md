---
title: ISource-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ISource
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: db3ba296a96b2e77c0ae7d9be3d0a499fe2e7f76
ms.lasthandoff: 02/24/2017

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
|[Accept-Methode](#accept)|Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine Nachricht, die von diesem angeboten wurde `ISource` Block überträgt den Besitz an den Aufrufer.|  
|[Acquire_ref-Methode](#acquire_ref)|Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für diesen `ISource` Block, um das Löschen zu verhindern.|  
|[Consume-Methode](#consume)|Ruft beim Überschreiben in einer abgeleiteten Klasse nimmt eine Meldung, die zuvor von diesem angebotenen `ISource` blockieren und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.|  
|[Link_target-Methode](#link_target)|Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen Zielblock mit diesem `ISource` Block.|  
|[Release-Methode](#release)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[Release_ref-Methode](#release_ref)|Ruft beim Überschreiben in einer abgeleiteten Klasse einen Verweiszähler für diese frei `ISource` Block.|  
|[Reserve-Methode](#reserve)|Ruft beim Überschreiben in einer abgeleiteten Klasse reserviert eine Meldung, die zuvor von diesem angebotenen `ISource` Block.|  
|[Unlink_target-Methode](#unlink_target)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem Zielblock aus diesem `ISource` zu blockieren, wenn zuvor Verknüpfung.|  
|[Unlink_targets-Methode](#unlink_targets)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Zielblöcke mit diesem `ISource` Block.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>akzeptieren 

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
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für diesen `ISource` Block, um das Löschen zu verhindern.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, ist die `link_target` Methode.  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>Nutzen 

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
  
##  <a name="a-namedtora-isource"></a><a name="dtor"></a>~ ISource 

 Zerstört das `ISource`-Objekt.  
  
```
virtual ~ISource();
```  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen Zielblock mit diesem `ISource` Block.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der mit dieser verknüpft `ISource` Block.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Version 

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
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 Ruft beim Überschreiben in einer abgeleiteten Klasse einen Verweiszähler für diese frei `ISource` Block.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierte Ressourcen freizugeben.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Reservieren 

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
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen fehlschlagen können viele Ursachen haben, z. B.: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, konnte die Quelle Reservierungen verweigern und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von `reserve`, das erfolgreich ist, rufen Sie entweder `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem Zielblock aus diesem `ISource` zu blockieren, wenn zuvor Verknüpfung.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der von diesem aufgehoben wird `ISource` Block.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Zielblöcke mit diesem `ISource` Block.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ITarget-Klasse](itarget-class.md)

