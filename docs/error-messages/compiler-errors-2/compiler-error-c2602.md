---
title: "Compilerfehler C2602"
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
  - "C2602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2602"
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse::Bezeichner' ist kein Member einer Basisklasse von 'Klasse'  
  
 Es ist kein Zugriff auf `Identifier` möglich, da es sich nicht um einen von einer Basisklasse geerbten Member handelt.  
  
 Im folgenden Beispiel wird C2602 generiert:  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```