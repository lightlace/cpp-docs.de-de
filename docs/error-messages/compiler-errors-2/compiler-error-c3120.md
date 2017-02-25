---
title: "Compilerfehler C3120 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3120"
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
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