---
title: "Compilerwarnung (Stufe 1) C4488 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4488"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4488"
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerwarnung (Stufe 1) C4488
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Das 'Schlüsselwort'\-Schlüsselwort muss die 'Schnittstelle'\-Schnittstellenmethode implementieren  
  
 Eine Klasse muss alle Member einer Schnittstelle implementieren, von der sie erbt.  Ein implementierter Member muss öffentlich zugreifbar sein und als virtuell gekennzeichnet werden.  
  
## Beispiel  
 C4488 kann auftreten, wenn ein implementierter Member nicht öffentlich ist.  Im folgenden Beispiel wird C4488 generiert.  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## Beispiel  
 C4488 kann auftreten, wenn ein implementierter Member nicht als virtuell gekennzeichnet ist.  Im folgenden Beispiel wird C4488 generiert.  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```