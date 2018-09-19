---
title: RuntimeClass-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3bc016367495be8cc10c09605e8018811bde5ca9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118907"
---
# <a name="runtimeclass-class"></a>RuntimeClass-Klasse

Stellt eine WinRT oder COM-Klasse, die die angegebene Schnittstelle erbt und die angegebenen Windows-Runtime, Klassisches COM und schwachen Verweis-Unterstützung.

Diese Klasse stellt die Codebausteine-Implementierung von WinRT und COM-Klassen, die die Implementierung von `QueryInterface`, `AddRef`, `Release` usw. verwaltet den Verweiszähler des Moduls und verfügt über Unterstützung für die Bereitstellung der Klassenfactory für aktivierbare Objekte.

## <a name="syntax"></a>Syntax

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Parameter

*classFlags*  
Optionale Parameter. Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) -Enumerationswerte fest. Die `__WRL_CONFIGURATION_LEGACY__` Makro definiert werden kann, um den Standardwert ClassFlags für alle Common Language Runtime-Klassen im Projekt zu ändern. Wenn definiert, sind RuntimeClass-Instanzen standardmäßig nicht agile. Wenn Sie nicht definiert ist, sind RuntimeClass-Instanzen standardmäßig agile. Um zu vermeiden Mehrdeutigkeit Geben Sie immer die `Microsoft::WRL::FtmBase` in `TInterfaces` oder `RuntimeClassType::InhibitFtmBase`. Beachten Sie, wenn InhibitFtmBase und FtmBase sind, dass sowohl das Objekt verwendet, werden als agile.

