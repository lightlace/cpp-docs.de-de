---
title: "Compilerfehler C2650"
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
  - "C2650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2650"
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator' : Keine virtuelle Funktion zulässig  
  
 Ein Operator `new` oder ein Operator `delete` wurde als `virtual` deklariert.  Diese Operatoren stellen `static`\-Memberfunktionen dar und können nicht als `virtual` deklariert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2650 generiert:  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```