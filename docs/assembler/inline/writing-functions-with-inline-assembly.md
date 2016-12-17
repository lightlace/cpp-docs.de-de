---
title: "Schreiben von Funktionen mit der Inlineassembly"
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
  - "__asm-Schlüsselwort [C++], In Funktionen"
  - "Assembler [C++], Schreiben von Funktionen"
  - "Funktionen [C++], Inlineassembly"
  - "Inlineassembly [C++], Schreiben von Funktionen"
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Schreiben von Funktionen mit der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Wenn Sie eine Funktion mit Inlineassemblycode schreiben, ist es einfach, Argumente für die Funktion zu übergeben und von ihr einen Wert zurückzugeben.  Die folgenden Beispiele vergleichen eine Funktion, die ursprünglich für einen separaten Assembler geschrieben wird und dann für den Inlineassembler neu geschrieben ist.  Die Funktion, die aufgerufen `power2`zwei Parameter und empfängt den ersten Parameter mit 2 multipliziert mit des zweiten Parameters.  Geschrieben für einen separaten Assembler, könnte die Funktion wie folgt aus:  
  
```  
; POWER.ASM  
; Compute the power of an integer  
;  
       PUBLIC _power2  
_TEXT SEGMENT WORD PUBLIC 'CODE'  
_power2 PROC  
  
        push ebp        ; Save EBP  
        mov ebp, esp    ; Move ESP into EBP so we can refer  
                        ;   to arguments on the stack  
        mov eax, [ebp+4] ; Get first argument  
        mov ecx, [ebp+6] ; Get second argument  
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )  
        pop ebp         ; Restore EBP  
        ret             ; Return with sum in EAX  
  
_power2 ENDP  
_TEXT   ENDS  
        END  
```  
  
 Da er für einen separaten Assembler geschrieben hat, erfordert die Funktion Schritte einer separaten Quelldatei und der angegebenen Assembly und des Links.  C\- und C\+\+\-Funktionsargumente werden normalerweise auf dem Stapel, sodass diese Version der `power2`\-Funktion greift auf ihre Argumente durch ihre Positionen im Stapel übergeben.  \(Beachten Sie, **MODEL**\-Direktive, die auch in der verfügbare MASM und in einigen anderen Assemblern, das für den Zugriff auf stapel argumenten und den lokalen Stapel variablen nach Namen ermöglicht.\)  
  
## Beispiel  
 Dieses Programm schreibt die `power2`\-Funktion Inlineassemblycode:  
  
```  
// Power2_inline_asm.c  
// compile with: /EHsc  
// processor: x86  
  
#include <stdio.h>  
  
int power2( int num, int power );  
  
int main( void )  
{  
    printf_s( "3 times 2 to the power of 5 is %d\n", \  
              power2( 3, 5) );  
}  
int power2( int num, int power )  
{  
   __asm  
   {  
      mov eax, num    ; Get first argument  
      mov ecx, power  ; Get second argument  
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )  
   }  
   // Return with result in EAX  
}  
```  
  
 Die inline Version der `power2`\-Funktion bezieht sich auf ihre Argumente nach Namen an und wird in derselben Quelldatei wie der Rest des Programms.  Diese Version erfordert auch weniger Assemblyanweisungen.  
  
 Da die inline Version von `power2``return` im C\-Format Anweisung nicht ausgeführt wird, verursacht sie eine harmlose Warnung, wenn Sie auf Warnstufe 2 oder höher kompiliert wird.  Die Funktion gibt einen Wert zurück, der Compiler kann jedoch nicht in Ermangelung einer `return`\-Anweisung vermitteln.  Sie können [\#Pragmawarnung](../../preprocessor/warning.md) verwenden, um die Generierung dieser Warnung zu deaktivieren.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von C oder C\+\+ in \_\_asm\-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)