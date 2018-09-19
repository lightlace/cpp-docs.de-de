---
title: SafeNotEquals | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeNotEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeNotEquals function
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19427d24d61581d207101605a8456e8067ade929
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713842"
---
# <a name="safenotequals"></a>SafeNotEquals

Bestimmt, ob zwei Zahlen ungleich sind.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.

*u*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* und *u* nicht gleich sind; andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Die Methode verbessert `!=` da **SafeNotEquals** ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen zu vergleichen.

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ohne eine Instanz des für einen einzelnen Vergleich aus dient die [SafeInt-Klasse](../windows/safeint-class.md).

> [!NOTE]
> Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen.

Weitere Informationen zu den Vorlagentypen `T` und `U`, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Funktionen](../windows/safeint-functions.md)  
[SafeInt-Bibliothek](../windows/safeint-library.md)  
[SafeInt-Klasse](../windows/safeint-class.md)  
[SafeEquals](../windows/safeequals.md)