---
title: SRWLockSharedTraits-Struktur
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: af567fd333854519df4543ad24084e52cda4d96e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383281"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits-Struktur

Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse in freigegebene sperren.

## <a name="syntax"></a>Syntax

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name   | Beschreibung
------ | --------------------------------------------------------------------------
`Type` | Synonym für einen Zeiger auf die [SRWLOCK](srwlock-class.md) Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                     | Beschreibung
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits::GetInvalidValue](#getinvalidvalue) | Ruft eine `SRWLockSharedTraits` -Objekt, das immer ungültig ist.
[SRWLockSharedTraits::Unlock](#unlock)                   | Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SRWLockSharedTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>SRWLockSharedTraits::GetInvalidValue

Ruft eine `SRWLockSharedTraits` -Objekt, das immer ungültig ist.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein `SRWLockSharedTraits` Objekt.

## <a name="unlock"></a>SRWLockSharedTraits::Unlock

Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parameter

*srwlock*<br/>
Ein Handle für ein `SRWLock` Objekt.
