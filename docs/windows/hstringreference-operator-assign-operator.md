---
title: 'Hstringreference:: Operator = | Microsoft-Dokumentation'
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
ms.openlocfilehash: fc8f919dcec994be5d4f0300e9c96dde95895e16
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608520"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator=-Operator
Verschiebt den Wert eines anderen **HStringReference** -Objekt mit dem aktuellen **HStringReference** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
### <a name="parameters"></a>Parameter  
 *other*  
 Eine vorhandene **HStringReference** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des vorhandenen *andere* Objekt kopiert wird, mit dem aktuellen **HStringReference** -Objekt, und klicken Sie dann die *andere* -Objekt zerstört wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HStringReference-Klasse](../windows/hstringreference-class.md)