---
title: CompareStringOrdinal-Methode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3abf87340671d1ac4851b055a57896e340d0c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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