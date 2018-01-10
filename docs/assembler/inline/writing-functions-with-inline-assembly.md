---
title: Schreiben von Funktionen mit der Inlineassembly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2fc9e6a1d2c94e74ef8aabf085af8fc4dc0bc28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="writing-functions-with-inline-assembly"></a>Schreiben von Funktionen mit der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Wenn Sie eine Funktion mit Inline-Assemblycode schreiben, ist es einfach an die Funktion als Argumente übergeben und von ihm einen Wert zurückgeben. Die folgenden Beispiele vergleichen eine Funktion zuerst für ein getrennter Assembler geschrieben, und klicken Sie dann für den Inlineassembler umgeschrieben. Die Funktion mit der Bezeichnung `power2`, empfängt der zwei Parameter, den ersten Parameter mit 2, um die Leistungsfähigkeit des zweiten Parameters multipliziert. Für ein getrennter Assembler geschrieben wurde, kann die Funktion wie folgt aussehen:  
  
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
  
 Da es für ein getrennter Assembler geschrieben wird, erfordert die Funktion einen separaten Quellcodefenster-Datei und Assembly- und Verknüpfungsschritte. Argumente für C- und C++-Funktion in der Regel auf dem Stapel übergeben sind also diese Version der `power2` Funktion greift auf die Argumente durch ihre Positionen im Stapel. (Beachten Sie, dass die **Modell** -Direktive in MASM und einige andere assemblern kann auch die Stapelrahmen Funktionsargumente und lokale Stapelvariablen anhand Ihres Namens zugreifen.)  
  
## <a name="example"></a>Beispiel  
 Dieses Programm schreibt die `power2` -Funktion mit Inline-Assemblycode:  
  
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
  
 Die inlineversion der der `power2` Funktion bezieht sich auf den Argumenten anhand des Namens und wird in der gleichen Quelldatei wie der Rest des Programms angezeigt. Diese Version erfordert auch weniger Assemblyanweisungen.  
  
 Da die inlineversion der `power2` C führt nicht `return` -Anweisung, er bewirkt, dass eine Warnung ignorieren beim Kompilieren auf Warnstufe 2 oder höher. Die Funktion gibt einen Wert zurück, aber der Compiler kann nicht mitzuteilen, dass in Ermangelung einer `return` Anweisung. Sie können [#pragma Warning](../../preprocessor/warning.md) zum Deaktivieren der Generierung der Warnung.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)