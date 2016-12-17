---
title: "Compilerfehler C3866"
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
  - "C3866"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3866"
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3866
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dem Funktionsaufruf fehlt die Argumentliste  
  
 In einer nicht statischen Memberfunktion steht keine Argumentliste für einen Destruktor\- oder Finalizer\-Aufruf zur Verfügung.  
  
 Im folgenden Beispiel wird C3866 generiert:  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```