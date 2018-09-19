---
title: 'CriticalSection:: TryLock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44b4e251898ef6386d0642582af2c00881f7a181
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408582"
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock-Methode

Versucht, einen kritischen Abschnitt ohne Blockierung zu geben. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den kritischen Abschnitt.

## <a name="syntax"></a>Syntax

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parameter

*cs*<br/>
Ein Kritischer Abschnitt Benutzer angegebene-Objekt.

## <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL, wenn der kritische Abschnitt erfolgreich eingegeben wird oder der aktuelle Thread besitzt bereits den kritischen Abschnitt. NULL, wenn ein anderer Thread den kritischen Abschnitt bereits im Besitz.

## <a name="remarks"></a>Hinweise

Die erste **TryLock** Funktion wirkt sich auf das aktuelle Objekt des kritischen Abschnitts. Die zweite **TryLock** Funktion wirkt sich auf einen vom Benutzer angegebenen kritischen Abschnitt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[CriticalSection-Klasse](../windows/criticalsection-class.md)