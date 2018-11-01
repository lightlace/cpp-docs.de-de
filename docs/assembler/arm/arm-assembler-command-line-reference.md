---
title: Befehlszeilenreferenz des ARM-Assemblers
ms.date: 08/30/2018
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
ms.openlocfilehash: f49b59a81fbe5f11c0f219d1e1fe83a4ee811c7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579235"
---
# <a name="arm-assembler-command-line-reference"></a>Befehlszeilenreferenz des ARM-Assemblers

Dieser Artikel enthält Angaben über den Microsoft-ARM-Assembler in der Befehlszeile *Armasm*, die ARMv7-Thumb-Assemblysprache kompiliert, in der Microsoft-Implementierung von der Common Object File Format (COFF). Der Linker kann COFF-Code mit Objektcode verknüpfen, das erstellt wird, indem der ARM-Assembler oder der C-Compiler, zusammen mit der Objektbibliotheken, die von der Bibliothekar erstellt werden.

## <a name="syntax"></a>Syntax

> **Armasm** [*Optionen*] *Sourcefile* *Objektdatei*
> **Armasm** [*Optionen *] **- e/a** *Objektdatei* *Sourcefile*

### <a name="parameters"></a>Parameter

*options*<br/>
Eine Kombination aus 0 (null) oder mehrere der folgenden:

- **-Fehler** *Dateiname*<br/>
   Umleiten von Fehler- und Warnmeldungen zu *Filename*.

- **-i** *Dir*[**;** <em>Dir</em>]<br/>
   Die angegebenen Verzeichnisse im Include-Suchpfad hinzufügen.

- **-vordefinieren** *Richtlinie*<br/>
   Geben Sie eine Richtlinie festgelegt, SETL oder SETS vordefinieren ein Symbols an.<br/>
   Beispiel: **armasm.exe-vordefinieren source.asm "Festgelegt, 150 COUNT"**<br/>
   Weitere Informationen finden Sie unter den [ARM Compiler Armasm Referenzhandbuch](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

- **-nowarn**<br/>
   Deaktivieren Sie alle Warnmeldungen.

- **-ignorieren** *Warnung*<br/>
   Die angegebene Warnung zu deaktivieren. Mögliche Werte finden Sie im Abschnitt zu Warnungen.

- **-help**<br/>
   Drucken Sie die Befehlszeilenhilfe-Nachricht.

- **-Machine** *Computer*<br/>
   Geben Sie den Computer im PE-Header festlegen.  Mögliche Werte für *Computer* sind:<br/>
   **ARM**– wird von den Computertyp auf IMAGE_FILE_MACHINE_ARMNT. Dies ist die Standardeinstellung.<br/>
   **Thumb-Steuerelement**– wird von den Computertyp auf IMAGE_FILE_MACHINE_THUMB.

- **-oldit**<br/>
   Generieren von ARMv7-Stil IT-Blöcke.  Standardmäßig ARMv8-kompatible IT-Blöcke generiert werden.

- **-über** *Dateiname*<br/>
   Lesen zusätzliche Befehlszeilenargumente von *Filename*.

- **-16**<br/>
   Assemblieren Sie Quelle als 16-Bit-Thumb-Anweisungen.  Dies ist die Standardeinstellung.

- **-32**<br/>
   Assemblieren Sie Quelle als 32-Bit-ARM-Anweisungen.

- **-g**<br/>
   Generieren Sie Debuginformationen.

- **-ErrorReport:** *Option*<br/>
   Geben Sie die Assembler-Tool wie interne Fehler an Microsoft gemeldet werden.  Mögliche Werte für *Option* sind:<br/>
   **keine**– senden keine Berichte.<br/>
   **Eingabeaufforderung**– der Benutzer aufgefordert, die Berichte sofort übertragen.<br/>
   **Warteschlange**– der Benutzer aufgefordert, die Berichte bei der nächsten administratoranmeldung zu senden. Dies ist die Standardeinstellung.<br/>
   **Senden von**– Berichte automatisch senden.

*SourceFile*<br/>
Der Name der Quelldatei.

*Objektdatei*<br/>
Der Name der Objektdatei (Ausgabe).

## <a name="remarks"></a>Hinweise

Im folgenden Beispiel wird veranschaulicht, wie Armasm in einem typischen Szenario verwendet wird. Verwenden Sie zunächst Armasm, um eine Quelldatei Assemblysprache (ASM) auf eine Objektdatei (obj) zu erstellen. Klicken Sie dann verwenden Sie den CL-Befehlszeilen-C-Compiler zu, um eine Quelldatei (c) zu kompilieren, und auch Geben Sie an, der Linkeroption, um die ARM-Objektdatei verknüpft werden.

**armasm myasmcode.asm -o myasmcode.obj**

**cl myccode.c /link myasmcode.obj**

## <a name="see-also"></a>Siehe auch

[Diagnosemeldungen des ARM-Assemblers](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
[ARM-Assemblyanweisungen](../../assembler/arm/arm-assembler-directives.md)<br/>
