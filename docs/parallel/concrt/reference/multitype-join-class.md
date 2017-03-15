---
title: Multitype_join-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::multitype_join
dev_langs:
- C++
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
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
ms.openlocfilehash: 71f644331cbaef8322176e554c52a14d59f6d75a
ms.lasthandoff: 02/24/2017

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
 Die `tuple` der Nutzlasttyp der Nachrichten hinzugefügt und vom Block weitergegeben.  
  
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
|[Multitype_join-Konstruktor](#ctor)|Überladen. Erstellt einen `multitype_join` -Meldungsblock.|  
|[~ Multitype_join-Destruktor](#dtor)|Zerstört die `multitype_join` Meldungsblocks.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accept-Methode](#accept)|Akzeptiert eine Meldung, die von diesem angeboten wurde `multitype_join` Block überträgt den Besitz an den Aufrufer.|  
|[Acquire_ref-Methode](#acquire_ref)|Ruft eine Verweisanzahl für diesen `multitype_join` -Meldungsblock ab, um den Löschvorgang zu verhindern.|  
|[Consume-Methode](#consume)|Nimmt eine Meldung, die zuvor von Angeboten der `multitype_join` -Meldungsblock und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.|  
|[Link_target-Methode](#link_target)|Verknüpft einen Zielblock mit diesem `multitype_join` Meldungsblocks.|  
|[Release-Methode](#release)|Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[Release_ref-Methode](#release_ref)|Gibt einen Verweiszähler für diese `multiple_join` Meldungsblocks.|  
|[Reserve-Methode](#reserve)|Reserviert eine Meldung, die zuvor von diesem angebotenen `multitype_join` Meldungsblocks.|  
|[Unlink_target-Methode](#unlink_target)|Hebt die Verknüpfung mit einem Zielblock aus diesem `multitype_join` Meldungsblocks.|  
|[Unlink_targets-Methode](#unlink_targets)|Hebt die Verknüpfung aller Ziele mit diesem `multitype_join` Meldungsblocks. (Überschreibt [ISource:: Unlink_targets](isource-class.md#unlink_targets).)|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>akzeptieren 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `multitype_join` Block überträgt den Besitz an den Aufrufer.  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun Eigentümer ist.  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 Ruft eine Verweisanzahl für diesen `multitype_join` -Meldungsblock ab, um den Löschvorgang zu verhindern.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, ist die `link_target` Methode.  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>Nutzen 

 Nimmt eine Meldung, die zuvor von Angeboten der `multitype_join` -Meldungsblock und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
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
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 Verknüpft einen Zielblock mit diesem `multitype_join` Meldungsblocks.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Herstellen eines Links `multitype_join` Meldungsblocks.  
  
##  <a name="a-namectora-multitypejoin"></a><a name="ctor"></a>multitype_join 

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
  
##  <a name="a-namedtora-multitypejoin"></a><a name="dtor"></a>~ Multitype_join 

 Zerstört die `multitype_join` Meldungsblocks.  
  
```  
~multitype_join();
```  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Version 

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
 Ein Zeiger auf den Zielblock, der den Aufruf der `release` Methode.  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 Gibt einen Verweiszähler für diese `multiple_join` Meldungsblocks.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierte Ressourcen freizugeben.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Reservieren 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `multitype_join` Meldungsblocks.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` -Objekt reserviert wird.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können viele Ursachen haben, z. B. fehlschlagen: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, konnte die Quelle Reservierungen verweigern und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von `reserve`, das erfolgreich ist, rufen Sie entweder `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 Hebt die Verknüpfung mit einem Zielblock aus diesem `multitype_join` Meldungsblocks.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Aufheben der Verknüpfung von diesem `multitype_join` Meldungsblocks.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 Hebt die Verknüpfung aller Ziele mit diesem `multitype_join` Meldungsblocks.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Choice-Klasse](choice-class.md)   
 [Join-Klasse](join-class.md)

