---
title: "Compilerfehler C3487 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3487"
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'return type': Alle Rückgabeausdrücke müssen in denselben Typ hergeleitet werden: Zuvor war es 'return type'.  
  
 Ein Lambda\-Ausdruck muss seinen eigenen Rückgabetyp angeben, es sei denn, es enthält eine einzelne Rückgabeanweisung.  Wenn ein Lambda\-Ausdruck mehrere Rückgabeanweisungen enthält, müssen alle den gleichen Typ aufweisen.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie einen nachgestellten Rückgabetyp für den Lambda\-Ausdruck an.  Stellen Sie sicher, dass alle Rückgaben vom Lambda denselben Typ aufweisen oder implizit zu diesem Rückgabetyp konvertiert werden können.  
  
## Beispiel  
 Im folgende Beispiel wird C3487 generiert, da die Rückgabetypen vom Lambda nicht übereinstimmen.  
  
```  
// C3487.cpp  
// Compile by using: cl /c /W4 C3487.cpp  
  
int* test(int* pi) {  
   // To fix the error, uncomment the trailing return type below  
   auto odd_pointer = [=]() /* -> int* */ {  
      if (*pi % 2)   
         return pi;  
      return nullptr; // C3487 - nullptr is not an int* type  
   };  
   return odd_pointer();  
}  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)