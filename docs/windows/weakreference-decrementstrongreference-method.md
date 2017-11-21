---
title: 'WeakReference:: Decrementstrongreference-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs: C++
helpviewer_keywords: DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8526385764206b3bb72691fa0ed5232f8f6edf8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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