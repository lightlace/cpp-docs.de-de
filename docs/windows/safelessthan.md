---
title: SafeLessThan | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThan
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThan function
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a5824b1e3ba050cf8c6d9c0f7b56231211f1f59a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377193"
---
# <a name="safelessthan"></a>SafeLessThan

Bestimmt, ob eine Zahl kleiner als ein anderes ist.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste Zahl. Dies muss vom Typ `T`.

*u*<br/>
[in] Die zweite Anzahl. Dies muss vom Typ `U`.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* ist kleiner als *u*andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Diese Methode wird den standard-Vergleichsoperator verbessert, da **SafeLessThan** ermöglicht es Ihnen, zwei verschiedene Arten von Zahl verglichen werden soll.

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ohne eine Instanz des für einen einzelnen Vergleich aus dient die [SafeInt-Klasse](../windows/safeint-class.md).

> [!NOTE]
> Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` -Klasse anstelle der einzelnen eigenständigen Funktionen aufrufen.

Weitere Informationen zu den Vorlagentypen `T` und `U`, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Funktionen](../windows/safeint-functions.md)<br/>
[SafeInt-Bibliothek](../windows/safeint-library.md)<br/>
[SafeInt-Klasse](../windows/safeint-class.md)<br/>
[SafeLessThanEquals](../windows/safelessthanequals.md)<br/>
[SafeGreaterThan](../windows/safegreaterthan.md)<br/>
[SafeGreaterThanEquals](../windows/safegreaterthanequals.md)