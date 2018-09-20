---
title: Hstringreference::&lt; Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17acdca8af1250b1f88fa8a6858ffa1854f8ca8c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426405"
---
# <a name="hstringreferenceoperatorlt-operator"></a>Hstringreference::&lt; Operator

Gibt an, ob der erste Parameter kleiner als der zweite Parameter.

## <a name="syntax"></a>Syntax

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()  
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Der erste Parameter, verglichen werden soll. *LHS* möglich ein Verweis auf ein **HStringReference**.

*RS*<br/>
Der zweite Parameter, verglichen werden soll.  *RS* möglich ein Verweis auf ein **HStringReference**.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* -Parameter ist kleiner als der *RS* Parameter ist, andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HStringReference-Klasse](../windows/hstringreference-class.md)