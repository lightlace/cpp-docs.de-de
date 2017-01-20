---
title: "Compilerwarnung (Stufe 1) C4733"
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
  - "C4733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4733"
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inline\-ASM wird "FS:0" zugewiesen: Handler ist nicht als sicherer Handler registriert  
  
 Eine Funktion, durch die der **FS:0**\-Wert geändert wird, um einen neuen Ausnahmehandler hinzuzufügen, unterstützt u. U. keine sicheren Ausnahmen, da der Handler möglicherweise nicht als gültiger Ausnahmehandler registriert ist \(siehe [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)\).  
  
 Um diese Warnung zu vermeiden, entfernen Sie entweder die **FS:0**\-Definition oder deaktivieren die Warnung und legen die sicheren Ausnahmehandler mithilfe von [.SAFESEH](../../assembler/masm/dot-safeseh.md) fest.  
  
 Im folgenden Beispiel wird C4733 generiert:  
  
```  
// C4733.cpp  
// compile with: /W1 /c  
// processor: x86  
#include "stdlib.h"  
#include "stdio.h"  
void my_handler()  
{  
   printf("Hello from my_handler\n");  
   exit(1);  
}  
  
int main()  
{  
   _asm {  
      push    my_handler  
      mov     eax, DWORD PTR fs:0  
      push    eax  
      mov     DWORD PTR fs:0, esp   // C4733  
   }  
  
   *(int*)0 = 0;  
}  
```