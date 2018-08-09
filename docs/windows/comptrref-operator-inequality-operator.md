---
title: Comptrref::! =-Operator | Microsoft-Dokumentation
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
ms.openlocfilehash: 4e2f0c432189dce1af9a255570dd259a90693591
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651290"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!=-Operator
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
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
  
### <a name="parameters"></a>Parameter  
 *a*  
 Ein Verweis auf eine **ComPtrRef** Objekt.  
  
 *b*  
 Ein Verweis auf einen anderen **ComPtrRef** Objekt oder ein Zeiger auf ein anonymes Objekt (`void*`).  
  
## <a name="return-value"></a>Rückgabewert  
 Der erste Operator ergibt **"true"** Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls **"false"**.  
  
 Führen Sie die zweite und dritte Operator **"true"** Wenn Objekt *eine* ist nicht gleich **"nullptr"** ist, andernfalls **"false"**.  
  
 Die vierten und fünften-Operatoren ergeben **"true"** Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 Gibt an, ob zwei **ComPtrRef** -Objekte ungleich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef-Klasse](../windows/comptrref-class.md)