---
title: Hstring::&lt; Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs: C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 84725ca0ceeb4778bec2add60c7e96eff3ab3bfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hstringoperatorlt-operator"></a>Hstring::&lt; Operator
Gibt an, ob der erste Parameter ist kleiner als der zweite Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `lhs`  
 Der erste Parameter, verglichen werden soll. `lhs`Ein Verweis auf ein HString kann sein.  
  
 `rhs`  
 Der zweite Parameter, verglichen werden soll. `rhs`Ein Verweis auf ein HString kann sein.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn die `lhs` Parameter ist kleiner als das `rhs` Parameter ist, andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)