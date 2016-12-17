---
title: "Aufrufen von C-Funktionen in der Inlineassembly"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], Aufrufende Funktionen"
  - "Funktionsaufrufe, C-Funktionen"
  - "Funktionsaufrufe, In der Inlineassembly"
  - "Funktionen [C], Aufrufen in der Inlineassembly"
  - "Inlineassembly, Aufrufende Funktionen"
  - "Visual C, Funktionen"
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Aufrufen von C-Funktionen in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Ein `__asm`\-Block kann C\-Funktionen, einschließlich C\-Bibliotheks routinen aufrufen.  Im folgenden Beispiel wird die `printf` routine Bibliothek an:  
  
```  
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp  
// processor: x86  
#include <stdio.h>  
  
char format[] = "%s %s\n";  
char hello[] = "Hello";  
char world[] = "world";  
int main( void )  
{  
   __asm  
   {  
      mov  eax, offset world  
      push eax  
      mov  eax, offset hello  
      push eax  
      mov  eax, offset format  
      push eax  
      call printf  
      //clean up the stack so that main can exit cleanly  
      //use the unused register ebx to do the cleanup  
      pop  ebx  
      pop  ebx  
      pop  ebx  
   }  
}  
```  
  
 Da Funktionsargumente auf dem Stapel übergeben werden, drücken Sie einfach die erforderlichen Argumente einen Zeichenfolgenzeiger mit dem vorhergehenden Beispiel, bevor die Funktion aufgerufen wird.  Die Argumente werden in umgekehrter Reihenfolge abgelegt werden, sodass sie den Stapel in der gewünschten Reihenfolge ab.  Um die C\-Anweisung emulieren  
  
```  
printf( format, hello, world );  
```  
  
 Das Beispiel legt Zeiger auf `world``hello`, und `format`, in dieser Reihenfolge und ruft dann `printf`an.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)