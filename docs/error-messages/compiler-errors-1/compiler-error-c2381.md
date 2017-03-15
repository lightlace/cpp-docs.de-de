---
title: "Compilerfehler C2381 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2381"
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Neudefinition; \_\_declspec\(noreturn\) unterscheidet sich  
  
 Eine Funktion wurde deklariert und anschließend definiert, in der Definition wurde jedoch der [noreturn](../../cpp/noreturn.md)\-Modifizierer für `__declspec` verwendet.  Durch Verwendung von `noreturn` wird die Neudefinition der Funktion festgelegt. Deklaration und Definition müssen bezüglich der Verwendung von `noreturn` angeglichen werden.  
  
 Im folgenden Beispiel wird C2381 generiert:  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```