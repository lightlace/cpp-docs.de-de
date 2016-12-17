---
title: "is_error_code_enum-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "future/std::is_error_code_enum"
dev_langs: 
  - "C++"
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
caps.latest.revision: 13
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# is_error_code_enum-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spezialisierungen, die diesem [future\_errc](../Topic/future_errc%20Enumeration.md) angibt, kann zum Speichern von [error\_code](../standard-library/error-code-class.md).  
  
## Syntax  
  
```  
template<>  
struct is_error_code_enum<Future_errc> : public true_type;  
```  
  
## Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)