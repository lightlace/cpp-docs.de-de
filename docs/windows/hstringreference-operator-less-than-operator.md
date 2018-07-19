---
title: Hstringreference::&lt; Operator | Microsoft Docs
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
ms.openlocfilehash: 5b486157fb42883af724f2356e7f85701e405035
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877292"
---
# <a name="hstringreferenceoperatorlt-operator"></a>Hstringreference::&lt; Operator
Gibt an, ob der erste Parameter ist kleiner als der zweite Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
#### <a name="parameters"></a>Parameter  
 `lhs`  
 Der erste Parameter, verglichen werden soll. `lhs` Ein Verweis auf ein HStringReference kann sein.  
  
 `rhs`  
 Der zweite Parameter, verglichen werden soll.  `rhs` Ein Verweis auf ein HStringReference kann sein.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn die `lhs` Parameter ist kleiner als das `rhs` Parameter ist, andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)