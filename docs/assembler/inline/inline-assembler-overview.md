---
title: Übersicht über Inlineassembler
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembler
- __asm keyword [C++], invoking inline assembler
- invoking inline assembler
- inline assembly, inline assembler
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
ms.openlocfilehash: 21e0d9ca0e64922b83518eb79c19d2f2e67813bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543207"
---
# <a name="inline-assembler-overview"></a>Übersicht über Inlineassembler

**Microsoft-spezifisch**

Der Inlineassembler können Sie Assemblysprachanweisungen in Ihrem C- und C++-Quellprogramme ohne zusätzliche Assembly- und Verknüpfungsschritte einbetten. Der Inlineassembler ist im Compiler integriert, daher benötigen Sie keinen getrennten Assembler wie den Microsoft Macro Assembler (MASM).

Da der Inlineassembler keine separaten Assembly- und Verknüpfungsschritte erfordert, ist er einfacher als ein getrennter Assembler. Inline-Assemblycode können einen C- oder C++ Variablen- oder Funktionsname-Namen, der im Gültigkeitsbereich, daher ist es einfach, es mit C und C++-Code des Programms zu integrieren. Und da der Assemblycode mit C und C++-Anweisungen kombiniert werden kann, können sie Aufgaben, die mühsam oder unmöglich in C oder C++ allein sind ausführen.

Die [__asm](../../assembler/inline/asm.md) -Schlüsselwort ruft den Inlineassembler und können angezeigt werden, wo eine C- oder C++-Anweisung gültig ist. Es kann nicht allein stehen. Ihm muss eine Assemblyanweisung, eine Gruppe von Anweisungen, die in geschweifte Klammern eingeschlossen sind, oder zumindest ein leeres Paar geschweifter Klammern folgen. Der Begriff "`__asm`-Block" bezieht sich hier auf eine beliebige Anweisung bzw. Gruppe von Anweisungen, unabhängig davon, ob in geschweifte Klammern gesetzt oder nicht.

Der folgende Code zeigt eine einfache `__asm` Block in geschweifte Klammern eingeschlossen. (Der Code ist eine Prologsequenz für eine benutzerdefinierte Funktion).

```cpp
// asm_overview.cpp
// processor: x86
void __declspec(naked) main()
{
    // Naked functions must provide their own prolog...
    __asm {
        push ebp
        mov ebp, esp
        sub esp, __LOCAL_SIZE
    }

    // ... and epilog
    __asm {
        pop ebp
        ret
    }
}
```

Alternativ können Sie `__asm` vor jede Assemblyanweisung setzen:

```cpp
__asm push ebp
__asm mov  ebp, esp
__asm sub  esp, __LOCAL_SIZE
```

Da das `__asm`-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie die Assemblyanweisungen auch in die gleiche Zeile einfügen:

```cpp
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>