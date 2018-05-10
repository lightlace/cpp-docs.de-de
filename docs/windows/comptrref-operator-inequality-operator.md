---
title: Comptrref::! =-Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs:
- C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d5a6e7389215452177add30b587004c312aeae1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!=-Operator
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `a`  
 Ein Verweis auf ein ComPtrRef-Objekt.  
  
 `b`  
 Ein Verweis auf ein anderes ComPtrRef-Objekt oder ein Zeiger auf ein anonymes Objekt (`void*`).  
  
## <a name="return-value"></a>Rückgabewert  
 Der erste Operator liefert `true` Wenn Objekt `a` stimmt nicht mit der Objekt- `b`ist, andernfalls `false`.  
  
 Der zweite und dritte Operator yield `true` Wenn Objekt `a` stimmt nicht mit `nullptr`ist, andernfalls `false`.  
  
 Die vierten und fünften Operatoren ergeben `true` Wenn Objekt `a` stimmt nicht mit der Objekt- `b`ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Gibt an, ob zwei ComPtrRef-Objekte nicht gleich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef-Klasse](../windows/comptrref-class.md)