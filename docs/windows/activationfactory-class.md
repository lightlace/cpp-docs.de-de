---
title: ActivationFactory-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2e8256b90b243bc02f9ca5bbfb8ee6a933a7fe4
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788642"
---
# <a name="activationfactory-class"></a>ActivationFactory-Klasse

Ermöglicht, dass eine oder mehrere Klassen durch die Windows-Runtime aktiviert werden.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Parameter

*I0*<br/>
Die nullte-Schnittstelle.

*I1*<br/>
Die erste Schnittstelle.

*I2*<br/>
Die zweite Schnittstelle.

## <a name="remarks"></a>Hinweise

`ActivationFactory` Stellt die Registrierungsmethoden und die grundlegenden Funktionen für die `IActivationFactory` Schnittstelle. `ActivationFactory` Außerdem können Sie eine benutzerdefinierte Factory-Implementierung bereitstellen.

Das folgende Codefragment veranschaulicht symbolisch ActivationFactory verwenden.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]

Das folgende Codefragment zeigt, wie Sie mit der [implementiert](../windows/implements-structure.md) Struktur an mehr als drei Schnittstellen-IDs.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                       | Beschreibung
---------------------------------------------------------- | ------------------------------------------
[Activationfactory:: Activationfactory](#activationfactory) | Initialisiert die `ActivationFactory` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                           | Beschreibung
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[Activationfactory:: AddRef](#addref)                           | Inkrementiert den Verweiszähler des aktuellen `ActivationFactory` Objekt.
[Activationfactory:: Getiids](#getiids)                         | Ruft ein Array von implementierten Schnittstellen-IDs ab.
[Activationfactory:: Getruntimeclassname](#getruntimeclassname) | Ruft den Common Language Runtime-Klassennamen des Objekts ab, die die aktuelle `ActivationFactory` instanziiert.
[Activationfactory:: Gettrustlevel](#gettrustlevel)             | Ruft der Vertrauensebene des Objekts ab, das aktuelle `ActivationFactory` instanziiert.
[Activationfactory:: QueryInterface](#queryinterface)           | Ruft einen Zeiger auf die angegebene Schnittstelle ab.
[Activationfactory:: Release](#release)                         | Dekrementiert den Verweiszähler des aktuellen `ActivationFactory` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="activationfactory"></a>Activationfactory:: Activationfactory

Initialisiert die `ActivationFactory` Klasse.

```cpp
ActivationFactory();
```

## <a name="addref"></a>Activationfactory:: AddRef

Inkrementiert den Verweiszähler des aktuellen `ActivationFactory` Objekt.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="getiids"></a>Activationfactory:: Getiids

Ruft ein Array von implementierten Schnittstellen-IDs ab.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parameter

*iidCount*<br/>
Wenn dieser Vorgang abgeschlossen ist, die Anzahl der interace-IDs in die *Iids* Array.

*IIDs*<br/>
Wenn dieser Vorgang abgeschlossen ist, implementiert ein Array von Schnittstellen-IDs an.

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. E_OUTOFMEMORY ist möglicherweise ein Fehler HRESULT.

## <a name="getruntimeclassname"></a>Activationfactory:: Getruntimeclassname

Ruft den Common Language Runtime-Klassennamen des Objekts ab, die die aktuelle `ActivationFactory` instanziiert.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Parameter

*runtimeName*<br/>
Wenn dieser Vorgang abgeschlossen ist, ein Handle für eine Zeichenfolge, die den Common Language Runtime-Klassennamen des Objekts enthält, die die aktuelle `ActivationFactory` instanziiert.

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="gettrustlevel"></a>Activationfactory:: Gettrustlevel

Ruft der Vertrauensebene des Objekts ab, das aktuelle `ActivationFactory` instanziiert.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Parameter

*trustLvl*<br/>
Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene der Runtime-Klasse, die `ActivationFactory` instanziiert.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; Andernfalls wird ein Assertionsfehler ausgegeben und *TrustLvl* nastaven NA hodnotu `FullTrust`.

## <a name="queryinterface"></a>Activationfactory:: QueryInterface

Ruft einen Zeiger auf die angegebene Schnittstelle ab.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*ppvObject*<br/>
Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf die Schnittstelle, die vom Parameter angegebene *Riid*.

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="release"></a>Activationfactory:: Release

Dekrementiert den Verweiszähler des aktuellen `ActivationFactory` Objekt.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.
