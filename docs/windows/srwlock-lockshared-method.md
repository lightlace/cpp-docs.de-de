---
title: 'SRWLOCK:: Lockshared-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
dev_langs:
- C++
helpviewer_keywords:
- LockShared method
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f6b3135171e61e928984c0eeb91aff0717a4727
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599248"
---
# <a name="srwlocklockshared-method"></a>SRWLock::LockShared-Methode

Ruft eine **SRWLock** Objekt im freigegebenen Modus.

## <a name="syntax"></a>Syntax

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*  
Zeiger auf ein **SRWLock** Objekt.

## <a name="return-value"></a>Rückgabewert

Ein **SRWLock** Objekt im freigegebenen Modus.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[SRWLock-Klasse](../windows/srwlock-class.md)