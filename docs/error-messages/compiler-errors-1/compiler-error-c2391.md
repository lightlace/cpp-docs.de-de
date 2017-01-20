---
title: "Compilerfehler C2391"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2391"
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': 'friend' innerhalb von Typdefinitionen nicht zulässig  
  
 Die `friend`\-Deklaration umfasst eine vollständige Klassendeklaration.  Durch eine `friend`\-Deklaration kann eine Memberfunktion oder ein ausgearbeiteter Typspezifizierer angegeben werden, aber keine vollständige Klassendeklaration.  
  
 Im folgenden Beispiel wird C2326 generiert:  
  
```  
// C2391.cpp  
// compile with: /c  
class D {   
   void func( int );   
};  
  
class A {  
   friend class B { int i; };   // C2391  
  
   // OK  
   friend class C;  
   friend void D::func(int);  
};  
```