---
title: "Compilerfehler C2361"
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
  - "C2361"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2361"
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2361
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisierung von 'Bezeichner' durch 'Standard'\-Marke übersprungen  
  
 Die Initialisierung von `identifier` kann in einer `switch`\-Anweisung übersprungen werden.  Sprünge hinter eine Deklaration sind bei einer Initialisierung nicht zulässig, es sein denn, sie befindet sich innerhalb eines Blockes. \(Sofern die Variable nicht innerhalb eines Blockes definiert ist, befindet sie sich bis zum Ende der `switch`\-Anweisung innerhalb des Gültigkeitsbereichs.\)  
  
 Im folgenden Beispiel wird C2361 generiert:  
  
```  
// C2361.cpp  
void func( void ) {  
   int x;  
   switch (x) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   default :   // C2361 error  
      int k = 1;  
   }  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2361b.cpp  
// compile with: /c  
void func( void ) {  
   int x = 0;  
   switch (x) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   default :  
      int k = 1;  
   }  
}  
```