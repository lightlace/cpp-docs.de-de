---
title: 'SRWLOCK:: Trylockshared-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 985629f224f199d1b1f095847e64cc67fa5a97f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388463"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared-Methode

Versucht, für eine **SRWLock** Objekt im freigegebenen Modus für den aktuellen oder angegebenen **SRWLock** Objekt.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein **SRWLock** Objekt.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung einen **SRWLock** Objekt im Modus für gemeinsame Nutzung und der aufrufende Thread übernimmt den Besitz der Sperre. Andernfalls ein **SRWLock** Objekt, dessen Status ungültig ist.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[SRWLock-Klasse](../windows/srwlock-class.md)