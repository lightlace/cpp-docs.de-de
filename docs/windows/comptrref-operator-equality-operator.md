---
title: 'Comptrref:: Operator ==-Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs:
- C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea2fd557c9ae7da6c696ab8f8174ad8610a9174b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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