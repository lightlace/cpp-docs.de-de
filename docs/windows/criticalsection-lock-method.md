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
ms.openlocfilehash: f13af220107ba8d5bc5c26c65c2034f125a39454
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382452"
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

*cs*<br/>
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