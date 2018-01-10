---
title: Hstringreference::&lt; Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs: C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac370a8d863e7c71dcd3564b3a5d0ae7d214322d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Der erste Parameter, verglichen werden soll. `lhs`Ein Verweis auf ein HStringReference kann sein.  
  
 `rhs`  
 Der zweite Parameter, verglichen werden soll.  `rhs`Ein Verweis auf ein HStringReference kann sein.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn die `lhs` Parameter ist kleiner als das `rhs` Parameter ist, andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)