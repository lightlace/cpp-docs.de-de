---
title: "Compilerfehler C2669"
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
  - "C2669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2669"
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Memberfunktion ist in einer anonymen Union nicht erlaubt  
  
 Anonyme Unions können keine Memberfunktionen enthalten.  
  
 Im folgenden Beispiel wird C2669 generiert:  
  
```  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  
## Siehe auch  
 [Anonyme Unions](../../misc/anonymous-unions.md)