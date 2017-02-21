---
title: "Compilerwarnung (Stufe 4) C4740 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4740"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4740"
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4740
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fluss in oder aus einen\/einem Inline\-ASM\-Code verhindert die globale Optimierung  
  
 Wennn ein Sprung in einen oder aus einem `asm`\-Block vorhanden ist, werden die globalen Optimierungen für diese Funktion deaktiviert.  
  
 Im folgenden Beispiel wird C4740 generiert:  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```