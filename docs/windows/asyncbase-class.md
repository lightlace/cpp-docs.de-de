---
title: AsyncBase-Klasse
ms.date: 10/08/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
- async/Microsoft::WRL::AsyncBase::AsyncBase
- async/Microsoft::WRL::AsyncBase::Cancel
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
- async/Microsoft::WRL::AsyncBase::Close
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
- async/Microsoft::WRL::AsyncBase::CurrentStatus
- async/Microsoft::WRL::AsyncBase::ErrorCode
- async/Microsoft::WRL::AsyncBase::FireCompletion
- async/Microsoft::WRL::AsyncBase::FireProgress
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
- async/Microsoft::WRL::AsyncBase::get_Id
- async/Microsoft::WRL::AsyncBase::get_Status
- async/Microsoft::WRL::AsyncBase::GetOnComplete
- async/Microsoft::WRL::AsyncBase::GetOnProgress
- async/Microsoft::WRL::AsyncBase::OnCancel
- async/Microsoft::WRL::AsyncBase::OnClose
- async/Microsoft::WRL::AsyncBase::OnStart
- async/Microsoft::WRL::AsyncBase::put_Id
- async/Microsoft::WRL::AsyncBase::PutOnComplete
- async/Microsoft::WRL::AsyncBase::PutOnProgress
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
helpviewer_keywords:
- Microsoft::WRL::AsyncBase class
- Microsoft::WRL::AsyncBase::AsyncBase, constructor
- Microsoft::WRL::AsyncBase::Cancel method
- Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall method
- Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall method
- Microsoft::WRL::AsyncBase::Close method
- Microsoft::WRL::AsyncBase::ContinueAsyncOperation method
- Microsoft::WRL::AsyncBase::CurrentStatus method
- Microsoft::WRL::AsyncBase::ErrorCode method
- Microsoft::WRL::AsyncBase::FireCompletion method
- Microsoft::WRL::AsyncBase::FireProgress method
- Microsoft::WRL::AsyncBase::get_ErrorCode method
- Microsoft::WRL::AsyncBase::get_Id method
- Microsoft::WRL::AsyncBase::get_Status method
- Microsoft::WRL::AsyncBase::GetOnComplete method
- Microsoft::WRL::AsyncBase::GetOnProgress method
- Microsoft::WRL::AsyncBase::OnCancel method
- Microsoft::WRL::AsyncBase::OnClose method
- Microsoft::WRL::AsyncBase::OnStart method
- Microsoft::WRL::AsyncBase::put_Id method
- Microsoft::WRL::AsyncBase::PutOnComplete method
- Microsoft::WRL::AsyncBase::PutOnProgress method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
ms.openlocfilehash: 19c4779dbd4d39260d5fe03967e8c0a530a75026
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556919"
---
# <a name="asyncbase-class"></a>AsyncBase-Klasse

Implementiert den asynchronen Zustandsautomat der Windows-Runtime.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename TComplete,
    typename TProgress = Details::Nil,
    AsyncResultType resultType = SingleResult
>
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;

template <typename TComplete, AsyncResultType resultType>
class AsyncBase<TComplete, Details::Nil, resultType> :
    public Microsoft::WRL::Implements<IAsyncInfo>;
