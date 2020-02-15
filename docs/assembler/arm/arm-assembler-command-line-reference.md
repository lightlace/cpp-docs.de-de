---
title: Befehlszeilenreferenz zum ARM-Assemblers
description: Referenzhandbuch zu den Befehlszeilenoptionen für den Microsoft Arm-Assembler.
ms.date: 02/09/2020
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
ms.openlocfilehash: a63273e8d21e7a28574ec79d62c15f29ee59cd50
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257378"
---
# <a name="arm-assembler-command-line-reference"></a>Befehlszeilenreferenz zum ARM-Assemblers

Dieser Artikel enthält Befehlszeilen Informationen über den Microsoft Arm-Assembler, **armasm**. **armasm** assembliert ARMv7 Thumb-Assemblysprache in die Microsoft-Implementierung des Common Object File Format (COFF). Der Linker kann COFF-Code Objekte verknüpfen, die sowohl vom Arm-Assembler als auch vom C-Compiler erstellt werden. Sie kann entweder zusammen mit Objektbibliotheken verknüpft werden, die vom Bibliothekar erstellt wurden.

## <a name="syntax"></a>Syntax

> **`armasm`** [*Optionen*] *source_file* *object_file*\
> **`armasm`** [*Optionen*] **`-o`** *object_file* *source_file*

### <a name="parameters"></a>Parameter

*Optionen*\
Eine Kombination aus null oder mehr der folgenden Optionen:

- **`-errors`** *Dateiname*\
   Umleiten von Fehler-und Warnmeldungen an *filename*.

- **`-i`** *dir*[ **`;`** <em>dir</em>] \
   Fügt die angegebenen Verzeichnisse zum include-Suchpfad hinzu.

- **`-predefine`** - *Direktive*\
   Geben Sie eine Seta-, SETL-oder Sets-Direktive an, um ein Symbol vorzudefinieren.
   Beispiel: `armasm.exe -predefine "COUNT SETA 150" source.asm`\
   Weitere Informationen finden Sie im [ARM Compiler armasm Reference Guide](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

- **`-nowarn`**\
   Deaktivieren Sie alle Warnmeldungen.

- **`-ignore`** *Warnung*\
   Deaktiviert die angegebene Warnung. Mögliche Werte finden Sie im Abschnitt zu Warnungen.

- **`-help`**\
   Druckt die Befehlszeilen-Hilfe Nachricht.

- **`-machine`** *Computer*\
   Geben Sie den Computertyp an, der im PE-Header festgelegt wird.  Mögliche Werte für " *Computer* ": \
   **Arm**– legt den Computertyp auf IMAGE_FILE_MACHINE_ARMNT fest. Diese Option ist die Standardeinstellung. \
   **Thumb**– legt den Computertyp auf IMAGE_FILE_MACHINE_THUMB fest.

- **`-oldit`**\
   Generieren von ARMv7-Blöcken.  Standardmäßig werden ARMv8-kompatible it-Blöcke generiert.

- **`-via`** *Dateiname*\
   Lesen Sie zusätzliche Befehlszeilenargumente aus *filename*.

- **`-16`**\
   Assemblieren Sie Source als 16-Bit-Ziehpunkt Anweisungen.  Diese Option ist die Standardeinstellung.

- **`-32`**\
   Assemblieren Sie Source als 32-Bit-arm-Anweisungen.

- **`-g`**\
   Generieren von Debuginformationen.

- **`-errorReport:`** *Option*\
   Diese Option ist veraltet. Ab Windows Vista wird die Fehlerberichterstattung durch [Windows-Fehlerberichterstattung (wer)](/windows/win32/wer/windows-error-reporting) -Einstellungen gesteuert.

*source_file*\
Der Name der Quelldatei.

*object_file*\
Der Name der Objektdatei (Ausgabedatei).

## <a name="remarks"></a>Bemerkungen

Im folgenden Beispiel wird veranschaulicht, wie armasm in einem typischen Szenario verwendet werden kann. Verwenden Sie zuerst armasm, um eine assemblysprachquelldatei (ASM-Datei) in einer Objektdatei (obj-Datei) zu erstellen. Kompilieren Sie dann mithilfe des Befehlszeilen-C-Compilers von cl eine Quelldatei (. C), und geben Sie auch die Linkeroption zum Verknüpfen der Arm-Objektdatei an.

```cmd
armasm myasmcode.asm -o myasmcode.obj
cl myccode.c /link myasmcode.obj
```

## <a name="see-also"></a>Weitere Informationen

[Diagnosemeldungen des Arm-Assemblers](../../assembler/arm/arm-assembler-diagnostic-messages.md)\
[Arm-Assembler-Anweisungen](../../assembler/arm/arm-assembler-directives.md)
