---
title: 'Comptrref:: Operator ==-Operator | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs:
- C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0b7cc1d89a0e113164530245467afd94becdc1e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator==-Operator
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `a`  
 Ein Verweis auf ein ComPtrRef-Objekt.  
  
 `b`  
 Ein Verweis auf ein anderes ComPtrRef-Objekt, oder ein Zeiger auf einen anonymen Typ (`void*`).  
  
## <a name="return-value"></a>Rückgabewert  
 Der erste Operator liefert `true` Wenn Objekt `a` Objekt entspricht `b`ist, andernfalls `false`.  
  
 Der zweite und dritte Operator yield `true` Wenn Objekt `a` gleich `nullptr`ist, andernfalls `false`.  
  
 Die vierten und fünften Operatoren ergeben `true` Wenn Objekt `a` Objekt entspricht `b`ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Gibt an, ob zwei ComPtrRef-Objekte gleich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef-Klasse](../windows/comptrref-class.md)