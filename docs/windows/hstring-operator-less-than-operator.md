---
title: "HString::Operator&lt;-Operator"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator<"
dev_langs: 
  - "C++"
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator&lt;-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob der erste Parameter kleiner als der zweite Parameter ist.  
  
## Syntax  
  
```cpp  
  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### Parameter  
 `lhs`  
 Der erste Parameter zu vergleichen.  `lhs` kann ein Verweis auf ein HString sein.  
  
 `rhs`  
 Der zweite Parameter zu vergleichen.  `rhs` kann ein Verweis auf ein HString sein.  
  
## Rückgabewert  
 `true`, wenn der `lhs`\-Parameter kleiner ist, als Parameter der `rhs` ; andernfalls `false`.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)