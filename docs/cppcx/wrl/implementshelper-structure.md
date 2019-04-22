---
title: ImplementsHelper-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: 250a59152e9b41eb48c453caaa696fdc8ca3d3b4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785655"
---
# <a name="implementshelper-structure"></a>ImplementsHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Parameter

*RuntimeClassFlagsT*<br/>
Ein Feld von Flags, der angibt, eine oder mehrere [RuntimeClassType](runtimeclasstype-enumeration.md) Enumeratoren.

*ILst*<br/>
Eine Liste der Schnittstellen-IDs.

*IsDelegateToClass*<br/>
Geben Sie **"true"** Wenn die aktuelle Instanz von `Implements` ist eine Basisklasse, der die erste Schnittstellen-ID in *ILst*ist, andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Hilft, implementieren die [implementiert](implements-structure.md) Struktur.

Diese Vorlage durchläuft eine Liste von Schnittstellen und fügt sie hinzu, als Basisklassen, sowie Informationen zum Aktivieren von erforderlich `QueryInterface`.

## <a name="members"></a>Member

### <a name="protected-methods"></a>Geschützte Methoden

Name                                                    | Beschreibung
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[ImplementsHelper::CanCastTo](#cancastto)               | Ruft einen Zeiger auf die angegebene Schnittstellen-ID.
[ImplementsHelper::CastToUnknown](#casttounknown)       | Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle für den aktuellen `Implements` Struktur.
[ImplementsHelper::FillArrayWithIid](#fillarraywithiid) | Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.
[ImplementsHelper::IidCount](#iidcount)                 | Enthält die Anzahl der implementierten Schnittstellen-IDs in der aktuellen `Implements` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ImplementsHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="cancastto"></a>ImplementsHelper::CanCastTo

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Verweis auf eine Schnittstellen-ID.

*ppv*<br/>
Wenn dieser Vorgang erfolgreich ist, ein Zeiger auf die Schnittstelle angegeben *Riid* oder *Iid*.

*iid*<br/>
Verweis auf eine Schnittstellen-ID.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die angegebene Schnittstellen-ID.

## <a name="casttounknown"></a>ImplementsHelper::CastToUnknown

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.

### <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle für den aktuellen `Implements` Struktur.

## <a name="fillarraywithiid"></a>ImplementsHelper::FillArrayWithIid

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Parameter

*index*<br/>
Ein nullbasierter Index, der das Startelement "Array" für diesen Vorgang angibt. Klicken Sie nach Abschluss dieses Vorgangs *Index* um 1 erhöht.

*iids*<br/>
Ein Array vom Typ IIDs werden soll.

### <a name="remarks"></a>Hinweise

Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.

## <a name="iidcount"></a>ImplementsHelper::IidCount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Hinweise

Enthält die Anzahl der implementierten Schnittstellen-IDs in der aktuellen `Implements` Objekt.
