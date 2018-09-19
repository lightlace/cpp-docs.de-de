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
ms.openlocfilehash: 382dbdd2d0816d6ab0846acd0f8c164cd542114f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575840"
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

*cs*  
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