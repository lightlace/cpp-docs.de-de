---
title: "WeakReference::WeakReference-Konstruktor"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference, Konstruktor"
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference::WeakReference-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
WeakReference();  
```  
  
## <a name="remarks"></a>Hinweise  
 Initialisiert eine neue Instanz der dem [WeakReference-Klasse](../windows/weakreference-class1.md).  
  
 Der starken Verweiszeiger für die WeakReference-Objekt wird initialisiert, um `nullptr`, und die Anzahl der starken Verweise auf 1 initialisiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
    
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)