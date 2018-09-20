---
title: 'Mutex:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea5aee6f248487097462028a763a98b4e814a17a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396791"
---
# <a name="mutexoperator-operator"></a>Mutex::operator=-Operator

Zugewiesen (bewegt) der angegebenen **Mutex** -Objekt mit dem aktuellen **Mutex** Objekt.

## <a name="syntax"></a>Syntax

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Rvalue-Verweis auf eine **Mutex** Objekt.

## <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle **Mutex** Objekt.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den **verschieben Semantik** Abschnitt [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[Mutex-Klasse](../windows/mutex-class1.md)