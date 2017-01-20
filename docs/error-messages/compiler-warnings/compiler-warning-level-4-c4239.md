---
title: "Compilerwarnung (Stufe 4) C4239"
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
  - "C4239"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4239"
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4239
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung verwendet: 'Token': Konvertierung von 'Typ' zu 'Typ'  
  
 Diese Typkonvertierung ist gemäß C\+\+\-Standard nicht zulässig. In diesem Fall ist sie jedoch als Erweiterung zulässig.  Auf diese Warnung folgt mindestens eine Zeile mit Erklärungen, in der erläutert wird, gegen welche Regel verstoßen wurde.  
  
## Beispiel  
 Im folgenden Beispiel wird C4239 generiert.  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## Beispiel  
 Umwandlung von ganzzahligen Typen in Enumerationstypen ist streng genommen nicht zulässig.  
  
 Im folgenden Beispiel wird C4239 generiert.  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```