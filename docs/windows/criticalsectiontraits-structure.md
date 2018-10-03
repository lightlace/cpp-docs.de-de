---
title: CriticalSectionTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/26/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 420ab1019dfa2e95e00e366c64509178ad20e685
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234338"
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
[Criticalsectiontraits:: Getinvalidvalue](#getinvalidvalue) | Spezialisiert hat eine `CriticalSection` Vorlage so, dass die Vorlage immer ungültig ist.
[Criticalsectiontraits:: Unlock](#unlock)                   | Spezialisiert hat eine `CriticalSection` Vorlage so, dass die It freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CriticalSectionTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Criticalsectiontraits:: Getinvalidvalue

Spezialisiert hat eine `CriticalSection` Vorlage so, dass die Vorlage immer ungültig ist.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer einen Zeiger auf einen ungültigen kritischen Abschnitt zurück.

### <a name="remarks"></a>Hinweise

Die `Type` Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.

## <a name="unlock"></a>Criticalsectiontraits:: Unlock

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
