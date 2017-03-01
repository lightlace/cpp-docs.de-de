---
title: Choice-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::choice
dev_langs:
- C++
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
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
ms.openlocfilehash: 1ee8fe2197a41ad2abc14e24c372f808bdbc16d0
ms.lasthandoff: 02/24/2017

---
# <a name="choice-class"></a>choice-Klasse
Ein `choice`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der eine Kontrollflussinteraktion zwischen mehreren Quellen darstellt. Der Auswahlblock wartet, bis eine von mehreren Quellen eine Meldung erzeugt, und gibt den Index der Quelle, von der die Meldung erzeugt wurde, weiter.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein `tuple`-basierten Typ, der die Nutzlasten der Eingabequellen darstellt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Choice-Konstruktor](#ctor)|Überladen. Erstellt einen `choice` -Meldungsblock.|  
|[~ Choice-Destruktor](#dtor)|Zerstört die `choice` Meldungsblocks.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accept-Methode](#accept)|Akzeptiert eine Meldung, die von diesem angeboten wurde `choice` Block überträgt den Besitz an den Aufrufer.|  
|[Acquire_ref-Methode](#acquire_ref)|Ruft eine Verweisanzahl für diesen `choice` -Meldungsblock ab, um den Löschvorgang zu verhindern.|  
|[Consume-Methode](#consume)|Nimmt eine Meldung, die zuvor von diesem angebotenen `choice` -Meldungsblock und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.|  
|[Has_value-Methode](#has_value)|Überprüft, ob diese `choice` -Meldungsblock noch mit einem Wert initialisiert wurde.|  
|[Index-Methode](#index)|Gibt einen Index in der `tuple` , die vom ausgewählten Element darstellt, das `choice` Meldungsblocks.|  
|[Link_target-Methode](#link_target)|Verknüpft einen Zielblock mit diesem `choice` Meldungsblocks.|  
|[Release-Methode](#release)|Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[Release_ref-Methode](#release_ref)|Gibt einen Verweiszähler für diese `choice` Meldungsblocks.|  
|[Reserve-Methode](#reserve)|Reserviert eine Meldung, die zuvor von diesem angebotenen `choice` Meldungsblocks.|  
|[Unlink_target-Methode](#unlink_target)|Hebt die Verknüpfung mit einem Zielblock aus diesem `choice` Meldungsblocks.|  
|[Unlink_targets-Methode](#unlink_targets)|Hebt die Verknüpfung aller Ziele mit diesem `choice` Meldungsblocks. (Überschreibt [ISource:: Unlink_targets](isource-class.md#unlink_targets).)|  
|[Wert-Methode](#value)|Ruft die Meldung ab, deren Index, indem ausgewählt wurde, die `choice` Meldungsblocks.|  
  
## <a name="remarks"></a>Hinweise  
 Der Auswahlblock stellt sicher, dass nur eine der eingehenden Nachrichten verwendet wird.  
  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>akzeptieren 

 Akzeptiert eine Meldung, die von diesem angeboten wurde `choice` Block überträgt den Besitz an den Aufrufer.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der angebotenen `message` Objekt.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `accept` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Meldung, der der Aufrufer nun Eigentümer ist.  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 Ruft eine Verweisanzahl für diesen `choice` -Meldungsblock ab, um den Löschvorgang zu verhindern.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, ist die `link_target` Methode.  
  
##  <a name="a-namectora-choice"></a><a name="ctor"></a>Auswahl 

 Erstellt einen `choice` -Meldungsblock.  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>Parameter  
 `_Tuple`  
 Ein `tuple` von Quellen für die Auswahl.  
  
 `_PScheduler`  
 Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist.  
  
 `_PScheduleGroup`  
 Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.  
  
 `_Choice`  
 Ein `choice` -Meldungsblock, aus dem kopiert werden soll. Beachten Sie, dass das ursprüngliche Objekt verwaist ist, sodass dies ein Bewegungskonstruktor ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.  
  
 Bewegungskonstruktion wird bei einer aktiven Sperre nicht ausgeführt, d. h., der Benutzer muss sicherstellen, dass zum Zeitpunkt der Bewegung keine einfachen Aufgaben aktiv sind. Andernfalls können zahlreiche Wettläufe auftreten, wodurch Ausnahmen oder inkonsistente Zuständen verursacht werden.  
  
##  <a name="a-namedtora-choice"></a><a name="dtor"></a>~ Wahl 

 Zerstört die `choice` Meldungsblocks.  
  
```  
~choice();
```  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>Nutzen 

 Nimmt eine Meldung, die zuvor von diesem angebotenen `choice` -Meldungsblock und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 Überprüft, ob diese `choice` -Meldungsblock noch mit einem Wert initialisiert wurde.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Block einen Wert empfangen hat `false` andernfalls.  
  
##  <a name="a-nameindexa-index"></a><a name="index"></a>Index 

 Gibt einen Index in der `tuple` , die vom ausgewählten Element darstellt, das `choice` Meldungsblocks.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Nachrichtenindex.  
  
### <a name="remarks"></a>Hinweise  
 Die Nachrichtennutzlast mit extrahiert die `get` Methode.  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 Verknüpft einen Zielblock mit diesem `choice` Meldungsblocks.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Herstellen eines Links `choice` Meldungsblocks.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Version 

 Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von der `message` Objekt freigegeben wird.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `release` Methode.  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 Gibt einen Verweiszähler für diese `choice` Meldungsblocks.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierte Ressourcen freizugeben.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Reservieren 

 Reserviert eine Meldung, die zuvor von diesem angebotenen `choice` Meldungsblocks.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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

 Hebt die Verknüpfung mit einem Zielblock aus diesem `choice` Meldungsblocks.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Aufheben der Verknüpfung von diesem `choice` Meldungsblocks.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 Hebt die Verknüpfung aller Ziele mit diesem `choice` Meldungsblocks.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode muss nicht vom Destruktor aufgerufen werden, da der Destruktor für die interne `single_assignment` Block ordnungsgemäß Verknüpfung.  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>Wert 

 Ruft die Meldung ab, deren Index, indem ausgewählt wurde, die `choice` Meldungsblocks.  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>Parameter  
 `_Payload_type`  
 Der Typ der Nutzlast der Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Nutzlast der Nachricht.  
  
### <a name="remarks"></a>Hinweise  
 Da eine `choice` -Meldungsblock Eingaben mit anderen Nutzlasttypen annehmen kann, müssen Sie den Typ der Nutzlast beim Abruf angeben. Sie können den Typ anhand des Ergebnisses der bestimmen die `index` Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Join-Klasse](join-class.md)   
 [Single_assignment-Klasse](single-assignment-class.md)

