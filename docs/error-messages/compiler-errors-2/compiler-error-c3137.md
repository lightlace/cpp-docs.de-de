---
title: "Compilerfehler C3137"
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
  - "C3137"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3137"
ms.assetid: 70bb1313-2e87-43ed-a0d8-33fa6ff475e4
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3137
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Eigenschaft' : Eine Eigenschaft kann nicht initialisiert werden  
  
 Eine Eigenschaft kann nicht, z. B. in der Initialisierungsliste eines Konstruktors, initialisiert werden.  
  
 Im folgenden Beispiel wird C3137 generiert:  
  
```  
// C3137.cpp  
// compile with: /clr /c  
ref class CMyClass {  
public:  
   property int Size {  
      int get() {  
         return 0;  
      }  
      void set( int i ) {}  
   }  
  
   CMyClass() : Size( 1 ) {   // C3137  
      // to resolve this C3137, remove the initializer from the  
      // ctor declaration and perform the assignment as follows  
      // Size = 1;  
   }  
};  
```  
  
 Im folgenden Beispiel wird C3137 generiert:  
  
```  
// C3137_2.cpp  
// compile with: /clr:oldSyntax /c  
__gc class CMyClass {  
public:  
   __property int get_Size() {  
      return 0;  
   }  
   __property void set_Size(int i) {}  
  
   CMyClass() : Size(1) {   // C3137  
      // to resolve this C3137, remove the initializer from the  
      // ctor declaration and perform the assignment as follows  
      // Size = 1;  
   }  
};  
```