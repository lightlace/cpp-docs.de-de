---
title: "Compilerfehler C2831"
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
  - "C2831"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2831"
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2831
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Standardparameter für 'Operator Operator' nicht möglich  
  
 Standardparameter sind nur für drei Operatoren zulässig:  
  
-   [new](../../cpp/new-operator-cpp.md)  
  
-   Zuweisung \=  
  
-   Linke runde Klammer \(  
  
 Im folgenden Beispiel wird C2831 generiert:  
  
```  
// C2831.cpp  
// compile with: /c  
#define BINOP <=  
class A {  
public:  
   int i;  
   int operator BINOP(int x = 1) {   // C2831  
   // try the following line instead  
   // int operator BINOP(int x) {  
      return i+x;  
   }  
};  
```