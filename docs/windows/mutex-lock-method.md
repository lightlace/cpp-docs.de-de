---
title: 'Mutex:: Lock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38bd11620f8d403bbd1667ab6fa4f3f827362c88
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600872"
---
# <a name="mutexlock-method"></a>Mutex::Lock-Methode

Wartet, bis das aktuelle Objekt, oder die **Mutex** Objekt verknüpft, die mit dem angegebenen Handle, Versionen, die den Mutex oder das angegebene Timeoutintervall verstrichen ist.

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
Das Handle für ein **Mutex** Objekt.

## <a name="return-value"></a>Rückgabewert

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch
[Mutex-Klasse](../windows/mutex-class1.md)