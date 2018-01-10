---
title: Weakref::&amp; Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::operator&
dev_langs: C++
helpviewer_keywords: operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 787712a857740afad539c0e44c450c6762aeb48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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