---
title: -Oy (Framezeiger unterdrücken) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/22/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
dev_langs:
- C++
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c077b5a350d7381adc5412ca4a318713d720ad6
ms.sourcegitcommit: 1870c342d44b10990fd015e60856225c3026e8c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49963050"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Framezeiger unterdrücken)

Unterdrückt die Erstellung von Framezeigern im Anrufstapel.

## <a name="syntax"></a>Syntax

> / Oy [-]

## <a name="remarks"></a>Hinweise

Durch diese Option werden Funktionsaufrufe beschleunigt, da keine Framezeiger eingerichtet und entfernt werden müssen. Es gibt auch ein weiteres Register für die allgemeine Nutzung frei.

**/ Oy** Framezeiger unterdrücken können und **/Oy-** Auslassung deaktiviert. **/ Oy** steht nur in X86 Compiler.

Wenn Ihr Code EBP-basierte Adressierung erfordert, können Sie angeben der **/Oy-** option die **/Ox** oder verwenden Sie [optimieren](../../preprocessor/optimize.md) mit der "**y**" und **aus** Argumente für die maximale Optimierung für EBP-basierte Adressierung zu erhalten. Der Compiler erkennt in den meisten Situationen, wenn eine EBP-basierte Adressierung erforderlich ist (beispielsweise in der `_alloca`-und der `setjmp`-Funktion sowie bei strukturierter Ausnahmebehandlung).

Die [/Ox (ermöglichen die meisten Geschwindigkeitsoptimierungen)](../../build/reference/ox-full-optimization.md) und [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) implizieren **/Oy**. Angeben von **/Oy-** nach der **/Ox**, **"/ O1"**, oder **"/ O2"** deaktiviert **/Oy**, ob es sich handelt explizit oder implizit.

Die **/Oy** -Compileroption erschwert die Verwendung des Debuggers, da der Compiler hierdurch Framezeigerinformationen unterdrückt. Wenn Sie eine Debug-Compileroption angeben ([/Z7, / Zi, / Zi](../../build/reference/z7-zi-zi-debug-information-format.md)), es wird empfohlen, die Sie angeben, die **/Oy-** wurde festgelegt, nachdem alle anderen Optimierungsoptionen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Optimierung** Eigenschaftenseite.

1. Ändern der **Framezeiger** Eigenschaft. Diese Eigenschaft hinzugefügt oder entfernt nur die **/Oy** Option. Wenn Sie hinzufügen möchten die **/Oy-** aus, klicken Sie auf **Befehlszeile** und Ändern von **zusätzliche Optionen**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)

[Compileroptionen](../../build/reference/compiler-options.md)

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
