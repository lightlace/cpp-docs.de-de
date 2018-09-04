---
title: ARM-Assemblyanweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 282d8bbd55bec8053961c709eb3733a65972b187
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693112"
---
# <a name="arm-assembler-directives"></a>ARM-Assemblyanweisungen

Der Microsoft-ARM-Assembler verwendet zum größten Teil der ARM-Assemblysprache, die in dokumentiert wird die [ARM Compiler Armasm Referenzhandbuch](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html). Allerdings unterscheiden sich die Microsoft-Implementierungen einiger Direktiven für die Assembly, von der ARM-Assemblyanweisungen zu erhalten. In diesem Artikel erläutert die Unterschiede.

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>Microsoft-Implementierungen von ARM-Assemblyanweisungen

`AREA`<br/>
Der Microsoft-ARM-Assembler unterstützt die folgenden `AREA` Attribute: `ALIGN`, `CODE`, `CODEALIGN`, `DATA`, `NOINIT`, `READONLY`, `READWRITE`, `THUMB`, `ARM`.

Alle außer `THUMB` und `ARM` funktioniert wie in der dokumentiert die [ARM Compiler Armasm Referenzhandbuch](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

In der Microsoft-ARM-Assembler `THUMB` gibt an, dass eine `CODE` Abschnitt Thumb-Code enthält, und ist die Standardeinstellung für `CODE` Abschnitte.  `ARM` Gibt an, dass im Abschnitt über ARM-Code enthält.

`ATTR`<br/>
Wird nicht unterstützt.

`CODE16`<br/>
Nicht unterstützt, da impliziert Pre-UAL-Thumb-Syntax, die der Microsoft-ARM-Assembler nicht zulässt.  Verwenden der `THUMB` stattdessen zusammen mit der Syntax für die Benutzerzugriffsprotokollierung die Richtlinie.

`COMMON`<br/>
Eine Ausrichtung für den allgemeinen Bereich wird nicht unterstützt.

`DCDO`<br/>
Wird nicht unterstützt.

`DN`, `QN`, `SN`<br/>
Die Spezifikation eines Typs oder einen Bereich auf den Register-Alias wird nicht unterstützt.

`ENTRY`<br/>
Wird nicht unterstützt.

`EQU`<br/>
Die Spezifikation eines Typs für die definiertes Symbol wird nicht unterstützt.

`EXPORT` und `GLOBAL`

> **EXPORTIEREN Sie** <em>Sym</em>{**[**<em>Typ</em>**]**}

*SYM* ist das Symbol für die exportiert werden.  [*Typ*], sofern angegeben, kann es sich um `[DATA]` , um anzugeben, dass das Symbol auf Daten verweist oder `[FUNC]` , um anzugeben, dass das Symbol auf Code verweist.

`GLOBAL` ist ein Synonym für `EXPORT`.

`EXPORTAS`<br/>
Wird nicht unterstützt.

`FRAME`<br/>
Wird nicht unterstützt.

`FUNCTION` und `PROC`<br/>
Obwohl die Assembly-Syntax die Angabe eines benutzerdefinierten unterstützt Aufrufkonvention für Prozeduren durch die Register, die Aufrufer-speichern und die aufgerufenen speichern, Auflisten der Microsoft-ARM-Assembler die Syntax akzeptiert ignoriert jedoch die Register-Listen.  Die Debuginformationen, die von der Assembler erstellt wird, unterstützt nur die Standardaufrufkonvention.

`IMPORT` und `EXTERN`

> **IMPORT** *Sym*{**, SCHWACHE** *Alias*{**, Typ** *t*}}

*SYM* ist der Name des Symbols, das importiert werden.

Wenn `WEAK` *Alias* angegeben ist, bedeutet dies, dass *Sym* eine schwache externe Adresse ist. Wenn zum Zeitpunkt der Verknüpfung keine Definition gefunden wird, alle Verweise darauf binden Sie stattdessen an *Alias*.

Wenn `TYPE` *t* angegeben ist, klicken Sie dann *t* gibt an, wie der Linker zum Auflösen versuchen *Sym*.  Diese Werte für *t* sind möglich:<br/>
1 – Führen Sie eine Bibliothek Suche nach nicht *Sym*<br/>
2 – führen Sie eine Bibliothek Suche nach *Sym*<br/>
3 –*Sym* ist ein Alias für *Alias* (Standard)

`EXTERN` ist ein Synonym für `IMPORT`, außer dass *Sym* ist nur importiert, wenn Verweise darauf in der aktuellen Assembly vorhanden sind.

`MACRO`<br/>
Die Verwendung von eine Variable für den Code der Bedingung eines Makros wird nicht unterstützt. Standardwerte für die Makro-Parameter werden nicht unterstützt.

`NOFP`<br/>
Wird nicht unterstützt.

`OPT`, `TTL`, `SUBT`<br/>
Nicht unterstützt, da der Microsoft-ARM-Assembler keine Angebote erzeugt werden.

`PRESERVE8`<br/>
Wird nicht unterstützt.

`RELOC`<br/>
`RELOC n` können Sie nur eine Anweisung oder eine Data Definition-Anweisung folgen. Es gibt keine "Anonym"Symbol", die verschoben werden kann.

`REQUIRE`<br/>
Wird nicht unterstützt.

`REQUIRE8`<br/>
Wird nicht unterstützt.

`THUMBX`<br/>
Nicht unterstützt, da der Microsoft-ARM-Assembler nicht den Thumb-2ee zurück-Anweisungssatz unterstützt.

## <a name="see-also"></a>Siehe auch

[Befehlszeilenverweis des ARM-Assemblers](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[Diagnosemeldungen des ARM-Assemblers](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
