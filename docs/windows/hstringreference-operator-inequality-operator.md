---
title: "HStringReference::Operator!=-Operator"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!="
dev_langs: 
  - "C++"
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator!=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob die zwei Parameter ungleich sind.  
  
## Syntax  
  
```cpp  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### Parameter  
 `lhs`  
 Der erste Parameter zu vergleichen.  `lhs` kann ein HStringReference\-Objekt oder ein HSTRING\-Handle sein.  
  
 `rhs`  
 Der zweite Parameter zu vergleichen. `rhs` kann ein HStringReference\-Objekt oder ein HSTRING\-Handle sein.  
  
## Rückgabewert  
 `true`, wenn der `lhs`\-Parameter und der `rhs`\-Parameter ungleich sind, andernfalls `false`.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HStringReference\-Klasse](../windows/hstringreference-class.md)