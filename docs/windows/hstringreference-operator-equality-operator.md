---
title: 'Hstringreference:: Operator ==-Operator | Microsoft Docs'
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
ms.openlocfilehash: 32cb8898cfc26297aaea888f9a382b5901ef8acf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887038"
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
  
#### <a name="parameters"></a>Parameter  
 `lhs`  
 Der erste Parameter, verglichen werden soll. `lhs` kann ein HStringReference-Objekt oder ein HSTRING-Handle.  
  
 `rhs`  
 Der zweite Parameter, verglichen werden soll.  `rhs` kann ein HStringReference-Objekt oder ein HSTRING-Handle.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn die `lhs` und `rhs` Parameter gleich sind; andernfalls, `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)