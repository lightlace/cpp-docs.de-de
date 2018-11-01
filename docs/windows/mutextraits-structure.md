---
title: MutexTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 15ed7d9dc3a1b97e05712e003fa61f662901fc18
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234987"
---
# <a name="mutextraits-structure"></a>MutexTraits-Struktur

Definiert die allgemeinen Merkmale der [Mutex](../windows/mutex-class1.md) Klasse.

## <a name="syntax"></a>Syntax

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                           | Beschreibung
------------------------------ | ------------------------------------------------
[Mutextraits:: Unlock](#unlock) | Gibt die exklusive Kontrolle über eine freigegebene Ressource frei.

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
