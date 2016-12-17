---
title: "Compilerwarnung (Stufe 1) C4028"
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
  - "C4028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4028"
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Formaler Parameter 'Nummer' unterscheidet sich von der Deklaration  
  
 Der Typ des formalen Parameters stimmt nicht mit dem entsprechenden Parameter in der Deklaration überein.  Der Typ in der ursprünglichen Deklaration wird verwendet.  
  
 Diese Warnung gilt nur für C\-Quellcode.  
  
## Beispiel  
 Im folgenden Beispiel wird C4028 generiert.  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```