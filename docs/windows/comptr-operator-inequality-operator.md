---
title: "ComPtr::operator!=-Operator"
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
  - "client/Microsoft::WRL::ComPtr::operator!="
dev_langs: 
  - "C++"
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator!=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob zwei ComPtr\-Objekte nicht gleich sind.  
  
## Syntax  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### Parameter  
 `a`  
 Ein Verweis auf einen ComPtr\-Objekt.  
  
 `b`  
 Ein Verweis auf ein anderes ComPtr\-Objekt.  
  
## Rückgabewert  
 Im ersten Operator ergibt `true`, wenn Objekt `a` ungleich Objekt `b` ist; andernfalls `false`.  
  
 Im zweiten und dritten Operatoren führen `true`, wenn `a`\-Objekt nicht gleich `nullptr` ist; andernfalls `false`.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr\-Klasse](../windows/comptr-class.md)