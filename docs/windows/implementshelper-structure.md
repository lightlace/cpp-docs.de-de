---
title: ImplementsHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 574d0dbf6a252f65dd6c15681a243ce0e4086f0e
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788499"
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
Ein Feld von Flags, der angibt, eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.

*ILst*<br/>
Eine Liste der Schnittstellen-IDs.

*IsDelegateToClass*<br/>
Geben Sie `true` Wenn die aktuelle Instanz von `Implements` ist eine Basisklasse, der die erste Schnittstellen-ID in *ILst*ist, andernfalls `false`.

## <a name="remarks"></a>Hinweise

Hilft, implementieren die [implementiert](../windows/implements-structure.md) Struktur.

Diese Vorlage durchläuft eine Liste von Schnittstellen und fügt sie hinzu, als Basisklassen, sowie Informationen zum Aktivieren von erforderlich `QueryInterface`.

## <a name="members"></a>Member

### <a name="protected-methods"></a>Geschützte Methoden

Name                                                    | Beschreibung
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[Implementshelper:: Cancastto](#cancastto)               | Ruft einen Zeiger auf die angegebene Schnittstellen-ID.
[Implementshelper:: Casttounknown](#casttounknown)       | Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle für den aktuellen `Implements` Struktur.
[Implementshelper:: Fillarraywithiid](#fillarraywithiid) | Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.
[Implementshelper:: Iidcount](#iidcount)                 | Enthält die Anzahl der implementierten Schnittstellen-IDs in der aktuellen `Implements` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ImplementsHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="cancastto"></a>Implementshelper:: Cancastto

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

*IID*<br/>
Verweis auf eine Schnittstellen-ID.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die angegebene Schnittstellen-ID.

## <a name="casttounknown"></a>Implementshelper:: Casttounknown

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.

### <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle für den aktuellen `Implements` Struktur.

## <a name="fillarraywithiid"></a>Implementshelper:: Fillarraywithiid

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Parameter

*index*<br/>
Ein nullbasierter Index, der das Startelement "Array" für diesen Vorgang angibt. Klicken Sie nach Abschluss dieses Vorgangs *Index* um 1 erhöht.

*IIDs*<br/>
Ein Array vom Typ IIDs werden soll.

### <a name="remarks"></a>Hinweise

Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.

## <a name="iidcount"></a>Implementshelper:: Iidcount

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Hinweise

Enthält die Anzahl der implementierten Schnittstellen-IDs in der aktuellen `Implements` Objekt.
