---
title: 'CriticalSection:: Lock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4fedde29441c9c14b68dec5cff998be57d216e29
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607659"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock-Methode

Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitt. Gibt die Funktion zurück, wenn der aufrufende Thread den Besitz gewährt wird.

## <a name="syntax"></a>Syntax

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parameter

*cs*  
Ein Kritischer Abschnitt Benutzer angegebene-Objekt.

## <a name="return-value"></a>Rückgabewert

Eine Sperrobjekt, das verwendet werden kann, um den aktuellen kritischen Abschnitt zu entsperren.

## <a name="remarks"></a>Hinweise

Die erste **Sperre** Funktion wirkt sich auf das aktuelle Objekt des kritischen Abschnitts. Die zweite **Sperre** Funktion wirkt sich auf einen vom Benutzer angegebenen kritischen Abschnitt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[CriticalSection-Klasse](../windows/criticalsection-class.md)