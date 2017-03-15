---
title: "future_error-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::future_error"
dev_langs: 
  - "C++"
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# future_error-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Ausnahmeobjekt, das von Methoden von Typen ausgelöst werden, die Objekte [Zukunft](../standard-library/future-class.md) verwalten.  
  
## Syntax  
  
```  
class future_error : public logic_error {  
public:  
   future_error(error_code code);  
   const error_code& code() const throw();  
   const char *what() const throw();  
};  
```  
  
## Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [logic\_error\-Klasse](../standard-library/logic-error-class.md)   
 [error\_code\-Klasse](../standard-library/error-code-class.md)