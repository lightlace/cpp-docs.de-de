---
title: /Qfast_transcendentals (Erzwingen von schnellen Transzendenten)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: d96b2c93e9fc8be73ef43f63fc0a6328661df442
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414199"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Erzwingen von schnellen Transzendenten)

Generiert Inlinecode für transzendentale Funktionen.

## <a name="syntax"></a>Syntax

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Hinweise

Diese Compileroption erzwingt transzendentale Funktionen, um Inlinecode zur Verbesserung der Geschwindigkeit der abfrageausführung konvertiert werden soll. Diese Option wirkt sich nur bei Verwendung **/fp: mit Ausnahme von** oder **/fp: präzise**. Generieren von Inlinecode für transzendentale Funktionen ist bereits das Standardverhalten unter **fast**.

Diese Option ist nicht kompatibel mit **/fp: strict**. Finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../../build/reference/fp-specify-floating-point-behavior.md) für Weitere Informationen über Gleitkomma-Compileroptionen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