```

### <a name="parameters"></a>Parameter

*TComplete*<br/>
Ein Ereignishandler, der aufgerufen wird, wenn ein asynchroner Vorgang abgeschlossen ist.

*TProgress*<br/>
Ein Ereignishandler, der aufgerufen wird, wenn Sie ein aktiven asynchroner Vorgang, den aktuellen Status des Vorgangs meldet.

*ResultType-Element*<br/>
Eines der [AsyncResultType](../windows/asyncresulttype-enumeration.md) -Enumerationswerte fest. In der Standardeinstellung `SingleResult`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                               | Beschreibung
---------------------------------- | -------------------------------------------------
[Asyncbase:: Asyncbase](#asyncbase) | Initialisiert eine Instanz der `AsyncBase`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                         | Beschreibung
-------------------------------------------- | -------------------------------------------------------------------------------------
[Asyncbase:: Cancel](#cancel)                 | Bricht einen asynchronen Vorgang ab.
[Asyncbase:: Close](#close)                   | Schließt den asynchronen Vorgang an.
[Asyncbase:: Firecompletion](#firecompletion) | Ruft den Ereignishandler für den Abschluss, oder setzt den internen Status-Delegaten.
[Asyncbase:: Fireprogress](#fireprogress)     | Ruft den aktuellen Status-Ereignishandler.
[Asyncbase:: Get_errorcode](#get-errorcode)   | Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.
[Asyncbase:: Get_id](#get-id)                 | Ruft das Handle des asynchronen Vorgangs ab.
[Asyncbase:: Get_status](#get-status)         | Ruft einen Wert, der den Status des asynchronen Vorgangs angibt.
[Asyncbase:: Getoncomplete](#getoncomplete)   | Kopiert die Adresse des aktuellen ereignishandlers Abschluss an die angegebene Variable.
[Asyncbase:: Getonprogress](#getonprogress)   | Kopiert die Adresse des aktuellen ereignishandlers Status an die angegebene Variable.
[Asyncbase:: Put_id](#put-id)                 | Legt das Handle des asynchronen Vorgangs fest.
[Asyncbase:: Putoncomplete](#putoncomplete)   | Legt die Adresse des ereignishandlers Abschluss auf den angegebenen Wert fest.
[Asyncbase:: Putonprogress](#putonprogress)   | Legt die Adresse des ereignishandlers Status mit dem angegebenen Wert fest.


### <a name="protected-methods"></a>Geschützte Methoden

Name                                                                         | Beschreibung
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[Asyncbase:: Checkvalidstatefordelegatecall](#checkvalidstatefordelegatecall) | Testet, ob in den aktuellen Status des asynchronen delegateigenschaften geändert werden können.
[Asyncbase:: Checkvalidstateforresultscall](#checkvalidstateforresultscall)   | Testet, ob die Ergebnisse eines asynchronen Vorgangs in den aktuellen asynchronen Zustand erfasst werden können.
[Asyncbase:: Continueasyncoperation](#continueasyncoperation)                 | Bestimmt, ob der asynchrone Vorgang im Fortsetzen der Verarbeitung oder anhalten soll.
[Asyncbase:: currentStatus](#currentstatus)                                   | Ruft den Status der aktuellen asynchronen Vorgang ab.
[Asyncbase:: ErrorCode](#errorcode)                                           | Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.
[Asyncbase:: OnCancel](#oncancel)                                             | Ruft beim Überschreiben in einer abgeleiteten Klasse Bricht einen asynchronen Vorgang ab.
[Asyncbase:: OnClose](#onclose)                                               | Ruft beim Überschreiben in einer abgeleiteten Klasse schließt einen asynchronen Vorgang.
[Asyncbase:: OnStart](#onstart)                                               | Ruft beim Überschreiben in einer abgeleiteten Klasse wird einen asynchronen Vorgang gestartet.
[Asyncbase:: Start](#start)                                                   | Beginnt den asynchronen Vorgang an.
[Asyncbase:: Trytransitiontocompleted](#trytransitiontocompleted)             | Gibt an, ob der aktuelle asynchrone Vorgang abgeschlossen wurde.
[Asyncbase:: Trytransitiontoerror](#trytransitiontoerror)                     | Gibt an, ob der angegebene Fehlercode auf den internen Fehlerzustand ändern kann.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="asyncbase"></a>Asyncbase:: Asyncbase

Initialisiert eine Instanz der `AsyncBase`-Klasse.

```cpp
AsyncBase();
```

## <a name="cancel"></a>Asyncbase:: Cancel

Bricht einen asynchronen Vorgang ab.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Rückgabewert

Standardmäßig gibt stets S_OK zurück.

### <a name="remarks"></a>Hinweise

`Cancel()` ist eine Standardimplementierung der `IAsyncInfo::Cancel`, und keine Arbeit erledigt. Um einen asynchronen Vorgang tatsächlich abgebrochen werden soll, überschreiben die `OnCancel()` rein virtuelle Methode.

## <a name="checkvalidstatefordelegatecall"></a>Asyncbase:: Checkvalidstatefordelegatecall

Testet, ob in den aktuellen Status des asynchronen delegateigenschaften geändert werden können.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn der delegateigenschaften geändert werden können; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="checkvalidstateforresultscall"></a>Asyncbase:: Checkvalidstateforresultscall

Testet, ob die Ergebnisse eines asynchronen Vorgangs in den aktuellen asynchronen Zustand erfasst werden können.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn Ergebnisse erfasst werden können; andernfalls E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="close"></a>Asyncbase:: Close

Schließt den asynchronen Vorgang an.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn der Vorgang geschlossen oder bereits ist geschlossen wurde, andernfalls E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Hinweise

`Close()` ist eine Standardimplementierung der `IAsyncInfo::Close`, und keine Arbeit erledigt. Um einen asynchronen Vorgang tatsächlich zu schließen, außer Kraft setzen der `OnClose()` rein virtuelle Methode.

## <a name="continueasyncoperation"></a>Asyncbase:: Continueasyncoperation

Bestimmt, ob der asynchrone Vorgang im Fortsetzen der Verarbeitung oder anhalten soll.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Rückgabewert

**"true"** ist von der aktuelle Status des asynchronen Vorgangs *Schritte*, was bedeutet, dass den Vorgang sollte weiterhin. Andernfalls **"false"**, was bedeutet, dass den Vorgang sollte beendet werden.

## <a name="currentstatus"></a>Asyncbase:: currentStatus

Ruft den Status der aktuellen asynchronen Vorgang ab.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Parameter

*Status*<br/>
Der Speicherort, in dem dieser Vorgang für den aktuellen Status speichert.

### <a name="remarks"></a>Hinweise

Dieser Vorgang ist threadsicher.

## <a name="errorcode"></a>Asyncbase:: ErrorCode

Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Parameter

*Fehler*<br/>
Der Speicherort, in dem dieser Vorgang den Fehlercode der aktuellen speichert.

### <a name="remarks"></a>Hinweise

Dieser Vorgang ist threadsicher.

## <a name="firecompletion"></a>Asyncbase:: Firecompletion

Ruft den Ereignishandler für den Abschluss, oder setzt den internen Status-Delegaten.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Hinweise

Die erste Version des `FireCompletion()` der Delegatvariablen internen Status zurückgesetzt. Die zweite Version wird der Abschluss-Ereignishandler aufgerufen, wenn der asynchrone Vorgang abgeschlossen ist.

## <a name="fireprogress"></a>Asyncbase:: Fireprogress

Ruft den aktuellen Status-Ereignishandler.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Parameter

*arg*<br/>
Die Ereignishandlermethode aufgerufen.

### <a name="remarks"></a>Hinweise

`ProgressTraits` stammt aus [ArgTraitsHelper-Struktur](../windows/argtraitshelper-structure.md).

## <a name="get-errorcode"></a>Asyncbase:: Get_errorcode

Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Parameter

*errorCode*<br/>
Der Speicherort, in dem der aktuelle Fehlercode gespeichert ist.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL, ob der aktuelle asynchrone Vorgang abgeschlossen ist.

## <a name="get-id"></a>Asyncbase:: Get_id

Ruft das Handle des asynchronen Vorgangs ab.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Der Speicherort, an dem das Handle gespeichert werden.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Hinweise

Diese Methode implementiert `IAsyncInfo::get_Id`.

## <a name="get-status"></a>Asyncbase:: Get_status

Ruft einen Wert, der den Status des asynchronen Vorgangs angibt.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Parameter

*Status*<br/>
Der Speicherort, an dem der Status gespeichert werden. Weitere Informationen finden Sie unter `Windows::Foundation::AsyncStatus` Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Hinweise

Diese Methode implementiert `IAsyncInfo::get_Status`.

## <a name="getoncomplete"></a>Asyncbase:: Getoncomplete

Kopiert die Adresse des aktuellen ereignishandlers Abschluss an die angegebene Variable.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Parameter

*completeHandler*<br/>
Der Speicherort, in dem die Adresse des aktuellen ereignishandlers Abschluss gespeichert ist.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="getonprogress"></a>Asyncbase:: Getonprogress

Kopiert die Adresse des aktuellen ereignishandlers Status an die angegebene Variable.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Parameter

*progressHandler*<br/>
Der Speicherort, in dem die Adresse des aktuellen ereignishandlers Status gespeichert wird.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="oncancel"></a>Asyncbase:: OnCancel

Ruft beim Überschreiben in einer abgeleiteten Klasse Bricht einen asynchronen Vorgang ab.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="onclose"></a>Asyncbase:: OnClose

Ruft beim Überschreiben in einer abgeleiteten Klasse schließt einen asynchronen Vorgang.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="onstart"></a>Asyncbase:: OnStart

Ruft beim Überschreiben in einer abgeleiteten Klasse wird einen asynchronen Vorgang gestartet.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="put-id"></a>Asyncbase:: Put_id

Legt das Handle des asynchronen Vorgangs fest.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Ein ungleich NULL-Handle.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_INVALIDARG oder E_ILLEGAL_METHOD_CALL.

## <a name="putoncomplete"></a>Asyncbase:: Putoncomplete

Legt die Adresse des ereignishandlers Abschluss auf den angegebenen Wert fest.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Parameter

*completeHandler*<br/>
Die Adresse, die auf die der Abschluss-Ereignishandler festgelegt ist.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="putonprogress"></a>Asyncbase:: Putonprogress

Legt die Adresse des ereignishandlers Status mit dem angegebenen Wert fest.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Parameter

*progressHandler*<br/>
Die Adresse, die auf der der Status-Ereignishandler festgelegt ist.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.

## <a name="start"></a>Asyncbase:: Start

Beginnt den asynchronen Vorgang an.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn der Vorgang gestartet oder bereits gestartet. andernfalls E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Hinweise

`Start()` ist eine geschützte Methode, die nicht extern sichtbar ist, da asynchrone Vorgänge "Beginn"Hot"" vor der Rückgabe an den Aufrufer.

## <a name="trytransitiontocompleted"></a>Asyncbase:: Trytransitiontocompleted

Gibt an, ob der aktuelle asynchrone Vorgang abgeschlossen wurde.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der asynchrone Vorgang abgeschlossen wurde, andernfalls **"false"**.

## <a name="trytransitiontoerror"></a>Asyncbase:: Trytransitiontoerror

Gibt an, ob der angegebene Fehlercode auf den internen Fehlerzustand ändern kann.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Parameter

*Fehler*<br/>
Ein fehlerhaftes HRESULT.

### <a name="return-value"></a>Rückgabewert

**"true"** bei der internen Fehlerzustand geändert wurde, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Dieser Vorgang ändert den Status "Fehler" nur dann, wenn der Status "Fehler" S_OK bereits festgelegt ist. Dieser Vorgang hat keine Auswirkungen, wenn der Status "Fehler" bereits angezeigt wird, abgeschlossen, abgebrochen oder geschlossen ist.
