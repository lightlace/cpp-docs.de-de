---
title: "Compilerfehler C2549"
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
  - "C2549"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2549"
ms.assetid: 29310094-54a3-4605-bc6d-a312a68daf5d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2549
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Angabe von Ergebnistypen für selbst definierte Konvertierungen nicht zulässig  
  
 Im folgenden Beispiel wird C2549 generiert:  
  
```  
// C2549.cpp  
// compile with: /c  
class X {  
public:  
   int operator int() { return value; }   // C2549  
  
   // try the following line instead  
   // operator int() { return value; }  
private:  
   int value;  
};  
```