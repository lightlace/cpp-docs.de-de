---
title: 'Hstringreference:: Operator = | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs: C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b6a9938308f0cbd8339c24d1876c09ae49df349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator=-Operator
Verschiebt den Wert eines anderen HStringReference-Objekts zum aktuellen HStringReference-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### <a name="parameters"></a>Parameter  
 `other`  
 Ein vorhandenes HStringReference-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des vorhandenen `other` Objekt wird zum aktuellen HStringReference-Objekt kopiert und dann die `other` -Objekt zerstört wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)