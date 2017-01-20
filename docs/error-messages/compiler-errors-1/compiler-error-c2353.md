---
title: "Compilerfehler C2353"
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
  - "C2353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2353"
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausnahmespezifikation ist nicht zulässig  
  
 Ausnahmespezifikationen sind für Memberfunktionen verwalteter Klassen nicht zulässig.  
  
 Im folgenden Beispiel wird C2353 generiert:  
  
```  
// C2353.cpp  
// compile with: /clr /c  
ref class X {  
   void f() throw(int);   // C2353  
   void f();   // OK  
};  
```