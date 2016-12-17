---
title: "Compilerfehler C2802"
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
  - "C2802"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2802"
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2802
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Statischer Member 'Operator Operator' besitzt keine formalen Parameter  
  
 Ein Operator, der durch eine `static`\-Memberfunktion deklariert wird, muss mindestens einen Parameter haben.  
  
 Im folgenden Beispiel wird C2802 generiert:  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```