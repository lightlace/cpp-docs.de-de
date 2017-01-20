---
title: "Compilerfehler C2180"
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
  - "C2180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2180"
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

steuernder Ausdruck ist vom Typ "type".  
  
 Der steuernde Ausdruck in eine `if`\-, `while`\- oder `for`\-Anweisung, oder die `do`\-Anweisung ist ein konvertierter Ausdruck für `void`.  Um dieses Problem zu beheben, ändern Sie den steuernden Ausdruck so, dass er einen `bool`\-Typ oder einen Typ erstellt, der in `bool` konvertiert werden kann.  
  
 Im folgenden Beispiel wird C2180 generiert:  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```