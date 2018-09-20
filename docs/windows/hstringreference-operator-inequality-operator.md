---
title: Hstringreference::! =-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
dev_langs:
- C++
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 996ead81a72fb3cc58544576059a8347972e2a6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429056"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator!=-Operator

Gibt an, ob die zwei Parameter ungleich sind.

## <a name="syntax"></a>Syntax

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Der erste Parameter, verglichen werden soll. *LHS* kann ein **HStringReference** Objekt oder ein HSTRING-Handle.

*RS*<br/>
Der zweite Parameter, verglichen werden soll.  *RS* kann ein **HStringReference** Objekt oder ein HSTRING-Handle.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* und *RS* Parameter sind nicht gleich sind, andernfalls **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HStringReference-Klasse](../windows/hstringreference-class.md)