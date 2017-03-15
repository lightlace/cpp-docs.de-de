---
title: "Definieren von __asm-Bl&#246;cken als C-Makros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], Als C-Makros"
  - "Makros, __asm-Blöcke"
  - "Visual C, Makros"
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Definieren von __asm-Bl&#246;cken als C-Makros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 C\-Makros bieten eine einfache Möglichkeit, Assemblycode in den Quellcode einfügen, jedoch zusätzliche fordern Sorgfalt, da ein Makro in eine einzelne logische Zeile erstreckt.  Um störungsfreie Makros zu erstellen, führen Sie die folgenden Regeln:  
  
-   Schließen Sie den `__asm`\-Block in geschweifte Klammern ein.  
  
-   Legen Sie das `__asm`\-Schlüsselwort vor jeder Assemblyanweisung.  
  
-   Verwenden Sie alte C\-Kommentare \( `/* comment */`ASSEMBLY \(Kommentare Format\) anstelle `; comment`\) oder einzeiliger C\-Kommentare \( `// comment`\).  
  
 Um zu veranschaulichen, wird ein einfaches folgenden Beispiel wird das Makro:  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 Auf den ersten Blick scheinen die letzten drei `__asm` Schlüsselwörter überflüssig.  Sie werden jedoch, erfordert da das Makro in eine einzelne Zeile erweitert:  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 In der dritten und vierten `__asm` Schlüsselwörter werden als Anweisungstext Trennzeichen erforderlich ist.  Die einzigen Anweisung als Trennzeichen, die in `__asm` Blöcke erkannt werden, sind das Zeilenumbruchzeichen und das `__asm`\-Schlüsselwort.  Da ein Block, der als Makro definiert wurde, eine logische Zeile befindet, müssen Sie jede Anweisung mit `__asm`trennen.  
  
 Die Klammern sind auch Voraussetzung.  Wenn Sie ihn weglassen, kann der Compiler von C\# oder C\+\+\-Anweisungen in derselben Zeile auf der rechten Seite des Makros rufen verwirrt werden.  Ohne die schließende Klammer kann der Compiler nicht erkennen, wo Assemblycode und hält er C\# oder C\+\+\-Anweisungen nachdem der `__asm`\-Block als Assemblyanweisungen anzuzeigen.  
  
 ASSEMBLY\-Format Kommentare, die mit einem Semikolon \(**;**\) beginnen werden am Ende der Zeile fortgesetzt.  Auf diese Weise werden Probleme in Makros, da der Compiler alle nach dem Kommentar ignoriert, bis zum Ende der logischen Zeile.  Dies gilt auch von einzeiligen C\# oder C\+\+\-Kommentaren \( `// comment`\).  Um Fehler zu vermeiden, verwenden Sie alte C\-Kommentare \( `/* comment */`\) in `__asm` Blöcke, die als Makros definiert sind.  
  
 Ein `__asm`\-Block, der als Wechselstrom\-Makro geschrieben wird, kann Argumente akzeptieren.  Im Gegensatz zu C\-Makro ein normales kann jedoch ein `__asm` Makro keinen Wert zurückgeben.  So können Sie diese Makros in C\# oder C\+\+\-Ausdrücken nicht verwenden.  
  
 Achten Sie darauf, dass Sie keine Makros dieses Typs wahllos aufrufen.  Zum Beispiel kann das Aufrufen eines Assemblersprachen Sie Makros in einer Funktion, die mit der `__fastcall` Konvention deklarierte zu unerwarteten Ergebnissen führen.  \(Siehe [Anwendungs\- und Register in der Inlineassembly Argumenten beibehalten](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)\).  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)