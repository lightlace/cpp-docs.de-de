---
title: Schreiben von Funktionen mit der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
ms.openlocfilehash: 7848a8f071f50f8d809a999a96a9c0f8193c480e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445187"
---
# <a name="writing-functions-with-inline-assembly"></a>Schreiben von Funktionen mit der Inlineassembly

**Microsoft-spezifisch**

Wenn Sie eine Funktion mit Inline-Assemblycode schreiben, ist es einfach, Argumente an die Funktion übergeben, und geben Sie einen Wert daraus zurück. Die folgenden Beispiele vergleichen, eine Funktion, die zuerst für einen getrennten Assembler geschrieben, und klicken Sie dann für den Inlineassembler umgeschrieben. Die Funktion `power2`, empfängt der zwei Parameter: den ersten Parameter mit 2, um die Leistungsfähigkeit des zweiten Parameters multipliziert. Für einen getrennten Assembler geschrieben wurden, kann die Funktion wie folgt aussehen:

```asm
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

Da es für einen getrennten Assembler geschrieben wird, erfordert die Funktion einen separaten Quellcodefenster-Datei und Assembly- und Verknüpfungsschritte. Argumente für C- und C++-Funktion in der Regel auf dem Stapel übergeben sind also diese Version von der `power2` Funktion greift auf die Argumente durch ihre Positionen im Stapel. (Beachten Sie, dass die **Modell** -Direktive in MASM und einige andere assemblern auch können Sie Stack Argumente und lokaler Stapelvariablen anhand Ihres Namens zugreifen.)

## <a name="example"></a>Beispiel

Dieses Programm schreibt die `power2` -Funktion mit Inline-Assemblycode:

```cpp
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

Die inlineversion der der `power2` Funktion bezieht sich auf die Argumente, anhand des Namens und wird in der gleichen Quelldatei wie der Rest des Programms angezeigt. Diese Version erfordert auch weniger Assemblyanweisungen.

Da die inlineversion der `power2` nicht ausgeführt, eine C `return` -Anweisung, bei der Kompilierung auf Warnstufe 2 oder höher wird eine Warnung harmlose. Die Funktion gibt einen Wert zurück, aber der Compiler nicht unterscheiden, die in Ermangelung einer `return` Anweisung. Sie können [#pragma-Warnung](../../preprocessor/warning.md) zum Deaktivieren der Generierung der diese Warnung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>