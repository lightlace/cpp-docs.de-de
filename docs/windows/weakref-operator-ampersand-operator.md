---
title: Weakref::&amp; Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c8221b405618b1879f4e4c865115a227eb09857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890108"
---
# <a name="weakrefoperatoramp-operator"></a>Weakref::&amp; Operator
Gibt ein ComPtrRef-Objekt zurück, das das aktuelle WeakRef-Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein ComPtrRef-Objekt, das das aktuelle WeakRef-Objekt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Dies ist eine interne Hilfsmethode-Operator, der nicht in Ihrem Code verwendet werden soll.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)