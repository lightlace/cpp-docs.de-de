---
title: "choice-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::choice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "choice-Klasse"
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# choice-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

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
|[Choice:: choice-Konstruktor](#choice__choice_constructor)|Überladen. Erstellt einen `choice` -Meldungsblock.|  
|[Choice:: ~ Choice-Destruktor](#choice___dtorchoice_destructor)|Zerstört die `choice` Meldungsblocks.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Choice:: Accept-Methode](#choice__accept_method)|Akzeptiert eine Meldung, die von diesem angeboten wurde `choice` Block überträgt den Besitz an den Aufrufer.|  
|[Choice:: acquire_ref-Methode](#choice__acquire_ref_method)|Ruft eine Verweisanzahl für diesen `choice` -Meldungsblock ab, um den Löschvorgang zu verhindern.|  
|[Choice:: Consume-Methode](#choice__consume_method)|Nimmt eine Meldung, die zuvor von diesem angebotenen `choice` -Meldungsblock und erfolgreich vom Ziel reserviert wurde, überträgt den Besitz an den Aufrufer.|  
|[Choice:: has_value-Methode](#choice__has_value_method)|Überprüft, ob diese `choice` -Meldungsblock noch mit einem Wert initialisiert wurde.|  
|[Choice:: Index-Methode](#choice__index_method)|Gibt einen Index in der `tuple` die vom ausgewählten Element darstellt, das `choice` Meldungsblocks.|  
|[Choice:: link_target-Methode](#choice__link_target_method)|Verknüpft einen Zielblock mit diesem `choice` Meldungsblocks.|  
|[Choice:: Release-Methode](#choice__release_method)|Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.|  
|[Choice:: release_ref-Methode](#choice__release_ref_method)|Gibt einen Verweiszähler für diese `choice` Meldungsblocks.|  
|[Choice:: Reserve-Methode](#choice__reserve_method)|Reserviert eine Meldung, die zuvor von diesem angebotenen `choice` Meldungsblocks.|  
|[Choice:: unlink_target-Methode](#choice__unlink_target_method)|Hebt die Verknüpfung mit einem Zielblock aus diesem `choice` Meldungsblocks.|  
|[Choice:: unlink_targets-Methode](#choice__unlink_targets_method)|Hebt die Verknüpfung aller Ziele mit diesem `choice` Meldungsblocks. (Überschreibt [ISource:: Unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
|[Choice:: Value-Methode](#choice__value_method)|Ruft die Meldung ab, deren Index, indem ausgewählt wurde, die `choice` Meldungsblocks.|  
  
## <a name="remarks"></a>Hinweise  
 Der Auswahlblock stellt sicher, dass nur eine der eingehenden Nachrichten verwendet wird.  
  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namechoiceacceptmethoda-choiceaccept-method"></a><a name="choice__accept_method"></a>  Choice:: Accept-Methode  
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
  
##  <a name="a-namechoiceacquirerefmethoda-choiceacquireref-method"></a><a name="choice__acquire_ref_method"></a>  Choice:: acquire_ref-Methode  
 Ruft eine Verweisanzahl für diesen `choice` -Meldungsblock ab, um den Löschvorgang zu verhindern.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit dieser Quelle während verknüpft wird, ist die `link_target` Methode.  
  
##  <a name="a-namechoicechoiceconstructora-choicechoice-constructor"></a><a name="choice__choice_constructor"></a>  Choice:: choice-Konstruktor  
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
  
##  <a name="a-namechoicedtorchoicedestructora-choicechoice-destructor"></a><a name="choice___dtorchoice_destructor"></a>  Choice:: ~ Choice-Destruktor  
 Zerstört die `choice` Meldungsblocks.  
  
```  
~choice();
```  
  
##  <a name="a-namechoiceconsumemethoda-choiceconsume-method"></a><a name="choice__consume_method"></a>  Choice:: Consume-Methode  
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
  
##  <a name="a-namechoicehasvaluemethoda-choicehasvalue-method"></a><a name="choice__has_value_method"></a>  Choice:: has_value-Methode  
 Überprüft, ob diese `choice` -Meldungsblock noch mit einem Wert initialisiert wurde.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der Block einen Wert empfangen hat `false` andernfalls.  
  
##  <a name="a-namechoiceindexmethoda-choiceindex-method"></a><a name="choice__index_method"></a>  Choice:: Index-Methode  
 Gibt einen Index in der `tuple` die vom ausgewählten Element darstellt, das `choice` Meldungsblocks.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Nachrichtenindex.  
  
### <a name="remarks"></a>Hinweise  
 Die Nachrichtennutzlast mit extrahiert die `get` Methode.  
  
##  <a name="a-namechoicelinktargetmethoda-choicelinktarget-method"></a><a name="choice__link_target_method"></a>  Choice:: link_target-Methode  
 Verknüpft einen Zielblock mit diesem `choice` Meldungsblocks.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Herstellen eines Links `choice` Meldungsblocks.  
  
##  <a name="a-namechoicereleasemethoda-choicerelease-method"></a><a name="choice__release_method"></a>  Choice:: Release-Methode  
 Gibt die Reservierung einer vorherigen erfolgreichen Meldung frei.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von den `message` Objekt freigegeben wird.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `release` Methode.  
  
##  <a name="a-namechoicereleaserefmethoda-choicereleaseref-method"></a><a name="choice__release_ref_method"></a>  Choice:: release_ref-Methode  
 Gibt einen Verweiszähler für diese `choice` Meldungsblocks.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der diese Methode aufruft.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Quellblock darf für den Zielblock reservierte Ressourcen freizugeben.  
  
##  <a name="a-namechoicereservemethoda-choicereserve-method"></a><a name="choice__reserve_method"></a>  Choice:: Reserve-Methode  
 Reserviert eine Meldung, die zuvor von diesem angebotenen `choice` Meldungsblocks.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_MsgId`  
 Die `runtime_object_identity` von den `message` -Objekt reserviert wird.  
  
 `_PTarget`  
 Ein Zeiger auf den Zielblock, der den Aufruf der `reserve` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls. Reservierungen können viele Ursachen haben, z. B. fehlschlagen: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, konnte die Quelle Reservierungen verweigern und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von `reserve`, das erfolgreich ist, rufen Sie entweder `consume` oder `release` um übernehmen oder der Besitz der Nachricht bzw. abzugeben.  
  
##  <a name="a-namechoiceunlinktargetmethoda-choiceunlinktarget-method"></a><a name="choice__unlink_target_method"></a>  Choice:: unlink_target-Methode  
 Hebt die Verknüpfung mit einem Zielblock aus diesem `choice` Meldungsblocks.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `_PTarget`  
 Ein Zeiger auf eine `ITarget` Block zum Aufheben der Verknüpfung von diesem `choice` Meldungsblocks.  
  
##  <a name="a-namechoiceunlinktargetsmethoda-choiceunlinktargets-method"></a><a name="choice__unlink_targets_method"></a>  Choice:: unlink_targets-Methode  
 Hebt die Verknüpfung aller Ziele mit diesem `choice` Meldungsblocks.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode muss nicht vom Destruktor aufgerufen werden, da der Destruktor für die interne `single_assignment` Block ordnungsgemäß Verknüpfung.  
  
##  <a name="a-namechoicevaluemethoda-choicevalue-method"></a><a name="choice__value_method"></a>  Choice:: Value-Methode  
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
 [Concurrency-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Join-Klasse](../../../parallel/concrt/reference/join-class.md)   
 [Single_assignment-Klasse](../../../parallel/concrt/reference/single-assignment-class.md)
