---
title: /Qfast_transcendentals (Erzwingen von schnellen Transzendenten)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 383a915721d627367ca2ca035957df947996bbe2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319316"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Erzwingen von schnellen Transzendenten)

Generiert Inlinecode für transzendentale Funktionen.

## <a name="syntax"></a>Syntax

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Hinweise

Diese Compileroption erzwingt transzendentale Funktionen, um Inlinecode zur Verbesserung der Geschwindigkeit der abfrageausführung konvertiert werden soll. Diese Option wirkt sich nur bei Verwendung **/fp: mit Ausnahme von** oder **/fp: präzise**. Generieren von Inlinecode für transzendentale Funktionen ist bereits das Standardverhalten unter **fast**.

Diese Option ist nicht kompatibel mit **/fp: strict**. Finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](fp-specify-floating-point-behavior.md) für Weitere Informationen über Gleitkomma-Compileroptionen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](q-options-low-level-operations.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
