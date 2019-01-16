---
title: ClassFactory-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: ccc1c43e8c68053a773883c25704cdea086bd0b1
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335985"
---
# <a name="classfactory-class"></a>ClassFactory-Klasse

Implementiert die grundlegende Funktion der `IClassFactory`-Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
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

Nutzen `ClassFactory` eine benutzerdefinierte Factoryimplementierung bereitstellen.

Das folgende Muster für die Programmierung veranschaulicht, wie die [implementiert](implements-structure.md) Struktur, die mehr als drei Schnittstellen für eine Klassenfactory angeben.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                        | Beschreibung
------------------------------------------- | -----------
[ClassFactory::ClassFactory](#classfactory) |

### <a name="public-methods"></a>Öffentliche Methoden

Name                                            | Beschreibung
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory::AddRef](#addref)                 | Inkrementiert den Verweiszähler für den aktuellen `ClassFactory` Objekt.
[ClassFactory::LockServer](#lockserver)         | Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte nachverfolgt werden, von der aktuellen `ClassFactory` Objekt.
[ClassFactory::QueryInterface](#queryinterface) | Ruft einen Zeiger auf die Schnittstelle, die durch Parameter angegeben wird.
[ClassFactory::Release](#release)               | Dekrementiert den Verweiszähler für den aktuellen `ClassFactory` Objekt.

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

`ClassFactory`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="addref"></a>ClassFactory::AddRef

Inkrementiert den Verweiszähler für den aktuellen `ClassFactory` Objekt.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="classfactory"></a>ClassFactory::ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="lockserver"></a>ClassFactory::LockServer

Erhöht oder verringert die Anzahl der zugrunde liegenden Objekte nachverfolgt werden, von der aktuellen `ClassFactory` Objekt.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Parameter

*fLock*<br/>
**"true"** erhöht die Anzahl der überwachten Objekte. **"false"** um die Anzahl der überwachten Objekte zu verringern.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_FAIL.

### <a name="remarks"></a>Hinweise

`ClassFactory` verfolgt des Objekte in einer zugrunde liegenden Instanz, von der [Modul](module-class.md) Klasse.

## <a name="queryinterface"></a>ClassFactory::QueryInterface

Ruft einen Zeiger auf die Schnittstelle, die durch Parameter angegeben wird.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*ppvObject*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf die Schnittstelle, die vom Parameter angegebene *Riid*.

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="release"></a>ClassFactory::Release

Dekrementiert den Verweiszähler für den aktuellen `ClassFactory` Objekt.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.
