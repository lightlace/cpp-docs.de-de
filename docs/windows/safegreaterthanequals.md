---
title: SafeGreaterThanEquals | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeGreaterThanEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeGreaterThanEquals function
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4bafae070d3ff9fe80070e3598cd36867abcf830
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707199"
---
# <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

Vergleicht zwei Zahlen.

## <a name="syntax"></a>Syntax

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
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

**"true"** Wenn *t* ist größer als oder gleich *u*andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

**SafeGreaterThanEquals** standard Vergleichsoperator verbessert, da Sie zwei verschiedene Arten von Zahlen vergleichen können.

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
[SafeGreaterThan](../windows/safegreaterthan.md)  
[SafeLessThanEquals](../windows/safelessthanequals.md)  
[SafeLessThan](../windows/safelessthan.md)