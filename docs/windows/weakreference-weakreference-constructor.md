---
title: 'WeakReference:: WeakReference-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference, constructor
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e60b23a0c63ce1415765dd1f94863540849f975
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891060"
---
# <a name="weakreferenceweakreference-constructor"></a>WeakReference::WeakReference-Konstruktor
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
WeakReference();  
```  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der dem [WeakReference-Klasse](../windows/weakreference-class1.md).  
  
 Der starke Verweiszeiger für die WeakReference-Objekt wird initialisiert, um `nullptr`, und die Anzahl der starken Verweis wird mit 1 initialisiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
    
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)