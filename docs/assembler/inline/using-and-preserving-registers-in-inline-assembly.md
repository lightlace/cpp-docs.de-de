---
title: Verwenden und Beibehalten von Registern in der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
ms.openlocfilehash: 30b2f9ca8c658b65819709bb2e536b5aaecad676
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166671"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Verwenden und Beibehalten von Registern in der Inlineassembly

**Microsoft-spezifisch**

Im Allgemeinen sollten Sie nicht davon ausgehen, dass ein Register einen bestimmten Wert hat bei einem `__asm` Block beginnt. Registerwerte werden nicht unbedingt auf separaten beibehalten werden `__asm` Blöcke. Wenn Sie einen Block von Inlinecode zu beenden und starten eine andere, können nicht Sie auf die Registern in der der zweite Block, deren Werte aus den ersten Block beizubehalten verlassen. Ein `__asm` Block erbt alle Werte, entstehen die normale ablaufsteuerung registrieren.

Bei Verwendung der `__fastcall` Aufrufkonvention, übergibt der Compiler Argumente der Funktion in Registern anstelle von auf dem Stapel. Dies kann Probleme verursachen, in Funktionen mit `__asm` blockiert, da eine Funktion keine Möglichkeit festzustellen weist, welche Parameter in der Registrierung ist. Wenn die Funktion geschieht, erhalten Sie einen Parameter in "eax" und sofort etwas anderes in EAX speichert, ist der ursprüngliche Parameter verloren gehen. Darüber hinaus müssen Sie das ECX-Register in jeder Funktion, die mit deklariert beibehalten `__fastcall`.

Um diese Register-Konflikte zu vermeiden, verwenden Sie nicht die `__fastcall` Konvention für Funktionen enthalten eine `__asm` Block. Bei Angabe der `__fastcall` Konvention, mit der Compileroption/GR, global deklariert jede Funktion, ein `__asm` -block mit `__cdecl` oder `__stdcall`. (Die `__cdecl` -Attribut weist den Compiler an der C-Aufrufkonvention für diese Funktion zu verwenden.) Wenn Sie nicht mit/GR kompilieren, vermeiden Sie die Deklaration der Funktion mit dem `__fastcall` Attribut.

Bei Verwendung `__asm` um Assemblysprache in C/C++-Funktionen zu schreiben, Sie müssen nicht die Register EAX, EBX, ECX, EDX, "ESI" oder EDI-beibehalten. Z. B. in der POWER2. C#-Beispiel in [Schreiben von Funktionen mit der Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md), `power2` Funktion nicht den Wert im Register "eax" beibehalten. Verwenden diese Register wirkt sich jedoch der Codequalität, da die Register-Zuweisung sie, zum Speichern von Werten über verwenden kann `__asm` Blöcke. Mithilfe EBX "," ESI "oder" EDI in Inline-Assemblycode, erzwingen Sie darüber hinaus den Compiler an, speichern und Wiederherstellen dieser Registern in der funktionsprolog und Epilog.

Sie sollten andere Register, die Sie (z.B. DS, SS, SP, BP und Flags-Register verwenden) beizubehalten, für den Bereich des der `__asm` Block. Sie sollten die ESP und im EBP-Registern beibehalten, es sei denn, Sie aus irgendeinem Grund ändern (um zur Verfügung, z. B. wechseln). Siehe auch [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md).

Einige SSE-Typen erfordern die Ausrichtung von 8-Byte-Stapel, der Compiler zum Ausgeben von dynamischen Stack Ausrichtung Code gezwungen wird. Um nach der die Ausrichtung sowohl die lokalen Variablen und Funktionsparameter zugreifen können, verwaltet der Compiler zwei Framezeiger.  Wenn der Compiler von Framezeigern (FPO) ausgeführt wird, wird als auch ESP EBP verwendet.  Wenn der Compiler nicht FPO durchgeführt wird, wird EBX und im EBP verwendet. Ändern Sie zur codeausführung einwandfrei zu funktionieren, EBX nicht im Asm-Code fest, wenn die Funktion dynamischem Stapel-Ausrichtung benötigt, wie sie die Frame-Pointer ändern kann. Verschieben Sie die 8-Byte-ausgerichteten Typen aus der Funktion, oder verwenden Sie keine EBX.

> [!NOTE]
>  Wenn sich Ihre Inline-Assemblycode das Richtungsflag mithilfe der Anweisungen STD oder CLD ändert, müssen Sie das Flag auf den ursprünglichen Wert wiederherstellen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>