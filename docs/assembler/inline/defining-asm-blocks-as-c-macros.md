---
title: "Definieren von __asm-Blöcken als C-Makros | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af95f7b2c74d797203a0e6b3ddd6a92ddcb51e5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="defining-asm-blocks-as-c-macros"></a>Definieren von __asm-Blöcken als C-Makros
**Microsoft-spezifisch**  
  
 C-Makros bieten eine einfache Möglichkeit, den Assemblycode in Ihren Quellcode einfügen, aber sie fordern Vorsicht, da ein Makro zu einer einzigen logischen Zeile erweitert. Um problemlose Makros zu erstellen, die entsprechen Sie diesen Regeln:  
  
-   Schließen Sie die `__asm` -block in der geschweiften Klammern.  
  
-   Versetzen der `__asm` Schlüsselwort vor jede Assemblyanweisung.  
  
-   C-Kommentare im alten Stil verwenden ( `/* comment */`) anstelle von Assembly-Stil Kommentare ( `; comment`) oder ein einzeiliger C-Kommentare ( `// comment`).  
  
 Im folgenden Beispiel definiert ein einfaches Makro, um zu veranschaulichen:  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 Auf die letzten beiden ersten Blick `__asm` Schlüsselwörter überflüssig erscheinen. Sie sind jedoch benötigt, da das Makro zu einer einzigen Zeile erweitert:  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 Der dritte und vierte `__asm` Schlüsselwörter als Anweisung Trennzeichen erforderlich sind. Die einzige Anweisung Trennzeichen erkannt `__asm` Blöcke sind die Zeilenumbruchzeichen und `__asm` Schlüsselwort. Da ein Block, der als Makro definiert eine logische Zeile ist, müssen Sie jede Anweisung mit trennen `__asm`.  
  
 Die Klammern sind ebenfalls wichtig. Wenn Sie sie weglassen, kann der Compiler von C- oder C++-Anweisungen in derselben Zeile auf der rechten Seite des Makroaufruf verwechselt werden. Ohne die schließende Klammer gefunden, kann nicht den Compiler aufzufordern, wo Assemblycode beendet, und es sieht C- oder C++-Anweisungen nach der `__asm` Block als Assemblyanweisungen.  
  
 Assembly-Stil-Kommentare, die mit einem Semikolon beginnen (**;**) bis zum Ende der Zeile fortgesetzt. Dies verursacht Probleme in Makros, da der Compiler alles nach dem Kommentar, ganz nach Ende der logischen Zeile ignoriert. Dasselbe gilt für einzeilige Kommentare für C- oder C++ ( `// comment`). Um Fehler zu vermeiden, verwenden Sie im alten Stil C-Kommentare ( `/* comment */`) in `__asm` Blöcke, die als "Makros" definiert.  
  
 Ein `__asm` Block geschrieben, wie ein C#-Makro Argumente annehmen kann. Im Gegensatz zu einer normalen C#-Makro, jedoch ein `__asm` Makro kann keinen Wert zurückgeben. Damit Sie diese Makros in C oder C++-Ausdrücken verwenden können.  
  
 Achten Sie darauf, keine Makros dieses Typs wahllos aufrufen. Z. B. deklariert eine Assemblersprache Makro in eine Funktion aufrufen, wobei die `__fastcall` Konvention kann zu unerwarteten Ergebnissen führen. (Siehe [verwenden und Beibehalten von Registern in der Inlineassembly](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).)  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)