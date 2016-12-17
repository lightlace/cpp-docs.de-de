---
title: "Compilerfehler C3120"
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
  - "C3120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3120"
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3120
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Methodenname': Schnittstellenmethoden können keine Variablenargumentlisten verwenden  
  
 Eine Schnittstellenmethode kann keine Variablenargumentliste enthalten.  Durch die folgende Schnittstellendefinition wird z. B. C3120 generiert:  
  
```  
// C3120.cpp  
__interface A {  
int X(int i, ...);    // C3120  
};  
  
int main(void) { return(0); }  
```