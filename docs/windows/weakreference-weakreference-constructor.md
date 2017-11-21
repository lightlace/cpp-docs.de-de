---
title: 'WeakReference:: WeakReference-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::WeakReference
dev_langs: C++
helpviewer_keywords: WeakReference, constructor
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3eedb6f083bb9c936eaa34bfcde0463db494c60f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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