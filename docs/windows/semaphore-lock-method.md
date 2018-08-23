---
title: 'Semaphore:: Lock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 47925bcc647d253775e4dd61f6a7f5d5fb586dde
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599282"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock-Methode

Wartet, bis das aktuelle Objekt, oder die **Semaphor** zugeordnete Objekt das angegebene Handle im signalisierten Zustand ist, oder das angegebene Timeoutintervall verstrichen.

## <a name="syntax"></a>Syntax

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Parameter

*Millisekunden*  
Das Timeoutintervall in Millisekunden. Der Standardwert ist UNENDLICH sein, was die unbegrenzt wartet.

*h*  
Ein Handle für ein **Semaphor** Objekt.

## <a name="return-value"></a>Rückgabewert

Eine `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Semaphore-Klasse](../windows/semaphore-class.md)