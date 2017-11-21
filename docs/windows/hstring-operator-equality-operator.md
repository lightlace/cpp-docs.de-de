---
title: 'Hstring:: Operator ==-Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs: C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a53b451ca5beae1e26bdda8cac9041669f63cd87
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hstringoperator-operator"></a>HString::Operator==-Operator
Gibt an, ob die zwei Parameter gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline bool operator==(  
               const HString& lhs,   
               const HString& rhs) throw()  
  
inline bool operator==(  
                const HString& lhs,   
                const HStringReference& rhs) throw()  
  
inline bool operator==(  
                const HStringReference& lhs,   
                const HString& rhs) throw()  
  
inline bool operator==(  
                 const HSTRING& lhs,   
                 const HString& rhs) throw()  
  
inline bool operator==(  
                 const HString& lhs,   
                 const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `lhs`  
 Der erste Parameter, verglichen werden soll. `lhs`kann ein HString oder HStringReference-Objekt oder ein HSTRING-Handle.  
  
 `rhs`  
 Der zweite Parameter, verglichen werden soll.`rhs` kann ein HString oder HStringReference-Objekt oder ein HSTRING-Handle.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn die `lhs` und `rhs` Parameter gleich sind; andernfalls, `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)