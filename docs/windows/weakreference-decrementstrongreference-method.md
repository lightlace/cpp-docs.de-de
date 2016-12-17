---
title: "WeakReference::DecrementStrongReference-Methode"
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
  - "implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DecrementStrongReference-Methode"
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference::DecrementStrongReference-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>Hinweise  
 Dekrementiert den starken Verweiszähler des dem aktuellen WeakReference-Objekt.  
  
 Wenn die Anzahl der starken Verweise auf 0 (null) ist, die starke Referenz auf festgelegt ist `nullptr`.  
  
## <a name="return-value"></a>Rückgabewert  
 Der dekrementierte starken Verweiszähler.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
[WeakReference-Klasse](../windows/weakreference-class1.md)  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)