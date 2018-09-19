---
title: 'SafeIntException:: SafeIntException | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24138db5ab772990f050fc8fcb6e5dad640a662d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396778"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException

Erstellt eine **SafeIntException** Objekt.

## <a name="syntax"></a>Syntax

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parameter

*Code*<br/>
[in] Ein Aufzählungsdaten-Wert, der den Fehler beschreibt, der aufgetreten sind.

## <a name="remarks"></a>Hinweise

Die möglichen Werte für *Code* werden in der Datei Safeint.h definiert. Der Einfachheit halber sind die möglichen Werte auch hier aufgeführt.

- `SafeIntNoError`

- `SafeIntArithmeticOverflow`

- `SafeIntDivideByZero`

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** MSL:: Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Bibliothek](../windows/safeint-library.md)<br/>
[SafeIntException-Klasse](../windows/safeintexception-class.md)<br/>
[SafeInt-Klasse](../windows/safeint-class.md)