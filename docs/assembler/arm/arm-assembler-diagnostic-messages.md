---
title: Diagnosemeldungen des ARM-Assembler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54dca3a864ca34107314ad33725793297fd93e4a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="arm-assembler-diagnostic-messages"></a>Diagnosemeldungen des ARM-Assemblers
Der Microsoft-ARM-Assembler (*Armasm*) Diagnose Warnungen und Fehler ausgibt, wenn sie gefunden wird. Dieser Artikel beschreibt die Nachrichten häufig auftreten.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## <a name="diagnostic-messages"></a>Diagnosemeldungen  
  
### <a name="errors"></a>Fehler  
 A2193: Diese Anweisung wird zu einem unvorhersehbaren Verhalten generiert.  
 Die ARM-Architektur kann nicht garantieren, was geschieht, wenn diese Anweisung ausgeführt wird.  Weitere Informationen zu den fest definierten Formen der diese Anweisung, wenden Sie sich an den [ARM Architecture Reference Manual](http://go.microsoft.com/fwlink/p/?linkid=246464).  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: Anweisung kann nicht in den 16 Bits codiert werden  
 Die angegebene Anweisung kann nicht als 16-Bit-Thumb-Anweisung nicht codiert werden.  Geben Sie eine 32-Bit-Anweisung oder erneute Anordnen von Code aus, um die Ziel-Bezeichnung in den Bereich einer 16-Bit-Anweisung zu bringen.  
  
 Der Assembler versucht möglicherweise, codieren eine Verzweigung in 16 Bits lang sein und dieser Fehler auftreten, obwohl eine 32-Bit-Verzweigung Sicherheitsrichtlinienverwendung ist. Sie können dieses Problem beheben, indem Sie mit der `.W` Bezeichner, die als 32-Bit-Verzweigung explizit zu markieren.  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202: Pre-UAL-Anweisungssyntax in THUMB-Region unzulässig.  
 Thumb-Code muss die Unified-Assembler-Sprache (UAL)-Syntax verwenden.  Die alte Syntax wird nicht mehr akzeptiert.  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: Drehung muss gerade sein.  
 In ARM-Modus besteht eine alternative Syntax zum Angeben von Konstanten zur Verfügung.  Anstelle des Schreibens von `#<const>`, können Sie schreiben `#<byte>,#<rot>`, der den konstanten Wert an, die abgerufen werden, indem Sie den Wert drehen darstellt `<byte>` nach rechts um `<rot>`.  Wenn Sie diese Syntax verwenden, müssen Sie vergewissern, dass den Wert des `<rot>` selbst.  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: Falsche Anzahl von Bytes zum Zurückschreiben  
 Klicken Sie auf die NEON-Struktur laden und speichern Sie die Anweisungen (`VLDn`, `VSTn`), es ist eine alternative Syntax für das Rückschreiben von Daten in die Basisregister angeben.  Anstatt ein Ausrufezeichen (!) nach der Adresse einfügen, können Sie einen unmittelbaren nutzen angeben, der den Offset der Basisregister hinzuzufügende angibt.  Wenn Sie diese Syntax verwenden, müssen Sie die genaue Anzahl von Bytes angeben, die von der Anweisung gespeichert oder geladen wurden.  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### <a name="warnings"></a>Warnungen  
 A4228: Ausrichtungswert überschreitet Bereich Ausrichtung; Ausrichtung nicht garantiert.  
 Die Ausrichtung, die im angegebenen ein `ALIGN` Richtlinie ist größer als die Ausrichtung des einschließenden `AREA`.  Daher der Assembler nicht garantieren, dass die `ALIGN` Richtlinie berücksichtigt.  
  
 Um dieses Problem zu beheben, können Sie auf angeben, die `AREA` Richtlinie eine `ALIGN` -Attribut, das die gewünschte Ausrichtung größer oder gleich ist.  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508: Mithilfe dieser gedreht Konstante ist veraltet.  
 In ARM-Modus besteht eine alternative Syntax zum Angeben von Konstanten zur Verfügung.  Anstelle des Schreibens von `#<const>`, können Sie schreiben `#<byte>,#<rot>`, der den konstanten Wert an, die abgerufen werden, indem Sie den Wert drehen darstellt `<byte>` nach rechts um `<rot>`.  In einigen Kontexten wurde die Verwendung der folgenden Konstanten gedreht von ARM als veraltet. Verwenden Sie in diesen Fällen ist die grundlegende `#<const>` Syntax stattdessen.  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509: Diese Form der bedingten Anweisung ist veraltet.  
 Diese Form der bedingten Anweisung wurde vom ARM in der Architektur ARMv8 als veraltet markiert. Es wird empfohlen, dass Sie den Code, um bedingte Verzweigungen verwenden ändern. Um festzustellen, welche bedingten Anweisungen weiterhin unterstützt werden, finden Sie in der [ARM Architecture Reference Manual](http://go.microsoft.com/fwlink/p/?linkid=246464).  
  
 Diese Warnung wird nicht ausgegeben, wenn die `-oldit` Befehlszeilenoption verwendet wird.  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlszeilenreferenz des ARM-Assembler](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM-Assemblyanweisungen](../../assembler/arm/arm-assembler-directives.md)