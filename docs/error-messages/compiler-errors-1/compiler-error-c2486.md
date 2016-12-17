---
title: "Compilerfehler C2486"
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
  - "C2486"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2486"
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2486
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\_\_LOCAL\_SIZE" nur in Funktionen mit dem "naked"\-Attribut erlaubt  
  
 In Inlineassemblerfunktionen ist der Name `__LOCAL_SIZE` für Funktionen reserviert, die mit dem [naked](../../cpp/naked-cpp.md)\-Attribut deklariert werden.  
  
 Im folgenden Beispiel wird C2486 generiert:  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```