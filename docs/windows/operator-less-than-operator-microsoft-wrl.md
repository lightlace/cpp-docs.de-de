---
title: 'Operator&lt; -Operator (Microsoft:: wrl) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
dev_langs:
- C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3ea56386cadc638fd0234993ef6a8a0f5eb2be
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="operatorlt-operator-microsoftwrl"></a>Operator&lt; -Operator (Microsoft:: wrl)
Bestimmt, ob die Adresse eines Objekts kleiner als ein anderes ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<class T, class U>  
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();  
template<class T, class U>  
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `a`  
 Das linke Objekt.  
  
 `b`  
 Das rechte Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Adresse des `a` ist kleiner als die Adresse des `b`ist, andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)