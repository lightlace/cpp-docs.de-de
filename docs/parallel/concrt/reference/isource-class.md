---
title: ISource-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27b1aa57a8c90c2f996aab3b8ee47797f15edd5b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692570"
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
 Der Datentyp der Nutzlast innerhalb der Nachrichten, die vom Quellblock erzeugt wurde.  
  
## <a name="members"></a>Member  
  
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
|[accept](#accept)|Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine Meldung, die von diesem angebotenen wurde `ISource` -Block übertragen des Besitzes an den Aufrufer.|  
|[acquire_ref](#acquire_ref)|Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für dieses `ISource` Block, um den Löschvorgang zu verhindern.|  
|[Nutzen](#consume)|Ruft beim Überschreiben in einer abgeleiteten Klasse verwendet eine Meldung, die zuvor von diesem angebotenen `ISource` blockieren und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.|  
|[link_target](#link_target)|Ruft beim Überschreiben in einer abgeleiteten Klasse einen Zielblock verknüpft, mit diesem `ISource` Block.|  
|[release](#release)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[release_ref](#release_ref)|Ruft beim Überschreiben in einer abgeleiteten Klasse einen Verweiszähler für dieses frei `ISource` Block.|  
|[reserve](#reserve)|Ruft beim Überschreiben in einer abgeleiteten Klasse reserviert eine Meldung, die zuvor von diesem angebotenen `ISource` Block.|  
|[unlink_target](#unlink_target)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem Zielblock und dies `ISource` blockieren, wenn gefunden, die zuvor verknüpft werden.|  
|[unlink_targets](#unlink_targets)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung von diesem alle Zielblöcke `ISource` Block.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept"></a> Akzeptieren 

 Ruft beim Überschreiben in einer abgeleiteten Klasse akzeptiert eine Meldung, die von diesem angebotenen wurde `ISource` -Block übertragen des Besitzes an den Aufrufer.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun den Besitz von verfügt.  
  
### <a name="remarks"></a>Hinweise  
 Die `accept` Methode wird von einem Ziel aufgerufen, während eine Nachricht von diesem angeboten wird `ISource` Block. Der zurückgegebene Meldungszeiger möglicherweise andere als die übergebenen der `propagate` Methode der `ITarget` blockieren, wenn diese Quelle entscheidet, eine Kopie der Nachricht zu erstellen.  
  
##  <a name="acquire_ref"></a> acquire_ref 

 Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für dieses `ISource` Block, um den Löschvorgang zu verhindern.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, wird die `link_target` Methode.  
  
##  <a name="consume"></a> Nutzen 

 Ruft beim Überschreiben in einer abgeleiteten Klasse verwendet eine Meldung, die zuvor von diesem angebotenen `ISource` blockieren und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` des reservierten `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `consume` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` -Objekt, dass der Aufrufer nun den Besitz von aufweist.  
  
### <a name="remarks"></a>Hinweise  
 Die `consume` Methode ist vergleichbar mit `accept`, aber immer durch einen Aufruf von vorangestellt werden muss `reserve` zurückgegebenen `true`.  
  
##  <a name="dtor"></a> ~ ISource 

 Zerstört das `ISource`-Objekt.  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a> link_target 

 Ruft beim Überschreiben in einer abgeleiteten Klasse einen Zielblock verknüpft, mit diesem `ISource` Block.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der mit dieser verknüpft `ISource` Block.  
  
##  <a name="release"></a> Version 

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
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `release` Methode.  
  
##  <a name="release_ref"></a> release_ref 

 Ruft beim Überschreiben in einer abgeleiteten Klasse einen Verweiszähler für dieses frei `ISource` Block.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das aus dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierten Ressourcen freizugeben.  
  
##  <a name="reserve"></a> Hostreserven 

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
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können viele Gründe geben, einschließlich fehl: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, die Quelle konnte verweigern Reservierungen usw.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `reserve`, wenn er erfolgreich ausgeführt wird, müssen Sie entweder Aufrufen `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="unlink_target"></a> unlink_target 

 Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem Zielblock und dies `ISource` blockieren, wenn gefunden, die zuvor verknüpft werden.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der von diesem aufgehoben wird `ISource` Block.  
  
##  <a name="unlink_targets"></a> unlink_targets 

 Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung von diesem alle Zielblöcke `ISource` Block.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ITarget-Klasse](itarget-class.md)
