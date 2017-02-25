---
title: "Compilerwarnung (Stufe 1) C4401 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4401"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4401"
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4401
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bitfeld': Member ist ein Bitfeld  
  
 Inlineassemblycode versucht, auf einen Bitfeldmember zuzugreifen.  Die Inlineassembly kann nicht auf Bitfeldmember zugreifen, sodass die letzte Ausrichtungsgrenze vor dem Bitfeldmember verwendet wird.  
  
 Um diese Warnung zu vermeiden, wandeln Sie den Bitfeldtyp in einen geeigneten Typ um, bevor Sie den Verweis im Inlineassemblycode erstellen.  Im folgenden Beispiel wird C4401 generiert:  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```