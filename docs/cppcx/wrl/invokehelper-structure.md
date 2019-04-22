---
title: InvokeHelper-Struktur
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 3fcba210d4018d22487d234b437acfee3634cec6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785163"
---
# <a name="invokehelper-structure"></a>InvokeHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>Parameter

*TDelegateInterface*<br/>
Der Typ des Delegaten-Schnittstelle.

*TCallback*<br/>
Der Typ des Ereignishandlerfunktion.

*argCount*<br/>
Die Anzahl von Argumenten in eine `InvokeHelper` Spezialisierung.

## <a name="remarks"></a>Hinweise

Stellt eine Implementierung der `Invoke()` -Methode basierend auf der angegebenen Nummer und Typ der Argumente.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name     | Beschreibung
-------- | -----------------------------------------------------------------------------
`Traits` | Ein Synonym für die Klasse, die den Typ jedes Arguments der Ereignis-Handler definiert.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                        | Beschreibung
------------------------------------------- | -------------------------------------------------------
[InvokeHelper::InvokeHelper](#invokehelper) | Initialisiert eine neue Instanz der `InvokeHelper`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                            | Beschreibung
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper::Invoke](#invoke) | Ruft den Ereignishandler, dessen Signatur mit die angegebene Anzahl von Argumenten enthält.

### <a name="public-data-members"></a>Öffentliche Datenmember

Name                                 | Beschreibung
------------------------------------ | ----------------------------------------------------------
[InvokeHelper::callback_](#callback) | Stellt den Ereignishandler aufgerufen wird, wenn ein Ereignis auftritt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InvokeHelper`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="callback"></a>InvokeHelper::callback_

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Hinweise

Stellt den Ereignishandler aufgerufen wird, wenn ein Ereignis auftritt.

Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.

## <a name="invoke"></a>InvokeHelper::Invoke

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>Parameter

*arg1*<br/>
Das Argument 1.

*arg2*<br/>
Argument 2.

*arg3*<br/>
Argument 3.

*arg4*<br/>
4-Argument.

*arg5*<br/>
5-Argument.

*arg6*<br/>
6-Argument.

*arg7*<br/>
7-Argument.

*arg8*<br/>
8-Argument.

*arg9*<br/>
9-Argument.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

### <a name="remarks"></a>Hinweise

Ruft den Ereignishandler, dessen Signatur mit die angegebene Anzahl von Argumenten enthält.

## <a name="invokehelper"></a>InvokeHelper::InvokeHelper

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parameter

*callback*<br/>
Ein Ereignishandler.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `InvokeHelper`-Klasse.

Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.
