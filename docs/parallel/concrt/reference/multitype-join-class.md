---
title: Multitype_join-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eea798db304b27a77ae70766a7271cfa3f94981b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019413"
---
# <a name="multitypejoin-class"></a>multitype_join-Klasse
Ein `multitype_join`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der Meldungen verschiedener Typen aus allen Quellen kombiniert und dem Ziel ein Tupel der kombinierten Meldungen bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<
    typename T,  
    join_type _Jtype = non_greedy  
>  
class multitype_join: public ISource<typename _Unwrap<T>::type>;  
```  
  
#### <a name="parameters"></a>Parameter  
*T*<br/>
Die `tuple` Typ der Ereignisnutzlast der Nachrichten hinzugefügt und vom Block weitergegeben.  
  
*_Jtype*<br/>
Die Art der `join` Blocks, entweder `greedy` oder `non_greedy`  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[multitype_join](#ctor)|Überladen. Erstellt einen `multitype_join` -Meldungsblock.|  
|[~ Multitype_join-Destruktor](#dtor)|Zerstört die `multitype_join` Meldungsblock.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accept](#accept)|Akzeptiert eine Meldung, die von diesem angeboten wurde `multitype_join` Block übertragen des Besitzes an den Aufrufer.|  
|[acquire_ref](#acquire_ref)|Eine Verweisanzahl dazu `multitype_join` Meldungsblock, um löschen zu verhindern.|  
|[Nutzen](#consume)|Nimmt eine Meldung, die zuvor von Angeboten die `multitype_join` -Meldungsblock und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.|  
|[link_target](#link_target)|Verknüpft einen Zielblock mit diesem `multitype_join` Meldungsblock.|  
|[release](#release)|Gibt die nachrichtenreservierung einer vorherigen erfolgreichen frei.|  
|[release_ref](#release_ref)|Gibt einen Verweiszähler für diese `multiple_join` Meldungsblock.|  
|[reserve](#reserve)|Reserviert eine Meldung, die zuvor von diesem angebotenen `multitype_join` Meldungsblock.|  
|[unlink_target](#unlink_target)|Hebt die Verknüpfung mit einem Zielblock und dadurch `multitype_join` Meldungsblock.|  
|[unlink_targets](#unlink_targets)|Hebt die Verknüpfung alle Ziele aus diesem `multitype_join` Meldungsblock. (Überschreibt [ISource:: Unlink_targets](isource-class.md#unlink_targets).)|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept"></a> Akzeptieren 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `multitype_join` Block übertragen des Besitzes an den Aufrufer.  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.  
  
*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer jetzt besitzt.  
  
##  <a name="acquire_ref"></a> acquire_ref 

 Eine Verweisanzahl dazu `multitype_join` Meldungsblock, um löschen zu verhindern.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit der Quelle während der zu verknüpfenden der `link_target` Methode.  
  
##  <a name="consume"></a> Nutzen 

 Nimmt eine Meldung, die zuvor von Angeboten die `multitype_join` -Meldungsblock und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekt.  
  
*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `consume` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Die `consume` -Methode ist vergleichbar mit `accept`, jedoch immer durch einen Aufruf von vorangestellt werden muss `reserve` zurückgegebenen `true`.  
  
##  <a name="link_target"></a> link_target 

 Verknüpft einen Zielblock mit diesem `multitype_join` Meldungsblock.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_PTarget*<br/>
Ein Zeiger auf ein `ITarget` Block, um Sie zu diesem link `multitype_join` Meldungsblock.  
  
##  <a name="ctor"></a> multitype_join 

 Erstellt einen `multitype_join` -Meldungsblock.  
  
```  
explicit multitype_join(
    T _Tuple);

 
multitype_join(
    Scheduler& _PScheduler,  
    T _Tuple);

 
multitype_join(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
multitype_join(
    multitype_join&& _Join);
```  
  
### <a name="parameters"></a>Parameter  
*_Tuple*<br/>
Ein `tuple` von Quellen für diesen `multitype_join` -Meldungsblock.  
  
*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.  
  
*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
*_Join*<br/>
Ein `multitype_join` -Meldungsblock, aus dem kopiert werden soll. Beachten Sie, dass das ursprüngliche Objekt verwaist ist, sodass dies ein Bewegungskonstruktor ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.  
  
 Bewegungskonstruktion wird bei einer aktiven Sperre nicht ausgeführt, d. h., der Benutzer muss sicherstellen, dass zum Zeitpunkt der Bewegung keine einfachen Aufgaben aktiv sind. Andernfalls können zahlreiche Wettläufe auftreten, wodurch Ausnahmen oder inkonsistente Zuständen verursacht werden.  
  
##  <a name="dtor"></a> ~ Multitype_join 

 Zerstört die `multitype_join` Meldungsblock.  
  
```  
~multitype_join();
```  
  
##  <a name="release"></a> Version 

 Gibt die nachrichtenreservierung einer vorherigen erfolgreichen frei.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `release` Methode.  
  
##  <a name="release_ref"></a> release_ref 

 Gibt einen Verweiszähler für diese `multiple_join` Meldungsblock.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Der Quellblock darf für den Zielblock reservierten Ressourcen freizugeben.  
  
##  <a name="reserve"></a> Hostreserven 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `multitype_join` Meldungsblock.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt reserviert wird.  
  
*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können für viele Gründe, z. B. Fehler auftreten: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, kann die Quelle Reservierungen verweigern und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von `reserve`, wenn dies gelingt, müssen Sie entweder Aufrufen `consume` oder `release` zum Erstellen oder den Besitz der Nachricht bzw. aufgeben.  
  
##  <a name="unlink_target"></a> unlink_target 

 Hebt die Verknüpfung mit einem Zielblock und dadurch `multitype_join` Meldungsblock.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
*_PTarget*<br/>
Ein Zeiger auf ein `ITarget` Block, um diese aufheben `multitype_join` Meldungsblock.  
  
##  <a name="unlink_targets"></a> unlink_targets 

 Hebt die Verknüpfung alle Ziele aus diesem `multitype_join` Meldungsblock.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Choice-Klasse](choice-class.md)   
 [join-Klasse](join-class.md)
