---
title: "operator!=-Operator (Microsoft::WRL)"
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
  - "client/Microsoft::WRL::operator!="
dev_langs: 
  - "C++"
ms.assetid: 785435da-87a6-4454-9bce-9d288a96dc26
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# operator!=-Operator (Microsoft::WRL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ungleichheitsoperator für [ComPtr](../windows/comptr-class.md) und [ComPtrRef](../windows/comptrref-class.md)\-Objekte.  
  
## Syntax  
  
```  
WRL_NOTHROW bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
WRL_NOTHROW bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
WRL_NOTHROW bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
WRL_NOTHROW bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
WRL_NOTHROW bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### Parameter  
 `a`  
 Das linksobjekt.  
  
 `b`  
 Das richtige Objekt.  
  
## Rückgabewert  
 `true`, wenn die Objekte ungleich sind, andernfalls `false`.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)