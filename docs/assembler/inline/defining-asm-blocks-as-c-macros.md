---
title: Definieren von __asm-Blöcken als C-Makros
ms.date: 08/30/2018
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
ms.openlocfilehash: c48298cf802600995dbbf68885896b6feccb807d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167025"
---
# <a name="defining-asm-blocks-as-c-macros"></a>Definieren von __asm-Blöcken als C-Makros

**Microsoft-spezifisch**

C-Makros bieten eine bequeme Möglichkeit, den Assemblycode in den Quellcode einfügen, aber sie fordern besonders sorgfältig vor, da ein Makro in eine einzelne logische Zeile erweitert. Um die problemlose Makros zu erstellen, folgen Sie diesen Regeln:

- Schließen Sie die `__asm` -block in geschweifte Klammern.

- Platzieren der `__asm` Schlüsselwort vor jede Assemblyanweisung.

- Verwenden der alten C-Kommentare ( `/* comment */`) anstelle von Assembly-Stil Kommentare ( `; comment`) oder eine einzeilige C-Kommentare ( `// comment`).

Um zu veranschaulichen, werden im folgenden Beispiel wird ein einfaches Makro definiert:

```cpp
#define PORTIO __asm      \
/* Port output */         \
{                         \
   __asm mov al, 2        \
   __asm mov dx, 0xD007   \
   __asm out dx, al       \
}
```

Auf die letzten drei ersten Blick `__asm` Schlüsselwörter überflüssig erscheinen. Sie sind jedoch erforderlich, da das Makro in einer einzelnen Zeile erweitert wird:

```cpp
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }
```

Der dritte und vierte `__asm` Schlüsselwörter als Trennzeichen für die Anweisung erforderlich sind. Die einzige Anweisung Trennzeichen erkannt `__asm` Blöcke sind die Zeilenumbruchzeichen und `__asm` Schlüsselwort. Da ein Block, der als Makro definiert eine logische Zeile ist, müssen Sie jede Anweisung mit trennen `__asm`.

Die Klammern sind ebenfalls wichtig. Wenn Sie sie weglassen, kann der Compiler von C- oder C++-Anweisungen in der gleichen Zeile rechts vom Makroaufruf verwechselt werden. Ohne die schließende Klammer gefunden, kann nicht dem Compiler mitzuteilen, wo Assemblycode beendet, und C- oder C++-Anweisungen angezeigt, nachdem die `__asm` Block als Assemblyanweisungen.

Assembly-Stil-Kommentare, beginnen mit einem Semikolon (**;**) bis zum Ende der Zeile fortgesetzt. Dies verursacht Probleme in Makros, da der Compiler alles, was nach dem Kommentar, ganz nach Ende der logischen Zeile ignoriert. Das gleiche gilt für einzeilige Kommentare für C- oder C++ ( `// comment`). Um Fehler zu vermeiden, verwenden Sie die alten C-Kommentare ( `/* comment */`) in `__asm` Blöcke, die als Makros definiert.

Ein `__asm` Block geschrieben, wie ein C-Makro Argumente annehmen kann. Im Gegensatz zu eines normale C-Makros, jedoch eine `__asm` Makro kann keinen Wert zurückgeben. Damit Sie diese Makros in C oder C++-Ausdrücken verwenden können.

Achten Sie darauf, dass Sie nicht wahllos Aufrufen der Makros dieses Typs. Beispielsweise deklariert eine Assemblysprache-Makro in einer Funktion aufrufen, mit der `__fastcall` Konvention kann zu unerwarteten Ergebnissen führen. (Finden Sie unter [verwenden und Beibehalten von Registern in der Inlineassembly](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>