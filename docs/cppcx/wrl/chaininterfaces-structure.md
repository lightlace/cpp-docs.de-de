---
title: ChainInterfaces-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: 9fd315f017d3dcc9823054ea99e845ec99bc4192
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398744"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces-Struktur

Gibt Überprüfungs- und Initialisierungsfunktionen an, die auf einen Satz von Schnittstellen-IDs angewendet werden können.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>Parameter

*I0*<br/>
(Erforderlich) Schnittstellen-ID 0.

*I1*<br/>
(Erforderlich) Schnittstellen-ID 1.

*I2*<br/>
(Optional) Schnittstellen-ID 2.

*I3*<br/>
(Optional) Schnittstellen-ID 3.

*I4*<br/>
(Optional) Schnittstellen-ID 4.

*I5*<br/>
(Optional) Schnittstellen-ID 5.

*I6*<br/>
(Optional) Schnittstellen-ID 6.

*I7*<br/>
(Optional) Schnittstellen-ID 7.

*I8*<br/>
(Optional) Schnittstellen-ID 8.

*I9*<br/>
(Optional) Schnittstellen-ID-9.

*DerivedType*<br/>
Ein abgeleiteter Typ.

*BaseType*<br/>
Der Basistyp eines abgeleiteten Typs.

*hasImplements*<br/>
Ein boolescher Wert, auch wenn **"true"**, bedeutet, dass Sie nicht verwenden eine [MixIn](mixin-structure.md) Struktur mit einer Klasse, die nicht von abgeleitet ist die [implementiert](implements-structure.md) abgeschrägten Designs.

## <a name="members"></a>Member

### <a name="protected-methods"></a>Geschützte Methoden

Name                                                   | Beschreibung
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ChainInterfaces::CanCastTo](#cancastto)               | Gibt an, ob die angegebene Schnittstellen-ID in jede der von definiert spezialisierungen umgewandelt werden kann die `ChainInterface` Vorlagenparameter.
[ChainInterfaces::CastToUnknown](#casttounknown)       | Wandelt den Schnittstellenzeiger, der den vom definierten Typ der *I0* Template-Parameter auf einen Zeiger auf `IUnknown`.
[ChainInterfaces::FillArrayWithIid](#fillarraywithiid) | Speichert die Schnittstellen-ID, durch definiert die *I0* Template-Parameter in einer angegebenen Position in einem angegebenen Array von Schnittstellen-IDs.
[ChainInterfaces::Verify](#verify)                     | Stellt sicher, dass jede Schnittstelle Vorlagenparameter definiert *I0* über *I9* erbt `IUnknown` und/oder `IInspectable`, und dass *I0* erbt von *I1* über *I9*.

### <a name="protected-constants"></a>Geschützte Konstanten

Name                                   | Beschreibung
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ChainInterfaces::IidCount](#iidcount) | Die Gesamtanzahl der Schnittstellen-IDs enthalten, die in den Schnittstellen, die vom Vorlagenparameter angegeben *I0* über *I9*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="cancastto"></a>ChainInterfaces::CanCastTo

Gibt an, ob die angegebene Schnittstellen-ID in jede der durch die nicht dem Standard-Vorlagenparameter definiert spezialisierungen umgewandelt werden kann.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*ppv*<br/>
Ein Zeiger auf die letzte Schnittstellen-ID, die erfolgreich umgewandelt wurde.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn alle Umwandlungsvorgänge erfolgreich war; andernfalls **"false"**.

## <a name="casttounknown"></a>ChainInterfaces::CastToUnknown

Wandelt den Schnittstellenzeiger, der den vom definierten Typ der *I0* Template-Parameter auf einen Zeiger auf `IUnknown`.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf `IUnknown`.

## <a name="fillarraywithiid"></a>ChainInterfaces::FillArrayWithIid

Speichert die Schnittstellen-ID, durch definiert die *I0* Template-Parameter in einer angegebenen Position in einem angegebenen Array von Schnittstellen-IDs.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parameter

*index*<br/>
Zeiger auf einen Indexwert in der *Iids* Array.

*iids*<br/>
Ein Array von Schnittstellen-IDs.

## <a name="iidcount"></a>ChainInterfaces::IidCount

Die Gesamtanzahl der Schnittstellen-IDs enthalten, die in den Schnittstellen, die vom Vorlagenparameter angegeben *I0* über *I9*.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Rückgabewert

Die Gesamtanzahl der Schnittstellen-IDs.

### <a name="remarks"></a>Hinweise

Vorlagenparameter *I0* und *I1* sind erforderlich, und die Parameter *I2* über *I9* sind optional. Die Anzahl der IID jeder Schnittstelle ist in der Regel 1.

## <a name="verify"></a>ChainInterfaces::Verify

Stellt sicher, dass jede Schnittstelle Vorlagenparameter definiert *I0* über *I9* erbt `IUnknown` und/oder `IInspectable`, und dass *I0* erbt von *I1* über *I9*.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Hinweise

Wenn der Überprüfungsvorgang fehlschlägt, eine `static_assert` gibt eine Fehlermeldung, die den Fehler beschreibt.

Vorlagenparameter *I0* und *I1* sind erforderlich, und die Parameter *I2* über *I9* sind optional.
