---
title: Microsoft::WRL::Wrappers::HandleTraits-Namespace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 6ed8156b6a0e71d40d1579fc9a33912f698e1773
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391971"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits-Namespace

Beschreibt die Eigenschaften der verwendeten Ressourcentypen von Handles basierende.

## <a name="syntax"></a>Syntax

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Member

### <a name="structures"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|[CriticalSectionTraits-Struktur](criticalsectiontraits-structure.md)|Spezialisiert hat eine `CriticalSection` Objekt, das entweder ein ungültiges kritischen Abschnitt oder eine Funktion, die einen kritischen Abschnitt release unterstützt.|
|[EventTraits-Struktur](eventtraits-structure.md)|Definiert die Merkmale einer `Event` Klassenhandle.|
|[FileHandleTraits-Struktur](filehandletraits-structure.md)|Definiert die Merkmale eines Dateihandles.|
|[HANDLENullTraits-Struktur](handlenulltraits-structure.md)|Definiert die allgemeinen Merkmale eines nicht initialisierten Handles.|
|[HANDLETraits-Struktur](handletraits-structure.md)|Definiert die allgemeinen Merkmale eines Handles.|
|[MutexTraits-Struktur](mutextraits-structure.md)|Definiert die allgemeinen Merkmale der [Mutex](mutex-class.md) Klasse.|
|[SemaphoreTraits-Struktur](semaphoretraits-structure.md)|Definiert die allgemeinen Merkmale einer Semaphorobjekt.|
|[SRWLockExclusiveTraits-Struktur](srwlockexclusivetraits-structure.md)|Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse im Sperrmodus für exklusive.|
|[SRWLockSharedTraits-Struktur](srwlocksharedtraits-structure.md)|Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse in freigegebene sperren.|

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers-Namespace](microsoft-wrl-wrappers-namespace.md)