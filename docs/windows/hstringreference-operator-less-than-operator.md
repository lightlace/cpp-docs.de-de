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
ms.openlocfilehash: 489d97252dcb4d20b7ef2f8557991a4e6016743d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605531"
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