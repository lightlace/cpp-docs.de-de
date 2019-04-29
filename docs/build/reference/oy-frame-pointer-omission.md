---
title: /Oy (Framezeiger unterdrücken)
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: 7884f52cc22766c6b1a864fc01abcd73f92cfabb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319966"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Framezeiger unterdrücken)

Unterdrückt die Erstellung von Framezeigern im Anrufstapel.

## <a name="syntax"></a>Syntax

> /Oy[-]

## <a name="remarks"></a>Hinweise

Durch diese Option werden Funktionsaufrufe beschleunigt, da keine Framezeiger eingerichtet und entfernt werden müssen. Es gibt auch ein weiteres Register für die allgemeine Nutzung frei.

**/ Oy** Framezeiger unterdrücken können und **/Oy-** Auslassung deaktiviert. In X64 Compiler **/Oy** und **/Oy-** sind nicht verfügbar.

Wenn Ihr Code die Frame-basierte Adressierung erfordert, können Sie angeben der **/Oy-** option die **/Ox** oder verwenden Sie [optimieren](../../preprocessor/optimize.md) mit der "**y**"und **aus** Argumente für die maximale Optimierung für die Frame-basierte Adressierung zu erhalten. Der Compiler erkennt die meisten Situationen, in dem Frame-basierte Adressierung erforderlich ist (z. B. mit der `_alloca` und `setjmp` Funktionen sowie bei strukturierter Ausnahmebehandlung).

Die [/Ox (ermöglichen die meisten Geschwindigkeitsoptimierungen)](ox-full-optimization.md) und [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](o1-o2-minimize-size-maximize-speed.md) implizieren **/Oy**. Angeben von **/Oy-** nach der **/Ox**, **"/ O1"**, oder **"/ O2"** deaktiviert **/Oy**, ob es sich handelt explizit oder implizit.

Die **/Oy** -Compileroption erschwert die Verwendung des Debuggers, da der Compiler hierdurch Framezeigerinformationen unterdrückt. Wenn Sie eine Debug-Compileroption angeben ([/Z7, / Zi, / Zi](z7-zi-zi-debug-information-format.md)), es wird empfohlen, die Sie angeben, die **/Oy-** wurde festgelegt, nachdem alle anderen Optimierungsoptionen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Optimierung** Eigenschaftenseite.

1. Ändern der **Framezeiger** Eigenschaft. Diese Eigenschaft hinzugefügt oder entfernt nur die **/Oy** Option. Wenn Sie hinzufügen möchten die **/Oy-** auswählen, wählen die **über die Befehlszeile** Eigenschaft Seite, und ändern Sie **zusätzliche Optionen**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](o-options-optimize-code.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
