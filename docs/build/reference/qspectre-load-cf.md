---
title: /Qspectre-load-cf
description: Beschreibt die Option "MicrosoftC++ C/Compiler (MSVC)/Qspectre-load-cf".
ms.date: 01/28/2020
helpviewer_keywords:
- /Qspectre-load-cf
no-loc:
- Qspectre-load-cf
ms.openlocfilehash: c32b843df517cb6fbe662fba0b592cbf745f1764
ms.sourcegitcommit: 0f4ee9056d65043fa5a715f0ad1031c0ed30e2b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2020
ms.locfileid: "77035547"
---
# /Qspectre-load-cf

Gibt die Compilergenerierung von serialisierungsanweisungen für jede Ablauf Steuerungs Anweisung an, die eine Last enthält. Diese Option führt eine Teilmenge der entschärfungen aus, die von der [/Qspectre-Load](qspectre-load.md) -Option durchgeführt werden.

## <a name="syntax"></a>Syntax

> **/Qspectre-load-cf**

## <a name="remarks"></a>Bemerkungen

**/Qspectre-load-cf** bewirkt, dass der Compiler `JMP`, `RET`und `CALL` Ablauf Steuerungs Anweisungen erkennt, die aus dem Arbeitsspeicher geladen werden, und serialisierungsanweisungen nach dem Laden einfügen. Nach Möglichkeit werden diese Anweisungen in eine Last und eine Ablauf Steuerungs Übertragung aufgeteilt. Auf die Last folgt eine `LFENCE`, um sicherzustellen, dass die Last geschützt ist. Es gibt Fälle, in denen der Compiler keine Anweisungen aufteilen kann, wie z. b. die `JMP`-Anweisung, sodass er eine Alternative Entschärfungs Methode verwendet. Der Compiler verringert `jmp [rax]` z. b. durch Hinzufügen von Anweisungen zum nicht destruktiven Laden des Ziels vor dem Einfügen eines lfence, wie hier gezeigt:

```asm
    xor rbx, [rax]
    xor rbx, [rax]  ; force a load of [rax]
    lfence          ; followed by an LFENCE
    jmp [rax]
```

Da **/Qspectre-load-cf** die Spekulation aller Ladungen in Anweisungen für den Ablauf Steuerungs Vorgang stoppt, ist die Leistung stark beeinträchtigt. Die Entschärfung ist nicht überall geeignet. Wenn leistungskritische Code Blöcke vorhanden sind, die keinen Schutz erfordern, können Sie diese entschärfungen mithilfe von `__declspec(spectre(nomitigation))`deaktivieren.

Die Option **/Qspectre-load-cf** ist standardmäßig deaktiviert und unterstützt alle Optimierungs Ebenen.

Die Option **/Qspectre-load-cf** ist in Visual Studio 2019, Version 16,5 und höher, verfügbar. Diese Option ist nur in Compilern verfügbar, die auf x86-und x64-Prozessoren abzielen. Es ist nicht in Compilern verfügbar, die auf ARM-Prozessoren abzielen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

2. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C/ > C++ -** **Code Generierung** aus.

3. Wählen Sie einen neuen Wert für die Eigenschaft **Spectre-Entschärfung** aus. Wählen Sie **OK** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Weitere Informationen

[/Q-Optionen (Low-Level-Vorgänge)](q-options-low-level-operations.md)\
[MSVC-Compileroptionen](compiler-options.md)\
[MSVC-compilerbefehlszeilensyntax](compiler-command-line-syntax.md)
