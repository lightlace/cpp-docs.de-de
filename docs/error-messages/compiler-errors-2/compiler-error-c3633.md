---
title: "Compilerfehler C3633"
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
  - "C3633"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3633"
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3633
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' kann nicht als Member von verwaltetem 'Typ' definiert werden  
  
 CLR\-Verweisklassendatenmember können nur vom Typ POD C\+\+ sein.  In einem CLR\-Typ kann nur ein systemeigener POD\-Typ instanziiert werden.  Zum Beispiel kann ein POD\-Typ keinen Kopierkonstruktor oder einen Zuweisungsoperator enthalten.  
  
## Beispiel  
 Im folgenden Beispiel wird C3633 generiert.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3633 generiert.  
  
```  
// C3633_b.cpp  
// compile with: /clr:oldSyntax /c  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
__gc class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```