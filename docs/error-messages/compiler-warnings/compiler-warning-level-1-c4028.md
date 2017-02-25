---
title: "Compilerwarnung (Stufe 1) C4028 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4028"
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
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