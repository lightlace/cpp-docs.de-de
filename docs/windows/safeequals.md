---
title: SafeEquals | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeEquals function
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81f30386946c7fd187f1044804b9f1737a94c58f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718646"
---
# <a name="safeequals"></a>SafeEquals

Vergleicht zwei Zahlen, um festzustellen, ob diese gleich sind.

## <a name="syntax"></a>Syntax

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parameter

*t*<br/>
[in] Die erste zu vergleichende Zahl. Dies muss vom Typ "t".

*u*<br/>
[in] Die zweite zu vergleichende Zahl. Dies muss u sein.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn *t* und *u* gleich sind; andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Die Methode verbessert `==` da **SafeEquals** ermöglicht es Ihnen, zwei verschiedene Arten von Zahlen zu vergleichen.

Diese Methode ist Teil des [SafeInt-Bibliothek](../windows/safeint-library.md) und ohne eine Instanz des für einen einzelnen Vergleich aus dient die [SafeInt-Klasse](../windows/safeint-class.md).

> [!NOTE]
> Diese Methode sollte nur verwendet werden, wenn eine einzelne mathematische Operation, die geschützt werden muss. Wenn mehrere Vorgänge vorhanden sind, sollten Sie verwenden die `SafeInt` Klasse anstelle von den einzelnen eigenständigen Funktionen.

Weitere Informationen zu den Vorlagentypen T "und" U, finden Sie unter [SafeInt-Funktionen](../windows/safeint-functions.md).

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Funktionen](../windows/safeint-functions.md)  
[SafeInt-Bibliothek](../windows/safeint-library.md)  
[SafeInt-Klasse](../windows/safeint-class.md)  
[SafeNotEquals](../windows/safenotequals.md)