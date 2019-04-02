---
title: MutexTraits-Struktur
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: 9bc4071e5699610a664cbf01ca3e7d36d7effc5e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785066"
---
# <a name="mutextraits-structure"></a>MutexTraits-Struktur

Definiert die allgemeinen Merkmale der [Mutex](mutex-class.md) Klasse.

## <a name="syntax"></a>Syntax

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                           | Beschreibung
------------------------------ | ------------------------------------------------
[MutexTraits::Unlock](#unlock) | Gibt die exklusive Kontrolle über eine freigegebene Ressource frei.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>Mutextraits:: Unlock-Methode

Gibt die exklusive Kontrolle über eine freigegebene Ressource frei.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Handle für ein Mutex-Objekt.
