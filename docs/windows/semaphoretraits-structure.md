---
title: SemaphoreTraits-Struktur
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: e7bd2e5d0993c8e4be7223d98ffb1dbec14cbb74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502943"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits-Struktur

Definiert die allgemeinen Merkmale einer `Semaphore` Objekt.

## <a name="syntax"></a>Syntax

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                               | Beschreibung
---------------------------------- | --------------------------------------
[Semaphoretraits:: Unlock](#unlock) | Releases-Steuerelement eine gemeinsam genutzte Ressource.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>Semaphoretraits:: Unlock

Releases-Steuerelement eine gemeinsam genutzte Ressource.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Handle für ein `Semaphore` Objekt.

### <a name="remarks"></a>Hinweise

Wenn sich "Entsperren"-Vorgangs nicht erfolgreich ist `Unlock()` gibt einen Fehler, der die Ursache des Fehlers angibt.
