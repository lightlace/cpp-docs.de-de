---
title: "Compilerfehler C2634 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2634"
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'&class::member: der Zeiger, auf Verweismember ist ungültig  
  
 Es wurde ein Zeiger auf einen Verweismember deklariert.  
  
 Im folgenden Beispiel wird C2634 generiert:  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```