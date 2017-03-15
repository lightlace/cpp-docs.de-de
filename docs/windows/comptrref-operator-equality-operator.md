---
title: "ComPtrRef::operator==-Operator"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator=="
dev_langs: 
  - "C++"
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator==-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```cpp  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### Parameter  
 `a`  
 Ein Verweis auf einen ComPtrRef\-Objekt.  
  
 `b`  
 Ein Verweis auf ein anderes ComPtrRef\-Objekt oder ein Zeiger zu einem anonymen Typ \(`void*`\).  
  
## Rückgabewert  
 Im ersten Operator ergibt `true`, wenn Objekt `a` gleich `b` ist; Objekt andernfalls `false`.  
  
 Im zweiten und dritten Operatoren führen Objekt `true`, wenn `a` gleich `nullptr` ist; andernfalls `false`.  
  
 Die vierten und fünften Operatoren führen Objekt `true`, wenn `a` gleich `b` ist; Objekt andernfalls `false`.  
  
## Hinweise  
 Gibt an, ob zwei ComPtrRef\-Objekte gleich sind.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef\-Klasse](../windows/comptrref-class.md)