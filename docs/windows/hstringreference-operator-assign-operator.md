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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 097e89ab4ae2d3b6ddaacb2fa52b811c1577ef72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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