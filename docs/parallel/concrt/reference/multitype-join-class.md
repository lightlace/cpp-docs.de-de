---
title: Multitype_join-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a53206c32b59ab5cac9f14d51bed42a4870b94fa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 `T`  
 Die `tuple` Nutzlasttyp der Nachrichten hinzugefügt und vom Block weitergegeben.  
  
 `_Jtype`  
 Die Art der `join` Blocks, entweder `greedy` oder`non_greedy`  
  
## <a name="members"></a>Mitglieder  
  
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
|[akzeptieren](#accept)|Akzeptiert eine Meldung, die von diesem angeboten wurde `multitype_join` -Block übertragen des Besitzes an den Aufrufer.|  
|[acquire_ref](#acquire_ref)|Ruft eine Verweisanzahl für dieses `multitype_join` Meldungsblock, um den Löschvorgang zu verhindern.|  
|[Nutzen](#consume)|Nimmt eine Meldung, die zuvor von Angeboten die `multitype_join` -Meldungsblock und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.|  
|[link_target](#link_target)|Verknüpft einen Zielblock mit diesem `multitype_join` Meldungsblock.|  
|[release](#release)|Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[release_ref](#release_ref)|Gibt einen Verweiszähler für dieses `multiple_join` Meldungsblock.|  
|[reserve](#reserve)|Reserviert eine Meldung, die zuvor von diesem angebotenen `multitype_join` Meldungsblock.|  
|[unlink_target](#unlink_target)|Hebt die Verknüpfung mit einem Zielblock und dies `multitype_join` Meldungsblock.|  
|[unlink_targets](#unlink_targets)|Hebt die Verknüpfung mit allen Zielen, die von diesem `multitype_join` Meldungsblock. (Überschreibt [ISource:: Unlink_targets](isource-class.md#unlink_targets).)|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="accept"></a>akzeptieren 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `multitype_join` -Block übertragen des Besitzes an den Aufrufer.  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun den Besitz von verfügt.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Ruft eine Verweisanzahl für dieses `multitype_join` Meldungsblock, um den Löschvorgang zu verhindern.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, wird die `link_target` Methode.  
  
##  <a name="consume"></a>Nutzen 

 Nimmt eine Meldung, die zuvor von Angeboten die `multitype_join` -Meldungsblock und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
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
  
##  <a name="link_target"></a>link_target 

 Verknüpft einen Zielblock mit diesem `multitype_join` Meldungsblock.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf ein `ITarget` Block, mit dem Verknüpfen dieser `multitype_join` Meldungsblock.  
  
##  <a name="ctor"></a>multitype_join 

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
 `_Tuple`  
 Ein `tuple` von Quellen für diesen `multitype_join` -Meldungsblock.  
  
 `_PScheduler`  
 Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.  
  
 `_PScheduleGroup`  
 Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
 `_Join`  
 Ein `multitype_join` -Meldungsblock, aus dem kopiert werden soll. Beachten Sie, dass das ursprüngliche Objekt verwaist ist, sodass dies ein Bewegungskonstruktor ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.  
  
 Bewegungskonstruktion wird bei einer aktiven Sperre nicht ausgeführt, d. h., der Benutzer muss sicherstellen, dass zum Zeitpunkt der Bewegung keine einfachen Aufgaben aktiv sind. Andernfalls können zahlreiche Wettläufe auftreten, wodurch Ausnahmen oder inkonsistente Zuständen verursacht werden.  
  
##  <a name="dtor"></a>~ Multitype_join 

 Zerstört die `multitype_join` Meldungsblock.  
  
```  
~multitype_join();
```  
  
##  <a name="release"></a>Version 

 Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `release` Methode.  
  
##  <a name="release_ref"></a>release_ref 

 Gibt einen Verweiszähler für dieses `multiple_join` Meldungsblock.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das aus dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierten Ressourcen freizugeben.  
  
##  <a name="reserve"></a>Reservieren 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `multitype_join` Meldungsblock.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt reserviert wird.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können viele Gründe geben, einschließlich fehl: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, die Quelle konnte verweigern Reservierungen usw..  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `reserve`, wenn er erfolgreich ausgeführt wird, müssen Sie entweder Aufrufen `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="unlink_target"></a>unlink_target 

 Hebt die Verknüpfung mit einem Zielblock und dies `multitype_join` Meldungsblock.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf ein `ITarget` Block zum Aufheben der Verknüpfung von diesem `multitype_join` Meldungsblock.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Hebt die Verknüpfung mit allen Zielen, die von diesem `multitype_join` Meldungsblock.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Choice-Klasse](choice-class.md)   
 [join-Klasse](join-class.md)
