---
title: Hstring::&lt; Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0a89054dd7ce105f059083f3bd5ebb8db685396f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591941"
---
# <a name="hstringoperatorlt-operator"></a>Hstring::&lt; Operator

Gibt an, ob der erste Parameter kleiner als der zweite Parameter.

## <a name="syntax"></a>Syntax

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()  
```

### <a name="parameters"></a>Parameter

*LHS*  
Der erste Parameter, verglichen werden soll. *LHS* möglich ein Verweis auf ein **HString**.

*RS*  
Der zweite Parameter, verglichen werden soll. *RS* möglich ein Verweis auf ein **HString**.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* -Parameter ist kleiner als der *RS* Parameter ist, andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)