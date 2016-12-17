---
title: "Compilerwarnung (Stufe 3) C4570"
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
  - "C4570"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4570"
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4570
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Ist nicht explizit als abstrakt deklariert, weist jedoch abstrakte Funktionen auf  
  
 Ein Typ, der [abstract](../../windows/abstract-cpp-component-extensions.md)\-Funktionen enthält, sollte selbst als abstrakt gekennzeichnet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C4570 generiert.  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```