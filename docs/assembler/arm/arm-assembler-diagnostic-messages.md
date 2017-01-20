---
title: "ARM Assembler Diagnostic Messages"
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
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Diagnostic Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Microsoft\-ARM\-Assembler \(*Armasm*\) Diagnose Warnungen und Fehler ausgibt, wenn diese auftreten.  Dieser Artikel beschreibt die Nachrichten häufig auftreten.  
  
## Syntax  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## Diagnosemeldungen  
  
### Fehler  
 A2193: Diese Anweisung generiert unvorhersehbares Verhalten  
 ARM\-Architektur kann nicht dafür garantieren, was passiert, wenn diese Anweisung ausgeführt wird.  Informationen über die klar definierten Formen dieser Anweisung finden Sie in der [ARM Architektur Referenzhandbuch](http://go.microsoft.com/fwlink/?LinkId=246464).  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: Anweisung nicht in 16 Bits codiert sein  
 Die angegebene Anweisung nicht als eine 16\-Bit\-Thumb\-Anweisung nicht codiert sein.  Geben Sie eine 32\-Bit\-Anweisung an, oder neu ordnen Sie Code die Zielmarke in den Bereich einer 16\-Bit\-Anweisung zu bringen an.  
  
 Der Assembler versucht möglicherweise, eine Niederlassung in 16 Bits codiert und mit diesem Fehler fehlschlagen, obwohl eine 32\-Bit\-Verzweigung ermöglichen ist.  Sie können dieses Problem beheben, indem Sie mit der `.W` Bezeichner, um den Zweig als 32\-Bit explizit kennzeichnen.  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202: Pre\-UAL\-Anweisungssyntax in DAUMEN Region unzulässig.  
 Thumb\-Code muss die Unified\-Assembler\-Sprache \(UAL\)\-Syntax verwenden.  Die alte Syntax wird nicht mehr akzeptiert.  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: Die Drehung muss gerade sein.  
 Im ARM\-Modus gibt es eine alternative Syntax für das Angeben von Konstanten.  Anstelle von `#<const>`, können Sie schreiben `#<byte>,#<rot>`, die darstellt, des konstanten Wertes, der durch Drehen des Werts `<byte>` direkt `<rot>`.  Wenn Sie diese Syntax verwenden, müssen Sie den Wert der `<rot>` selbst.  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: Falsche Anzahl von Bytes zurück schreiben  
 Klicken Sie auf die NEON\-Struktur laden und Speichern von Anweisungen \(`VLDn`, `VSTn`\), gibt es eine alternative Syntax für das Rückschreiben in die Basisregister angeben.  Anstatt ein Ausrufezeichen \(\!\) nach der Adresse zu verwenden, können Sie einen sofortigen Wert angeben, der angibt, den Offset der Basisregister hinzugefügt werden.  Wenn Sie diese Syntax verwenden, müssen Sie die genaue Anzahl der Bytes angeben, die geladen oder von der Anweisung gespeichert wurden.  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### Warnungen  
 A4228: Der Ausrichtungswert überschreitet Bereich Ausrichtung; Ausrichtung nicht garantiert  
 Die Ausrichtung, die in einer `ALIGN` Richtlinie ist größer als die Ausrichtung des umgebenden `AREA`.  Als Folge der Assembler nicht garantieren, dass die `ALIGN` Richtlinie wird berücksichtigt.  
  
 Um dieses Problem zu beheben, können Sie festlegen, auf die `AREA` Richtlinie ein `ALIGN` \-Attribut, das gleich oder größer als die gewünschte Ausrichtung.  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508: Verwendung dieser gedrehte Konstante ist veraltet.  
 Im ARM\-Modus gibt es eine alternative Syntax für das Angeben von Konstanten.  Anstelle von `#<const>`, können Sie schreiben `#<byte>,#<rot>`, die darstellt, des konstanten Wertes, der durch Drehen des Werts `<byte>` direkt `<rot>`.  In einigen Kontexten hat ARM die Verwendung der folgenden gedrehten veraltet.  In diesen Fällen verwenden Sie die grundlegenden `#<const>` Syntax statt.  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509: Diese Form der bedingten Anweisung ist veraltet.  
 Diese Form der bedingten Anweisung wurde als veraltet markiert, ARM in der ARMv8\-Architektur.  Wir empfehlen, den Code, bedingte Verzweigungen zu ändern.  Sehen die bedingten Anweisungen noch unterstützt werden, finden Sie in der [ARM Architektur Referenzhandbuch](http://go.microsoft.com/fwlink/?LinkId=246464).  
  
 Diese Warnung wird nicht ausgegeben, wenn die  `- Oldit` Befehlszeilenoption verwendet wird.  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## Siehe auch  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)