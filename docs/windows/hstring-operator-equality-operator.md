---
title: 'Hstring:: Operator ==-Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs:
- C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dee6fd7b50d116264ea6b8b9a6b7bac3936e95cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413717"
---
# <a name="hstringoperator-operator"></a>HString::Operator==-Operator

Gibt an, ob die zwei Parameter gleich sind.

## <a name="syntax"></a>Syntax

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Der erste Parameter, verglichen werden soll. *LHS* kann ein **HString** oder `HStringReference` Objekt oder ein HSTRING-Handle.

*RS*<br/>
Der zweite Parameter, verglichen werden soll. *RS* kann ein **HString** oder `HStringReference` Objekt oder ein HSTRING-Handle.

## <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* und *RS* Parameter gleich sind; andernfalls, **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)