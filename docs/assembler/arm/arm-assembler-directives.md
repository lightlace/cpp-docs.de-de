---
title: "ARM Assembler Directives"
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
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Microsoft\-ARM\-Assembler verwendet zum größten Teil der ARM\-Assemblysprache, die in Kapitel 7 der dokumentiert ist die [ARM Assembler Tools Guide](http://go.microsoft.com/fwlink/?LinkId=246102).  Unterscheiden sich jedoch die Microsoft\-Implementierungen einiger Richtlinien Assembly ARM Assembly\-Direktiven.  Dieser Artikel erläutert die Unterschiede.  
  
## Microsoft\-Implementierungen von ARM Assembly\-Direktiven  
 BEREICH  
 Der Microsoft\-ARM\-Assembler unterstützt diesen Bereich Attribute: AUSZURICHTEN, CODE, CODEALIGN, Daten, NOINIT, READONLY, READWRITE DAUMEN, ARM.  
  
 Alle außer DAUMEN und ARM arbeiten wie dokumentiert die [ARM Assembler Tools Guide](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 In der Microsoft\-ARM\-Assembler zufolge DAUMEN ein Codeabschnitt Thumb\-Code enthält, und ist die Standardeinstellung für Codeabschnitte.  ARM gibt an, dass der Abschnitt ARM\-Code enthält.  
  
 ATTR  
 Wird nicht unterstützt.  
  
 CODE16  
 Nicht unterstützt, da sie Pre\-UAL Thumb\-Syntax, impliziert die Microsoft\-ARM\-Assembler nicht zulässt.  Verwenden Sie stattdessen die THUMB\-Richtlinie, zusammen mit UAL Syntax.  
  
 GEMEINSAME  
 Spezifikation der eine Ausrichtung für die gemeinsame Region wird nicht unterstützt.  
  
 DCDO  
 Wird nicht unterstützt.  
  
 DN, QN, SN  
 Angabe eines Typs oder einer Spur auf die Register\-Alias wird nicht unterstützt.  
  
 EINTRAG  
 Wird nicht unterstützt.  
  
 KANAL  
 Spezifikation eines Typs für das definierten Symbol wird nicht unterstützt.  
  
 Export\- und GLOBAL  
 ```  
  
EXPORTsym {[type]}  
  
```  
  
 `sym`ist das Symbol exportiert werden.  `[type]`, wenn angegeben, kann eine `[DATA]` an, dass das Symbol auf Daten zeigt oder `[FUNC]` an, dass das Symbol in Code verweist.  
  
 GLOBAL ist ein Synonym für den EXPORT.  
  
 EXPORTAS  
 Wird nicht unterstützt.  
  
 RAHMEN  
 Wird nicht unterstützt.  
  
 Funktion und PROC  
 Zwar Assembly\-Syntax die Angabe eines benutzerdefinierten unterstützt Aufrufkonvention für Prozeduren durch Auflisten der Register, die Anrufer speichern und die aufgerufene speichern, Microsoft\-ARM\-Assembler akzeptiert die Syntax ignoriert jedoch die Register\-Listen.  Die Debug\-Informationen, die vom Assembler erstellt wird, unterstützt nur die Standardaufrufkonvention.  
  
 IMPORT und EXTERN  
 ```  
  
IMPORT sym{, WEAK alias{, TYPE t}}  
  
```  
  
 `sym`ist der Name des Symbols importiert werden.  
  
 Wenn SCHWACH `alias` angegeben wird, bedeutet dies, dass `sym` ist eine schwache externe.  Wenn keine Definition dafür zur Verknüpfungszeit gefunden, wird stattdessen binden Sie alle Verweise darauf an `alias`.  
  
 Wenn TYPE  `t` angegeben ist, dann `t` gibt an, wie der Linker auflösen versuchen sollten `sym`.  Diese Werte für `t` sind möglich:   
1 – Führen Sie keine Bibliothek gesucht`sym`   
2 – Für die Bibliothek suchen`sym`   
3 —`sym` ist ein Alias für `alias` \(Standard\)  
  
 EXTERN ist ein Synonym für den IMPORT, außer dass `sym` wird nur dann, wenn die Verweise darauf in der aktuellen Assembly importiert.  
  
 MAKRO  
 Die Verwendung einer Variable für den Bedingungscode eines Makros wird nicht unterstützt.  Standardwerte für Makro Parameter werden nicht unterstützt.  
  
 NOFP  
 Wird nicht unterstützt.  
  
 OPT, TTL, SUBT  
 Nicht unterstützt, da der Microsoft\-ARM\-Assembler keine Angebote erzeugt werden.  
  
 PRESERVE8  
 Wird nicht unterstützt.  
  
 RELOC  
 `RELOC n`können nur eine Anweisung oder eine Daten\-Definition\-Direktive folgen.  Es gibt keine "anonyme Symbol", die verschoben werden kann.  
  
 ERFORDERN  
 Wird nicht unterstützt.  
  
 REQUIRE8  
 Wird nicht unterstützt.  
  
 THUMBX  
 Nicht unterstützt, da der Microsoft\-ARM\-Assembler keine Thumb\-2EE\-Befehlssatz unterstützt.  
  
## Siehe auch  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)