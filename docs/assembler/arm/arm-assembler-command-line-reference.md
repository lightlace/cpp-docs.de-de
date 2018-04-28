---
title: Befehlszeilenreferenz des ARM-Assembler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f196b4aad76c72233c179249386dbb42960b31a6
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="arm-assembler-command-line-reference"></a>Befehlszeilenreferenz des ARM-Assemblers
Dieser Artikel enthält Befehlszeilen Informationen zu den Microsoft-ARM-Assembler *Armasm*, die kompiliert ARMv7 Thumb-Assemblysprache in die Microsoft-Implementierung des Common Object File Format (COFF). Der Linker kann COFF-Code mit Objektcode verknüpfen, das erzeugt wird, indem der ARM-Assembler oder der C-Compiler, zusammen mit der Objektbibliotheken, die durch den Bibliothekar erstellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### <a name="parameters"></a>Parameter  
 `options`  
 -Fehler `filename`  
 Umleiten von Fehler- und Warnmeldungen zu `filename`.  
  
 -i `dir[;dir]`  
 Die angegebenen Verzeichnisse zur Suche Includepfad hinzufügen.  
  
 -vordefinieren `directive`  
 Geben Sie eine Direktive SETEINE, SETL oder SETS vordefinieren ein Symbol. Beispiel: **armasm.exe-vordefinieren "COUNT SETEINE 150" source.asm**. Weitere Informationen finden Sie unter der [ARM Assembler Tools Guide](http://go.microsoft.com/fwlink/p/?linkid=246102).  
  
 -nowarn  
 Deaktivieren Sie alle Warnmeldungen.  
  
 -ignorieren `warning`  
 Deaktivieren Sie die angegebene Warnung. Mögliche Werte finden Sie im Abschnitt zu den Warnungen.  
  
 -Hilfe  
 Drucken Sie die Befehlszeilenhilfe-Nachricht.  
  
 -Computer `machine`  
 Geben Sie den Computer im PE-Header festgelegt.  Mögliche Werte für `machine` sind:  
**ARM**– legt den Computertyp auf IMAGE_FILE_MACHINE_ARMNT fest. Dies ist die Standardeinstellung.   
**THUMB**– legt den Computertyp auf IMAGE_FILE_MACHINE_THUMB fest.  
  
 -oldit  
 ARMv7-Stil generieren IT-Blöcken.  Standardmäßig ARMv8-kompatiblen IT-Blöcke werden generiert.  
  
 -über `filename`  
 Lesen zusätzliche Befehlszeilenargumente aus `filename`.  
  
 -16  
 Quelle als 16-Bit-Thumb-Anweisungen zu assemblieren.  Dies ist die Standardeinstellung.  
  
 -32  
 Quelle als 32-Bit-ARM-Instruktionen zu assemblieren.  
  
 -g  
 Debuginformationen zu generieren.  
  
 -ErrorReport: `option`  
 Geben Sie an, wie interne Assembler Fehler an Microsoft gemeldet werden.  Mögliche Werte für `option` sind:   
**keine**– keine Berichte senden.   
**Eingabeaufforderung**– der Benutzer aufgefordert, die Berichte sofort übertragen.   
**Warteschlange**– der Benutzer aufgefordert, die Berichte bei der nächsten administratoranmeldung zu senden. Dies ist die Standardeinstellung.   
**Senden von**– automatisch Berichte senden.  
  
 `sourcefile`  
 Der Name der Quelldatei.  
  
 `objectfile`  
 Der Name der Objektdatei (Ausgabe).  
  
 Im folgenden Beispiel wird veranschaulicht, wie Armasm in einem typischen Szenario verwendet wird. Verwenden Sie zuerst Armasm zum Erstellen einer Quelldatei Assemblysprache (ASM) eine Objektdatei (obj). Klicken Sie dann verwenden Sie der CL-Befehlszeilen-C-Compiler zum Kompilieren einer Quelldatei (c), und auch die Linkeroption zum Verknüpfen der ARM-Objektdatei.  
  
 **armasm myasmcode.asm -o myasmcode.obj**  
  
 **cl myccode.c /link myasmcode.obj**  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosemeldungen des ARM-Assembler](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM-Assemblyanweisungen](../../assembler/arm/arm-assembler-directives.md)