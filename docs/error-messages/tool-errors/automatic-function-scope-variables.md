---
title: "Automatische Variablen (mit Funktionsg&#252;ltigkeitsbereich)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automatische Variablen"
  - "Funktionen [C++], Gültigkeitsbereich"
  - "Gültigkeitsbereich, Deklariert innerhalb von Funktionen"
  - "Variablen, Automatisch"
ms.assetid: 6e1a14c2-1fb0-4937-8628-8d963cc35ed4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Automatische Variablen (mit Funktionsg&#252;ltigkeitsbereich)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Variable, die innerhalb einer Funktion deklariert wurde, kann nur innerhalb des Gültigkeitsbereichs dieser Funktion verwendet werden.  
  
```  
// LNK2019_AV.cpp  
// compile with: /c  
void test(void);  
  
static int lnktest3 = 3;  
int lnktest4 = 4;  
  
int main() {  
   static int lnktest1 = 1;  
   int lnktest2 = 2;  
   test();  
}  
```  
  
 und anschließend  
  
```  
// LNK2019_AV_2.cpp  
// compile with: LNK2019_AV.cpp  
// LNK2019 expected  
extern int lnktest1;  
extern int lnktest2;  
extern int lnktest3;  
extern int lnktest4;  
  
void test(void) {  
   int i = 0;  
   i = lnktest1;  
   i = lnktest2;  
   i = lnktest3;  
   i = lnktest4;   // OK  
}  
```  
  
## Siehe auch  
 [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)