*TInterfaces*  
Die Liste der Schnittstellen das Objekt implementiert, über `IUnknown`, `IInspectable` oder anderen Schnittstellen gesteuert durch [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Kann auch andere Klassen von, abgeleitet werden, insbesondere auflisten `Microsoft::WRL::FtmBase` agil machen, das Objekt, und dazu führen, dass implementieren `IMarshal`.

## <a name="members"></a>Member

`RuntimeClassInitialize`<br/>
Eine Funktion, die das Objekt initialisiert, wenn die `MakeAndInitialize` Vorlagenfunktion zum Erstellen des Objekts verwendet wird. Es gibt S_OK zurück, wenn das Objekt erfolgreich initialisiert wurde, oder eine COM-Fehlercode zurück, wenn Fehler bei der Initialisierung. Die COM-Fehlercode als Rückgabewert der weitergegeben wird `MakeAndInitialize`. Beachten Sie, dass die `RuntimeClassInitialize` Methode wird nicht aufgerufen, wenn die `Make` Vorlagenfunktion zum Erstellen des Objekts verwendet wird.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

| Name                                               | Beschreibung                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [Runtimeclass:: Runtimeclass](#runtimeclass)        | Initialisiert die aktuelle Instanz von der `RuntimeClass` Klasse.   |
| [RuntimeClass:: ~ RuntimeClass](#tilde-runtimeclass) | Hebt die Initialisierung der aktuellen Instanz von der `RuntimeClass` Klasse. |

### <a name="public-methods"></a>Öffentliche Methoden

| Name                                                      | Beschreibung                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [Runtimeclass:: AddRef](#addref)                           | Inkrementiert den Verweiszähler für den aktuellen `RuntimeClass` Objekt.                              |
| [Runtimeclass:: Decrementreference](#decrementreference)   | Dekrementiert den Verweiszähler für den aktuellen `RuntimeClass` Objekt.                              |
| [Runtimeclass:: Getiids](#getiids)                         | Ruft ein Array, das die Schnittstellen-IDs, die von der aktuellen Implementierung darf `RuntimeClass` Objekt. |
| [Runtimeclass:: Getruntimeclassname](#getruntimeclassname) | Ruft den Common Language Runtime-Klassennamen des aktuellen `RuntimeClass` Objekt.                                  |
| [Runtimeclass:: Gettrustlevel](#gettrustlevel)             | Ruft die Vertrauensebene des aktuellen `RuntimeClass` Objekt.                                         |
| [Runtimeclass:: Getweakreference](#getweakreference)       | Ruft einen Zeiger auf das schwachen Verweis-Objekt ab, für die aktuelle `RuntimeClass` Objekt.                 |
| [Runtimeclass:: Internaladdref](#internaladdref)           | Inkrementiert den Verweiszähler der aktuellen `RuntimeClass` Objekt.                               |
| [Runtimeclass:: QueryInterface](#queryinterface)           | Ruft einen Zeiger auf die angegebene Schnittstellen-ID.                                                 |
| [Runtimeclass:: Release](#release)                         | Führt einen COM-Freigabe-Vorgang für die aktuelle `RuntimeClass` Objekt.                             |

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

Dies ist ein Implementierungsdetail.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="tilde-runtimeclass"></a>RuntimeClass:: ~ RuntimeClass

Hebt die Initialisierung der aktuellen Instanz von der `RuntimeClass` Klasse.

```cpp
virtual ~RuntimeClass();
```

## <a name="addref"></a>Runtimeclass:: AddRef

Inkrementiert den Verweiszähler für den aktuellen `RuntimeClass` Objekt.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="decrementreference"></a>Runtimeclass:: Decrementreference

Dekrementiert den Verweiszähler für den aktuellen `RuntimeClass` Objekt.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="getiids"></a>Runtimeclass:: Getiids

Ruft ein Array, das die Schnittstellen-IDs, die von der aktuellen Implementierung darf `RuntimeClass` Objekt.

```cpp
STDMETHOD(
   GetIids
)  
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parameter

*iidCount*  
Wenn dieser Vorgang abgeschlossen ist, die Gesamtzahl der Elemente im Array *Iids*.

*IIDs*  
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf ein Array von Schnittstellen-IDs.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_OUTOFMEMORY.

## <a name="getruntimeclassname"></a>Runtimeclass:: Getruntimeclassname

Ruft den Common Language Runtime-Klassennamen des aktuellen `RuntimeClass` Objekt.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parameter

*runtimeName*  
Wenn dieser Vorgang abgeschlossen ist, den Namen der Common Language Runtime-Klasse.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Ein Assert-Fehler wird ausgegeben, wenn `__WRL_STRICT__` oder `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` ist nicht definiert.

## <a name="gettrustlevel"></a>Runtimeclass:: Gettrustlevel

Ruft die Vertrauensebene des aktuellen `RuntimeClass` Objekt.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parameter

*trustLvl*  
Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene des aktuellen `RuntimeClass` Objekt.

### <a name="return-value"></a>Rückgabewert

Stets S_OK.

### <a name="remarks"></a>Hinweise

Ein Assert-Fehler wird ausgegeben, wenn `__WRL_STRICT__` oder `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` ist nicht definiert.

## <a name="getweakreference"></a>Runtimeclass:: Getweakreference

Ruft einen Zeiger auf das schwachen Verweis-Objekt ab, für die aktuelle `RuntimeClass` Objekt.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Parameter

*weakReference*  
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf einen schwachen Verweis-Objekt.

### <a name="return-value"></a>Rückgabewert

Stets S_OK.

## <a name="internaladdref"></a>Runtimeclass:: Internaladdref

Inkrementiert den Verweiszähler der aktuellen `RuntimeClass` Objekt.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Rückgabewert

Der resultierende Verweiszähler.

## <a name="queryinterface"></a>Runtimeclass:: QueryInterface

Ruft einen Zeiger auf die angegebene Schnittstellen-ID.

```cpp
STDMETHOD(
   QueryInterface
)  
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parameter

*riid*  
Eine Schnittstellen-ID.

*ppvObject*  
Wenn diese Opereation abgeschlossen ist, einen Zeiger auf die angegebene Schnittstelle die *Riid* Parameter.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="release"></a>Runtimeclass:: Release

Führt einen COM-Freigabe-Vorgang für die aktuelle `RuntimeClass` Objekt.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Wenn der Verweiszähler NULL ist, wird die `RuntimeClass` Objekt wird gelöscht.

## <a name="runtimeclass"></a>Runtimeclass:: Runtimeclass

Initialisiert die aktuelle Instanz von der `RuntimeClass` Klasse.

```cpp
RuntimeClass();
```
