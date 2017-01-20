---
title: "Compilerwarnung (Stufe 1) C4731"
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
  - "C4731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4731"
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeiger': Das Framezeigerregister 'Register' wurde vom Inlineassemblycode geändert  
  
 Ein Framezeigerregister wurde geändert.  Sie müssen das Register im Inlineassemblyblock oder in der Rahmenvariablen \(lokal oder Parameter, abhängig vom geänderten Register\) speichern und wiederherstellen, da der Code andernfalls u. U. nicht einwandfrei funktioniert.  
  
 Im folgenden Beispiel wird C4731 generiert:  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP ist der Framezeiger \(FPO ist nicht zulässig\) und wird geändert.  Wenn später auf `p` verwiesen wird, erfolgt der Verweis relativ zu `EBP`.  Da `EBP` jedoch vom Code außer Kraft gesetzt wurde, funktioniert das Programm nicht einwandfrei und verursacht u. U. sogar einen Fehler.