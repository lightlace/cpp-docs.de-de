---
title: Springen zu Bezeichnungen in der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
ms.openlocfilehash: 7653dc990e2f4b490bcbe333ed6f7586ac966d2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166905"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>Springen zu Bezeichnungen in der Inlineassembly

**Microsoft-spezifisch**

Wie eine normale C oder C++ Bezeichnung und eine Bezeichnung in einem `__asm` -Block ist der Gültigkeitsbereich der Funktion, die in der sie (nicht nur im Block definiert ist). Beide Assemblyanweisungen und `goto` Anweisungen können springen zu Bezeichnungen innerhalb oder außerhalb der `__asm` Block.

Bezeichnungen `__asm` Blöcke sind nicht in der Groß-/Kleinschreibung beachtet; `goto` Anweisungen und Assemblyanweisungen können auf diese Bezeichnungen ohne Berücksichtigung verweisen. C- und C++-Bezeichnungen sind Groß-/ Kleinschreibung erst bei durch `goto` Anweisungen. Assemblyanweisungen können in eine Bezeichnung für C- oder C++ ohne Berücksichtigung springen.

Der folgende Code zeigt alle Strukturvarianten:

```cpp
void func( void )
{
   goto C_Dest;  /* Legal: correct case   */
   goto c_dest;  /* Error: incorrect case */

   goto A_Dest;  /* Legal: correct case   */
   goto a_dest;  /* Legal: incorrect case */

   __asm
   {
      jmp C_Dest ; Legal: correct case
      jmp c_dest ; Legal: incorrect case

      jmp A_Dest ; Legal: correct case
      jmp a_dest ; Legal: incorrect case

      a_dest:    ; __asm label
   }

   C_Dest:       /* C label */
   return;
}
int main()
{
}
```

Verwenden Sie nicht als Bezeichnungen in der C-Bibliothek-Funktionsnamen `__asm` Blöcke. Versucht, verwenden Sie z. B. möglicherweise `exit` als eine Bezeichnung wie folgt:

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

Da **beenden** ist der Name einer C-Bibliothek-Funktion, dieser Code kann dazu führen, dass einen Sprung zu den **beenden** -Funktion anstelle von an die gewünschte Position.

Wie bei den MASM-Programme, Dollarsymbols (`$`) dient als den aktuellen Speicherort Leistungsindikator. Es ist eine Bezeichnung für die Anweisung, die gerade zusammengesetzt wird. In `__asm` Blöcke sein Hauptverwendungszweck ist es, lange bedingte Sprüngen:

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>