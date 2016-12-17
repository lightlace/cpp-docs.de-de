---
title: "ComPtrRef::operator!=-Operator"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator!="
dev_langs: 
  - "C++"
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator!=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```cpp  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### Parameter  
 `a`  
 Ein Verweis auf einen ComPtrRef\-Objekt.  
  
 `b`  
 Ein Verweis auf ein anderes ComPtrRef\-Objekt oder ein Zeiger zu einem anonymen Objekt \(`void*`\).  
  
## Rückgabewert  
 Im ersten Operator ergibt `true`, wenn Objekt `a` ungleich Objekt `b` ist; andernfalls `false`.  
  
 Im zweiten und dritten Operatoren führen `true`, wenn `a`\-Objekt nicht gleich `nullptr` ist; andernfalls `false`.  
  
 Die vierten und fünften Operatoren führen `true`, wenn Objekt `a` ungleich Objekt `b` ist; andernfalls `false`.  
  
## Hinweise  
 Gibt an, ob zwei ComPtrRef\-Objekte nicht gleich sind.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef\-Klasse](../windows/comptrref-class.md)