---
title: 'Hstringreference:: Operator = | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73ec71526d340aafb16ddf2af274dce7ad0e9cbd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875538"
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