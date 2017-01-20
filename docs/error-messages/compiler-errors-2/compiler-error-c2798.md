---
title: "Compilerfehler C2798"
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
  - "C2798"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2798"
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2798
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super::Member' ist mehrdeutig  
  
 Der Member, auf den mit [super](../../cpp/super.md) verwiesen wurde, ist in mehreren geerbten Strukturen enthalten.  Es gibt folgende Möglichkeiten, den Fehler zu beheben:  
  
-   Entfernen von B1 oder B2 aus der Vererbungsliste von D.  
  
-   Ändern des Namens des Datenmembers in B1 oder B2.  
  
 Im folgenden Beispiel wird C2798 generiert:  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```