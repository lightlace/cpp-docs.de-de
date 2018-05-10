---
title: Comptr::! =-Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2450b5d473d1caadae171516cf337479bfd5d603
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperator-operator"></a>ComPtr::operator!=-Operator
Gibt an, ob zwei ComPtr-Objekte ungleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `a`  
 Ein Verweis auf ein ComPtr-Objekt.  
  
 `b`  
 Ein Verweis auf ein anderes ComPtr-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Der erste Operator liefert `true` Wenn Objekt `a` stimmt nicht mit der Objekt- `b`ist, andernfalls `false`.  
  
 Der zweite und dritte Operator yield `true` Wenn Objekt `a` stimmt nicht mit `nullptr`ist, andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr-Klasse](../windows/comptr-class.md)