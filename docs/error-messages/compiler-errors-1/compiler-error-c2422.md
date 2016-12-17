---
title: "Compilerfehler C2422"
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
  - "C2422"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2422"
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2422
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unzulässige Segmentüberschreibung in 'Operand'  
  
 Der Inlineassemblercode verwendet fälschlicherweise einen Segmentüberschreibungsoperator \(Doppelpunkt\) für einen Operanden.  Mögliche Ursachen sind:  
  
-   Das Register, das dem Operator vorangeht, ist kein Segmentregister.  
  
-   Das Register, das dem Operator vorangeht, ist nicht das einzige Segmentregister im Operanden.  
  
-   Der Segmentüberschreibungsoperator steht innerhalb der eckigen Klammern eines Dereferenzierungsoperators.  
  
-   Der auf den Segmentüberschreibungsoperator folgende Ausdruck ist kein direkter Operand oder Speicheroperand.  
  
 Im folgenden Beispiel wird C2422 generiert:  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```