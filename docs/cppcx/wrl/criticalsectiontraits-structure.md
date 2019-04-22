---
title: CriticalSectionTraits-Struktur
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: ce904ecbd9a5855c63fd43f07f88c215cef544ae
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785378"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits-Struktur

Spezialisiert hat eine `CriticalSection` Objekt, das entweder ein ungültiges kritischen Abschnitt oder eine Funktion, die einen kritischen Abschnitt release unterstützt.

## <a name="syntax"></a>Syntax

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name   | Beschreibung
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | Ein `typedef` , die einen Zeiger auf einen kritischen Abschnitt definiert. `Type` wird definiert als `typedef CRITICAL_SECTION* Type;`.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                       | Beschreibung
---------------------------------------------------------- | -----------------
[CriticalSectionTraits::GetInvalidValue](#getinvalidvalue) | Spezialisiert hat eine `CriticalSection` Vorlage so, dass die Vorlage immer ungültig ist.
[CriticalSectionTraits::Unlock](#unlock)                   | Spezialisiert hat eine `CriticalSection` Vorlage so, dass die It freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CriticalSectionTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>CriticalSectionTraits::GetInvalidValue

Spezialisiert hat eine `CriticalSection` Vorlage so, dass die Vorlage immer ungültig ist.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer einen Zeiger auf einen ungültigen kritischen Abschnitt zurück.

### <a name="remarks"></a>Hinweise

Die `Type` Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.

## <a name="unlock"></a>CriticalSectionTraits::Unlock

Spezialisiert hat eine `CriticalSection` Vorlage so, dass die It freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Parameter

*cs*<br/>
Ein Zeiger auf ein Objekt des kritischen Abschnitts.

### <a name="remarks"></a>Hinweise

Die `Type` Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.

Weitere Informationen finden Sie unter **Funktion LeaveCriticalSection** in die **Synchronisierungsfunktionen** Teil der Windows-API-Dokumentation.
