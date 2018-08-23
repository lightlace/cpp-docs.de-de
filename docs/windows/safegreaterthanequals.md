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
ms.openlocfilehash: bf94c53bd0491d5959a53591b77305d19f21bc36
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612345"
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

[in] *t*  
Die erste zu vergleichende Zahl. Dies muss vom Typ `T`.

[in] *u*  
Die zweite zu vergleichende Zahl. Dies muss vom Typ `U`.

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