---
title: InterfaceTraits-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: e8222ccaca9572331412b90e696829568eedcf8e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785498"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Parameter

*I0*<br/>
Der Name einer Schnittstelle.

*CloakedType*<br/>
Für `RuntimeClass`, `Implements` und `ChainInterfaces`, eine Schnittstelle, die in der Liste der nicht unterstützten Schnittstellen-IDs.

## <a name="remarks"></a>Hinweise

Implementiert die allgemeinen Merkmale einer Schnittstelle.

Die zweite Vorlage ist eine Spezialisierung für die verdeckten Schnittstellen. Die dritte Vorlage ist eine Spezialisierung für NULL-Parameter.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name   | Beschreibung
------ | ------------------------------------------
`Base` | Ein Synonym für den *I0* Template-Parameter.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                   | Beschreibung
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[InterfaceTraits::CanCastTo](#cancastto)               | Gibt an, ob der angegebene Zeiger umgewandelt werden kann, auf einen Zeiger auf `Base`.
[InterfaceTraits::CastToBase](#casttobase)             | Wandelt den angegebenen Zeiger auf einen Zeiger auf `Base`.
[InterfaceTraits::CastToUnknown](#casttounknown)       | Wandelt den angegebenen Zeiger auf einen Zeiger auf `IUnknown`.
[InterfaceTraits::FillArrayWithIid](#fillarraywithiid) | Weist die Schnittstellen-ID des `Base` auf das Arrayelement, das durch die Indexargument angegeben wird.
[InterfaceTraits::Verify](#verify)                     | Überprüft, ob `Base` ordnungsgemäß abgeleitet ist.

### <a name="public-constants"></a>Öffentliche Konstanten

Name                                   | Beschreibung
-------------------------------------- | ---------------------------------------------------------------------------------------
[InterfaceTraits::IidCount](#iidcount) | Enthält die Anzahl der Schnittstellen-IDs im Zusammenhang mit der aktuellen `InterfaceTraits` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InterfaceTraits`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="cancastto"></a>InterfaceTraits::CanCastTo

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Der Name eines Zeigers auf einen Typ.

*riid*<br/>
Die Schnittstellen-ID des `Base`.

*ppv*<br/>
Wenn dieser Vorgang erfolgreich ist, ist *Ppv* verweist auf die angegebene Schnittstelle `Base`. Andernfalls *Ppv* nastaven NA hodnotu `nullptr`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn dieser Vorgang erfolgreich ist und *Ptr* der Umwandlung in einen Zeiger auf `Base`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Gibt an, ob der angegebene Zeiger umgewandelt werden kann, auf einen Zeiger auf `Base`.

Weitere Informationen zu `Base`, finden Sie unter den [öffentliche Typedefs](#public-typedefs) Abschnitt.

## <a name="casttobase"></a>InterfaceTraits::CastToBase

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Parameters *Ptr*.

*ptr*<br/>
Zeiger auf einen Typ *T*.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf `Base`.

### <a name="remarks"></a>Hinweise

Wandelt den angegebenen Zeiger auf einen Zeiger auf `Base`.

Weitere Informationen zu `Base`, finden Sie unter den [öffentliche Typedefs](#public-typedefs) Abschnitt.

## <a name="casttounknown"></a>InterfaceTraits::CastToUnknown

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Parameters *Ptr*.

*ptr*<br/>
Zeiger auf den Typ *T*.

### <a name="return-value"></a>Rückgabewert

Zeiger auf IUnknown aus dem `Base` abgeleitet ist.

### <a name="remarks"></a>Hinweise

Wandelt den angegebenen Zeiger auf einen Zeiger auf `IUnknown`.

Weitere Informationen zu `Base`, finden Sie unter den [öffentliche Typedefs](#public-typedefs) Abschnitt.

## <a name="fillarraywithiid"></a>InterfaceTraits::FillArrayWithIid

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parameter

*index*<br/>
Zeiger auf ein Feld, das einen nullbasierter Indexwert enthält.

*iids*<br/>
Ein Array von Schnittstellen-IDs.

### <a name="remarks"></a>Hinweise

Weist die Schnittstellen-ID des `Base` auf das Arrayelement, das durch die Indexargument angegeben wird.

Im Gegensatz zu den Namen dieser API wird nur eine Array-Elements geändert. nicht das gesamte Array.

Weitere Informationen zu `Base`, finden Sie unter den [öffentliche Typedefs](#public-typedefs) Abschnitt.

## <a name="iidcount"></a>InterfaceTraits::IidCount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Hinweise

Enthält die Anzahl der Schnittstellen-IDs im Zusammenhang mit der aktuellen `InterfaceTraits` Objekt.

## <a name="verify"></a>InterfaceTraits::Verify

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Hinweise

Überprüft, ob `Base` ordnungsgemäß abgeleitet ist.

Weitere Informationen zu `Base`, finden Sie unter den [öffentliche Typedefs](#public-typedefs) Abschnitt.
