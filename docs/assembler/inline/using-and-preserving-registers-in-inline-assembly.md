---
title: Verwenden und Beibehalten von Registern in der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a5db1c9c4facd51b2886d93017ad87a0683b899
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Verwenden und Beibehalten von Registern in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Im Allgemeinen sollten Sie nicht davon ausgehen, dass einen bestimmten Wert ein Registers haben bei einem `__asm` Block beginnt. Registerwerte sind nicht unbedingt über Separate beibehalten werden `__asm` blockiert. Wenn Sie einen Block von Inlinecode zu beenden und starten eine andere, können nicht Sie auf die für den zweiten Block, behalten ihre Werte aus den ersten Block-Register verlassen. Ein `__asm` Block erbt alle von Ihnen gewünschten Werte Ergebnis aus dem normalen Fluss des Steuerelements registrieren.  
  
 Bei Verwendung der `__fastcall` -Aufrufkonvention, übergibt der Compiler Funktionsargumente in Registern anstelle von auf dem Stapel. Dies kann Probleme verursachen, in Funktionen mit `__asm` blockiert, da eine Funktion keine Möglichkeit festzustellen weist, welche Parameter in der Registrierung ist. Wenn die Funktion geschieht, um einen Parameter in EAX zu erhalten und sofort etwas in EAX speichert, ist der ursprünglichen Parameter verloren. Darüber hinaus müssen Sie das ECX-Register in jeder Funktion deklariert mit beibehalten `__fastcall`.  
  
 Um solche Register-Konflikte zu vermeiden, verwenden Sie nicht die `__fastcall` Konvention für Funktionen enthalten eine `__asm` Block. Bei Angabe der `__fastcall` Konvention Global mit der Compileroption/GR, deklarieren Sie jede Funktion, ein `__asm` -block mit `__cdecl` oder `__stdcall`. (Die `__cdecl` Attribut teilt dem Compiler mit der C-Aufrufkonvention für diese Funktion zu verwenden.) Wenn Sie nicht mit/GR kompilieren, zu vermeiden, deklarieren die Funktion mit dem `__fastcall` Attribut.  
  
 Bei Verwendung `__asm` um Assemblysprache in C/C++-Funktionen zu schreiben, müssen Sie nicht die Register EAX, EBX, ECX, EDX, ESI oder EDI-beibehalten. Beispielsweise ist in der POWER2. C#-Beispiel in [Schreiben von Funktionen mit der Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md)die `power2` Funktion nicht den Wert in EAX-Register beibehalten. Verwenden diese Register wirkt sich jedoch der Codequalität, da die Zuweisung registrieren sie, zum Speichern von Werten verwenden kann `__asm` blockiert. Darüber hinaus zwingen mithilfe EBX, ESI oder EDI in Inline-Assemblycode, den Compiler, speichern und diese Registern in der funktionsprolog und Epilog wiederherstellen.  
  
 Sie sollten andere Register, die Sie (z. B. DS, SS SP, BP und Flags Register verwenden) beibehalten, für den Bereich des der `__asm` Block. Sie sollten die ESP und im EBP-Register beibehalten, es sei denn, Sie aus irgendeinem Grund (um z. B. Stapel, wechseln Sie) geändert haben. Siehe auch [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md).  
  
 Einige SSE-Typen erfordern Ausrichtung von 8-Byte-Stapel, der Compiler zum Ausgeben von dynamischen Stapel-Ausrichtung Code gezwungen wird. Um die lokalen Variablen und Parameter der Funktion nach der die Ausrichtung auf zugreifen zu können, verwaltet der Compiler zwei Framezeiger.  Wenn der Compiler Frame Zeiger Auslassung (FPO) ausführt, wird als auch ESP EBP verwendet.  Wenn der Compiler keine FPO ausführt, wird EBX und im EBP verwendet. Um sicherzustellen, dass Code ändern ausgeführt wird ordnungsgemäß, Sie nicht EBX Asm-Code, wenn die Funktion dynamischer Stapel-Ausrichtung benötigt, wie die Frame-Pointer geändert werden kann. Verschieben Sie die Typen der 8-Byte-ausgerichteten Rücksprung aus der Funktion oder zu vermeiden Sie, EBX verwenden.  
  
> [!NOTE]
>  Wenn die Inline-Assemblycode das Richtungsflag mithilfe der Anweisungen STD oder CLD ändert, müssen Sie das Flag auf den ursprünglichen Wert wiederherstellen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)