---
title: "ARM Assembler Command-Line Reference | Microsoft Docs"
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
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# ARM Assembler Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel enthält Angaben über die Microsoft\-ARM\-Assembler in der Befehlszeile  *Armasm*, die ARMv7\-Thumb\-Assemblysprache kompiliert, in der Microsoft\-Implementierung von der COFF Common Object File Format \(\).  Der Linker kann COFF\-Code, mit dem Objektcode verknüpfen, die produziert wird, durch den ARM\-Assembler oder C\-Compiler, zusammen mit Objektbibliotheken, die durch den Bibliothekar erstellt werden.  
  
## Syntax  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### Parameter  
 `options`  
 \-Fehler`filename`  
 Umleiten von Fehler\- und Warnmeldungen, `filename`.  
  
 \-i`dir[;dir]`  
 Fügen Sie die angegebenen Verzeichnisse zu Include\-Suchpfad.  
  
 \-vordefinieren`directive`  
 Geben Sie eine Richtlinie SETA, SETL oder Sätze ein Symbol vordefinieren.  Beispiel: **armasm.exe \-predefine "COUNT SETA 150" source.asm** Weitere Informationen finden Sie unter der [ARM Assembler Tools Guide](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 Nowarn\-  
 Deaktivieren Sie alle Warnmeldungen.  
  
 \-ignorieren`warning`  
 Die angegebene Warnung zu deaktivieren.  Mögliche Werte finden Sie im Abschnitt über Warnungen.  
  
 \-Hilfe  
 Drucken Sie die Befehlszeilenhilfe angezeigt.  
  
 \-Maschine`machine`  
 Geben Sie den Computer im PE\-Header festlegen.  Mögliche Werte für `machine` sind:   
**ARM**– Legt den Computertyp zu IMAGE\_FILE\_MACHINE\_ARMNT.  Dies ist die Standardeinstellung.   
**THUMB**– Legt den Computertyp zu IMAGE\_FILE\_MACHINE\_THUMB.  
  
 \-oldit  
 ARMv7\-Stil generieren IT\-Blöcke.  In der Standardeinstellung ARMv8\-kompatible IT\-Blöcke werden generiert.  
  
 \-über`filename`  
 Lesen zusätzliche Befehlszeilenargumente von `filename`.  
  
 \-16  
 Bauen Sie die Quelle als 16\-Bit\-Thumb\-Anweisungen.  Dies ist die Standardeinstellung.  
  
 \-32  
 Bauen Sie die Quelle als 32\-Bit\-ARM\-Anweisungen.  
  
 \-g  
 Debuginformationen generiert.  
  
 \-ErrorReport:`option`  
 Geben Sie wie interne Assembler Fehler an Microsoft gemeldet werden.  Mögliche Werte für `option` sind:   
**none**— Senden Sie keine Berichte.   
**prompt**— Der Benutzer aufgefordert, umgehend Berichten.   
**queue**— Fordert den Benutzer zum Senden von Berichten bei der nächsten Administratoranmeldung von.  Dies ist die Standardeinstellung.   
**send**— Senden Sie Berichte automatisch.  
  
 `sourcefile`  
 Der Name der Quelldatei.  
  
 `objectfile`  
 Der Name der Objektdatei \(Output\).  
  
 Im folgenden Beispiel wird veranschaulicht, wie mithilfe von Armasm in einem typischen Szenario.  Verwenden Sie zuerst Armasm, um eine Assembly Language\-Quelldatei \(ASM\) in eine Objektdatei \(.obj\) erstellen.  Dann verwenden Sie die CL\-Befehlszeile C\-Compiler zum Kompilieren einer Quelldatei \(c\), und auch Geben Sie die Linker\-Option zum Verknüpfen der ARM\-Objekt\-Datei an.  
  
 **armasm myasmcode.asm \-o myasmcode.obj**  
  
 **cl myccode.c \/link myasmcode.obj**  
  
## Siehe auch  
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)