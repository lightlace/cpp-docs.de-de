---
title: "Compilerfehler C2351"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2351"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2351"
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2351
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Veraltete Syntax für die Initialisierung eines C\+\+\-Konstruktors  
  
 In einer Initialisierungsliste eines Konstruktors im neuen Format muss jede direkte Basisklasse explizit benannt werden, selbst wenn sie die einzige in der Liste ist.  
  
 Im folgenden Beispiel wird C2351 generiert:  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```