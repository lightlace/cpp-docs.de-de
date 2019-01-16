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
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337341"
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
[SemaphoreTraits::Unlock](#unlock) | Releases-Steuerelement eine gemeinsam genutzte Ressource.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>SemaphoreTraits::Unlock

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
