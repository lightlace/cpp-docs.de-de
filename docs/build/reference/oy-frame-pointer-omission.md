---
title: -Oy (Framezeiger) | Microsoft Docs
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
dev_langs: C++
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15a760d1a9df383356ead2eb2d1e1b08e8b9ca57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="oy-frame-pointer-omission"></a>/Oy (Framezeiger unterdrücken)

Unterdrückt die Erstellung von Framezeigern im Anrufstapel.

## <a name="syntax"></a>Syntax

> / Oy [-]

## <a name="remarks"></a>Hinweise

Durch diese Option werden Funktionsaufrufe beschleunigt, da keine Framezeiger eingerichtet und entfernt werden müssen. Außerdem wird ein weiteres Register (EBP bei Intel 386- oder neueren Prozessoren) zum Speichern häufig verwendeter Variablen und untergeordneter Ausdrücke freigegeben.

**/ Oy** ermöglicht Framezeigers und **/Oy-** Auslassung deaktiviert. **/ Oy** steht nur in X86 Compiler.

Wenn Ihr Code EBP-basierte Adressierung erfordert, können Sie angeben der **/Oy-** option nach der **/Ox** oder verwenden Sie [optimieren](../../preprocessor/optimize.md) mit der "**y**" und **deaktiviert** Argumente, um maximale Optimierung mit EBP-basierte Adressierung zu erhalten. Der Compiler erkennt in den meisten Situationen, wenn eine EBP-basierte Adressierung erforderlich ist (beispielsweise in der `_alloca`-und der `setjmp`-Funktion sowie bei strukturierter Ausnahmebehandlung).

Die [/Ox (ermöglichen die meisten Geschwindigkeit Optimierungen)](../../build/reference/ox-full-optimization.md) und [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) implizieren **/Oy**. Angeben von **/Oy-** nach der **/Ox**, **/O1**, oder **/O2** deaktiviert die option **/Oy**, ob es sich handelt explizite oder implizite.

Die **/Oy** -Compileroption erschwert die Verwendung des Debuggers, da der Compiler hierdurch Framezeigerinformationen unterdrückt. Wenn Sie eine Compileroption "Debug" angeben (["/ Z7", / Zi, / Zi](../../build/reference/z7-zi-zi-debug-information-format.md)), wird empfohlen, dass Sie die **/Oy-** festgelegt, nachdem alle anderen Optimierungsoptionen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Optimierung** Eigenschaftenseite.

1. Ändern der **Framezeiger** Eigenschaft. Diese Eigenschaft hinzugefügt oder entfernt nur die **/Oy** Option. Wenn Sie hinzufügen möchten die **/Oy-** aus, klicken Sie auf **Befehlszeile** und Ändern von **Zusatzoptionen**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>.

## <a name="see-also"></a>Siehe auch

[/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)

[Compileroptionen](../../build/reference/compiler-options.md)

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)