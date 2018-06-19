---
title: 'Hstring:: Operator ==-Operator | Microsoft Docs'
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
ms.openlocfilehash: 5386636a348fdf7162e9b6d63f0e6dbc109bd655
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876539"
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
  
#### <a name="parameters"></a>Parameter  
 `lhs`  
 Der erste Parameter, verglichen werden soll. `lhs` kann ein HString oder HStringReference-Objekt oder ein HSTRING-Handle.  
  
 `rhs`  
 Der zweite Parameter, verglichen werden soll.`rhs` kann ein HString oder HStringReference-Objekt oder ein HSTRING-Handle.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn die `lhs` und `rhs` Parameter gleich sind; andernfalls, `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)