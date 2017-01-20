---
title: "Compilerfehler C2805"
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
  - "C2805"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2805"
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2805
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Binärer Operator 'Operator' hat zu wenig Parameter  
  
 Der binäre Operator hat keine Parameter.  
  
 Im folgenden Beispiel wird C2805 generiert:  
  
```  
// C2805.cpp  
// compile with: /c  
class X {  
public:  
   X operator< ( void );   // C2805 must take one parameter  
   X operator< ( X );   // OK  
};  
```