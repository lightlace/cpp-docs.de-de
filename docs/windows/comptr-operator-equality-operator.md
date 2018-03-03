---
title: 'Comptr:: Operator ==-Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator==
dev_langs:
- C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7eac03b462aeec3b30b00b2f065de645209178bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-operator"></a>ComPtr::operator==-Operator
Gibt an, ob zwei ComPtr-Objekte gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
bool operator==(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator==(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
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
 Der erste Operator liefert `true` Wenn Objekt `a` Objekt entspricht `b`ist, andernfalls `false`.  
  
 Der zweite und dritte Operator yield `true` Wenn Objekt `a` gleich `nullptr`ist, andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr-Klasse](../windows/comptr-class.md)