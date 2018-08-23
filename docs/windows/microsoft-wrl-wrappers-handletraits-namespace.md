---
title: Microsoft::wrl::Wrappers::HandleTraits-Namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 683759c3bf0b2152ee6fadbb638cd2398daecccd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586128"
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
|[CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)|Spezialisiert hat eine `CriticalSection` Objekt, das entweder ein ungültiges kritischen Abschnitt oder eine Funktion, die einen kritischen Abschnitt release unterstützt.|
|[EventTraits-Struktur](../windows/eventtraits-structure.md)|Definiert die Merkmale einer `Event` Klassenhandle.|
|[FileHandleTraits-Struktur](../windows/filehandletraits-structure.md)|Definiert die Merkmale eines Dateihandles.|
|[HANDLENullTraits-Struktur](../windows/handlenulltraits-structure.md)|Definiert die allgemeinen Merkmale eines nicht initialisierten Handles.|
|[HANDLETraits-Struktur](../windows/handletraits-structure.md)|Definiert die allgemeinen Merkmale eines Handles.|
|[MutexTraits-Struktur](../windows/mutextraits-structure.md)|Definiert die allgemeinen Merkmale der [Mutex](../windows/mutex-class1.md) Klasse.|
|[SemaphoreTraits-Struktur](../windows/semaphoretraits-structure.md)|Definiert die allgemeinen Merkmale einer Semaphorobjekt.|
|[SRWLockExclusiveTraits-Struktur](../windows/srwlockexclusivetraits-structure.md)|Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse im Sperrmodus für exklusive.|
|[SRWLockSharedTraits-Struktur](../windows/srwlocksharedtraits-structure.md)|Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse in freigegebene sperren.|

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)