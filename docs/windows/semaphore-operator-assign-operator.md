---
title: 'Semaphore:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b35268cd883245b125aa7c87919124b29451ff1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420321"
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator=-Operator

Verschiebt das angegebene Handle von einem **Semaphor** -Objekt mit dem aktuellen **Semaphor** Objekt.

## <a name="syntax"></a>Syntax

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Rvalue-Verweis auf eine **Semaphor** Objekt.

## <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle **Semaphor** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Semaphore-Klasse](../windows/semaphore-class.md)