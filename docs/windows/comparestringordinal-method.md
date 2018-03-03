---
title: CompareStringOrdinal-Methode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c7e83d78bd311d7a3bfcba0cbe1a092c6c1c46b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### <a name="parameters"></a>Parameter  
 `lhs`  
 Das erste HSTRING, verglichen werden soll.  
  
 `rhs`  
 Das zweite HSTRING, verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Bedingung|  
|-----------|---------------|  
|-1|`lhs` ist kleiner als `rhs`.|  
|0|`lhs` ist gleich `rhs`.|  
|1|`lhs` ist größer als `rhs`.|  
  
## <a name="remarks"></a>Hinweise  
 Vergleicht zwei angegebene HSTRING-Objekte und gibt eine ganze Zahl, die ihre relative Position in einer Sortierreihenfolge angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::Details-Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)