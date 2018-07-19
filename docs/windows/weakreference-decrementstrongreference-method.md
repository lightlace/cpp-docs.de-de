---
title: 'WeakReference:: Decrementstrongreference-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d5605670e05f91f9f1293c8bff0f4d74e458d25
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890335"
---
# <a name="weakreferencedecrementstrongreference-method"></a>WeakReference::DecrementStrongReference-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>Hinweise  
 Dekrementiert den Wert der starke Verweis zählen das aktuelle WeakReference-Objekt.  
  
 Die starke Verweiszähler auf 0 (null) wird, wird der starke Verweis als festgelegt `nullptr`.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl wieder um eins erniedrigt starken Verweis.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
[WeakReference-Klasse](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)