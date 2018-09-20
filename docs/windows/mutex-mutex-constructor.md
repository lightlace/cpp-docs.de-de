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
ms.openlocfilehash: b7436aeb470804bd47dcc647ff0fe9a13faaae95
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444280"
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

*h*<br/>
Ein Handle oder einen Rvalue-Verweis auf ein Handle, um eine **Mutex** Objekt.

## <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein **Mutex** Objekt aus dem angegebenen Handle. Der zweite Konstruktor initialisiert ein **Mutex** -Objekt aus dem angegebenen Handle, und klicken Sie dann wechselt der Besitz des Mutex, mit dem aktuellen **Mutex** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Mutex-Klasse](../windows/mutex-class1.md)