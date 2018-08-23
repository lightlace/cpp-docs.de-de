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
ms.openlocfilehash: ee7edbee285df6da752e875ac4d86a74e8f7893d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594140"
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

*LHS*  
Der erste Parameter, verglichen werden soll. *LHS* möglich ein Verweis auf ein **HStringReference**.

*RS*  
Der zweite Parameter, verglichen werden soll.  *RS* möglich ein Verweis auf ein **HStringReference**.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* -Parameter ist kleiner als der *RS* Parameter ist, andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HStringReference-Klasse](../windows/hstringreference-class.md)