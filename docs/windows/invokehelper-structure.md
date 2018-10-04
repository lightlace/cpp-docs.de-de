---
title: InvokeHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 46cd067e41fcc9ac0d8d3dd9fe50c9edd23532c3
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789110"
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
*TCallback*  
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
[InvokeHelper:: InvokeHelper](#invokehelper) | Initialisiert eine neue Instanz der `InvokeHelper`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                            | Beschreibung
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper:: Invoke](#invoke) | Ruft den Ereignishandler, dessen Signatur mit die angegebene Anzahl von Argumenten enthält.

### <a name="public-data-members"></a>Öffentliche Datenmember

Name                                 | Beschreibung
------------------------------------ | ----------------------------------------------------------
[InvokeHelper:: Callback_](#callback) | Stellt den Ereignishandler aufgerufen wird, wenn ein Ereignis auftritt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InvokeHelper`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="callback"></a>InvokeHelper:: Callback_

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Hinweise

Stellt den Ereignishandler aufgerufen wird, wenn ein Ereignis auftritt.

Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.

## <a name="invoke"></a>InvokeHelper:: Invoke

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

*Arg2*<br/>
Argument 2.

*Arg3*<br/>
Argument 3.

*Arg4*<br/>
4-Argument.

*Arg5*<br/>
5-Argument.

*Arg6*<br/>
6-Argument.

*Arg7*<br/>
7-Argument.

*Arg8*<br/>
8-Argument.

*Arg9*<br/>
9-Argument.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

### <a name="remarks"></a>Hinweise

Ruft den Ereignishandler, dessen Signatur mit die angegebene Anzahl von Argumenten enthält.

## <a name="invokehelper"></a>InvokeHelper:: InvokeHelper

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Parameter

*Rückruf*<br/>
Ein Ereignishandler.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `InvokeHelper`-Klasse.

Die `TCallback` Template-Parameter gibt den Typ des ereignishandlers.
