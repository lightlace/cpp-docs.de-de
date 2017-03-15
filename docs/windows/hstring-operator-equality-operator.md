---
title: "HString::Operator==-Operator"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator=="
dev_langs: 
  - "C++"
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator==-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob die zwei Parameter gleich sind.  
  
## Syntax  
  
```cpp  
  
inline bool operator==(  
               const HString& lhs,   
               const HString& rhs) throw()  
  
inline bool operator==(  
                const HString& lhs,   
                const HStringReference& rhs) throw()  
  
inline bool operator==(  
                const HStringReference& lhs,   
                const HString& rhs) throw()  
  
inline bool operator==(  
                 const HSTRING& lhs,   
                 const HString& rhs) throw()  
  
inline bool operator==(  
                 const HString& lhs,   
                 const HSTRING& rhs) throw()  
  
```  
  
#### Parameter  
 `lhs`  
 Der erste Parameter zu vergleichen.  `lhs` kann ein Objekt HString oder HStringReference sein oder ein HSTRING\-Handle.  
  
 `rhs`  
 Der zweite Parameter zu vergleichen.`rhs` kann ein Objekt HString oder HStringReference sein oder ein HSTRING\-Handle.  
  
## Rückgabewert  
 `true`, wenn der `lhs`\-Parameter und der `rhs`\-Parameter gleich sind, andernfalls `false`.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)