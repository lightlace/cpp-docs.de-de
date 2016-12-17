---
title: "Compilerwarnung (Stufe 1) C4405"
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
  - "C4405"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4405"
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4405
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Bezeichner ist ein reserviertes Wort  
  
 Ein für die Inlineassembly reserviertes Wort wird als Variablenname verwendet.  Dies kann zu unvorhersehbaren Ergebnissen führen.  Damit diese Warnung nicht mehr angezeigt wird, sollten Variablen nicht mit Wörtern benannt werden, die für die Inlineassembly reserviert wurden.  Im folgenden Beispiel wird C4405 generiert:  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```