---
title: Diagnosemeldungen des ARM-Assemblers
ms.date: 08/30/2018
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
ms.openlocfilehash: 867ef50065c6ed63a4da6d37523bd5a1f3cbadba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601681"
---
# <a name="arm-assembler-diagnostic-messages"></a>Diagnosemeldungen des ARM-Assemblers

Der Microsoft-ARM-Assembler (*Armasm*) diagnostische Warnungen und Fehler ausgibt, wenn sie gefunden wird. Dieser Artikel beschreibt die am häufigsten auftretenden Nachrichten.

## <a name="syntax"></a>Syntax

> <em>FileName</em>**(**<em>Zeilennummer</em>**):** \[ **Fehler**|**Warnung** ] **Ein**<em>Anzahl</em>**:** *Nachricht*

## <a name="diagnostic-messages---errors"></a>Diagnosemeldungen - Fehler

> A2193: Diese Anweisung wird zu einem unvorhersehbaren Verhalten generiert.

Die ARM-Architektur garantiert nicht, was geschieht, wenn diese Anweisung ausgeführt wird.  Weitere Informationen zu den klar definierten Formen der diese Anweisung finden Sie in der [ARM Architecture Reference Manual](http://go.microsoft.com/fwlink/p/?linkid=246464).

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: Anweisung kann nicht codiert werden in 16-Bit

Die angegebene Anweisung kann nicht als eine 16-Bit-Thumb-Anweisung nicht codiert werden.  Geben Sie eine 32-Bit-Anweisung, oder Neuanordnen von Code zum Zielbezeichner, die in den Wertebereich einer 16-Bit-Anweisung zu bringen.

Der Assembler versucht möglicherweise, codieren einen Branch im 16 Bits aus, und dieser Fehler auftreten, auch wenn ein 32-Bit-Branch Sicherheitsrichtlinienverwendung ist. Sie können dieses Problem beheben, indem Sie mit der `.W` Spezifizierer, um den Branch als 32-Bit-explizit zu markieren.

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: Pre-UAL-Anweisungssyntax in der Region des Thumb-Steuerelement nicht zulässig

Thumb-Code muss die Unified-Assembler-Sprache (UAL)-Syntax verwenden.  Die alte Syntax wird nicht mehr akzeptiert.

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: Drehung muss gerade sein.

Im Modus "ARM" besteht eine alternative Syntax zum Angeben von Konstanten zur Verfügung.  Anstelle des Schreibens von `#<const>`, können Sie schreiben `#<byte>,#<rot>`, steht für den konstanten Wert an, die abgerufen werden, indem Sie den Wert Drehen `<byte>` nach rechts `<rot>`.  Wenn Sie diese Syntax verwenden, müssen Sie den Wert des, `<rot>` selbst.

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: Falsche Anzahl von Bytes zum Zurückschreiben

Klicken Sie auf die NEON-Struktur laden, und speichern Sie die Anweisungen (`VLDn`, `VSTn`), es ist eine alternative Syntax für das Rückschreiben von Daten in die Basisregister angeben.  Anstelle ein Ausrufezeichen (!) nach der Adresse zu verwenden, können Sie einen unmittelbaren Wert angeben, der den Offset der Basisregister hinzuzufügende angibt.  Wenn Sie diese Syntax verwenden, müssen Sie die genaue Anzahl von Bytes angeben, die geladen oder gespeichert, die von dieser Anweisung waren.

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>Diagnosemeldungen - Warnungen

> A4228: Ausrichtungswert überschreitet Bereich Ausrichtung; Ausrichtung, die nicht garantiert.

Die Ausrichtung, die im angegebenen ein `ALIGN` -Direktive ist größer als die Ausrichtung des einschließenden `AREA`.  Daher der Assembler kann nicht garantieren, dass die `ALIGN` Richtlinie berücksichtigt.

Um dieses Problem zu beheben, geben Sie auf die `AREA` Richtlinie eine `ALIGN` -Attribut, das die gewünschte Ausrichtung größer oder gleich ist.

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: Mithilfe dieser gedrehte Konstante ist veraltet.

Im Modus "ARM" besteht eine alternative Syntax zum Angeben von Konstanten zur Verfügung.  Anstelle des Schreibens von `#<const>`, können Sie schreiben `#<byte>,#<rot>`, steht für den konstanten Wert an, die abgerufen werden, indem Sie den Wert Drehen `<byte>` nach rechts `<rot>`.  In einigen Kontexten wurde die Verwendung dieser gedrehte Konstanten von ARM als veraltet. In diesen Fällen verwenden Sie die einfache `#<const>` Syntax stattdessen.

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: Diese Form der bedingten Anweisung ist veraltet.

Diese Form der bedingten Anweisung wurde als veraltet markiert, indem ARM in der ARMv8-Architektur. Es wird empfohlen, den Code, um die bedingte Verzweigungen zu ändern. Um anzuzeigen, welche bedingten Anweisungen weiterhin unterstützt werden, finden Sie in der [ARM Architecture Reference Manual](http://go.microsoft.com/fwlink/p/?linkid=246464).

Diese Warnung wird nicht ausgegeben, wenn die **- Oldit** Befehlszeilenschalter wird verwendet.

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>Siehe auch

[Befehlszeilenverweis des ARM-Assemblers](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM-Assemblyanweisungen](../../assembler/arm/arm-assembler-directives.md)<br/>
