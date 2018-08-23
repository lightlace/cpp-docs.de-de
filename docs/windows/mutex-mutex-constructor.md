---
title: 'Mutex:: Mutex-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62a1fc796188c38dfbd3aff004eba15b7e30ea89
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600504"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex-Konstruktor

Initialisiert eine neue Instanz der dem **Mutex** Klasse.

## <a name="syntax"></a>Syntax

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parameter

*h*  
Ein Handle oder einen Rvalue-Verweis auf ein Handle, um eine **Mutex** Objekt.

## <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein **Mutex** Objekt aus dem angegebenen Handle. Der zweite Konstruktor initialisiert ein **Mutex** -Objekt aus dem angegebenen Handle, und klicken Sie dann wechselt der Besitz des Mutex, mit dem aktuellen **Mutex** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch
[Mutex-Klasse](../windows/mutex-class1.md)