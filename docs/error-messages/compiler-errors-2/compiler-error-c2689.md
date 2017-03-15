---
title: "Compilerfehler C2689 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2689"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2689"
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2689
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Eine Friend\-Funktion kann nicht innerhalb einer lokalen Klasse definiert werden  
  
 Innerhalb einer lokalen Klasse kann eine `friend`\-Funktion zwar deklariert, aber nicht definiert werden.  
  
 Im folgenden Beispiel wird C2689 generiert:  
  
```  
// C2689.cpp  
// compile with: /c  
void g() {  
   void f2();  
   class X {  
      friend void f2(){}   // C2689  
      friend void f2();   // OK  
   };  
}  
```