---
title: 'Hstringreference:: Operator ==-Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs:
- C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7620cee350ab69f55737e6336b275218a70b6891
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607712"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator==-Operator
Gibt an, ob die zwei Parameter gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
```  
  
### <a name="parameters"></a>Parameter  
 *LHS*  
 Der erste Parameter, verglichen werden soll. *LHS* kann ein **HStringReference** Objekt oder ein HSTRING-Handle.  
  
 *RS*  
 Der zweite Parameter, verglichen werden soll.  *RS* kann ein **HStringReference** Objekt oder ein HSTRING-Handle.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn die *Lhs* und *RS* Parameter gleich sind; andernfalls, **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)