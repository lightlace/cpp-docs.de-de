---
title: "Compilerwarnung (Stufe 1) C4319"
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
  - "C4319"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4319"
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4319
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': Mit 0 erweitert von 'type' zu größerem 'type'  
  
 Das Ergebnis des ~\-Operators \(bitweises Komplement\) ist nicht signiert und wird anschließend mit 0 erweitert, wenn es zu einem größeren Typ konvertiert wird.  
  
 Im folgenden Beispiel wird ~\(a \- 1\) als ein nicht signierter, langer 32\-Bit\-Ausdruck ausgewertet und anschließend durch die Erweiterung mit 0 zu 64 Bit konvertiert.  Dies kann zu unerwarteten Vorgangsergebnisse führen.  
  
```  
// C4319.cpp  
// compile with: cl /W4 C4319.cpp  
int main() {  
   unsigned long a = 0;  
   unsigned long long q = 42;  
   q = q & ~(a - 1);    // C4319 expected  
}  
```