---
title: "Compilerfehler C3866 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3866"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3866"
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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