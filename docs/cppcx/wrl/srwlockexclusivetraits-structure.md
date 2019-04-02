---
title: SRWLockExclusiveTraits-Struktur
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: 25249b8823b8c182133e85aa4cd07d38f5874cf2
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784247"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits-Struktur

Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse im Sperrmodus für exklusive.

## <a name="syntax"></a>Syntax

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name   | Beschreibung
------ | --------------------------------------------------------------------------
`Type` | Synonym für einen Zeiger auf die [SRWLOCK](srwlock-class.md) Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                        | Beschreibung
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits::GetInvalidValue](#getinvalidvalue) | Ruft eine `SRWLockExclusiveTraits` -Objekt, das immer ungültig ist.
[SRWLockExclusiveTraits::Unlock](#unlock)                   | Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>SRWLockExclusiveTraits::GetInvalidValue

Ruft eine `SRWLockExclusiveTraits` -Objekt, das immer ungültig ist.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Ein leeres `SRWLockExclusiveTraits`-Objekt.

## <a name="unlock"></a>SRWLockExclusiveTraits::Unlock

Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parameter

*srwlock*<br/>
Handle für ein `SRWLock` Objekt.
