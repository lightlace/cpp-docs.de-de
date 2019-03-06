---
title: /Ob (Inlinefunktionserweiterung)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 6406b604ab74d29d8bc6c9bc0920fd0cf0bd055b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426146"
---
# <a name="ob-inline-function-expansion"></a>/Ob (Inlinefunktionserweiterung)

Steuert die Inlineerweiterung von Funktionen.

## <a name="syntax"></a>Syntax

> /Ob{0|1|2}

## <a name="arguments"></a>Argumente

**0**<br/>
Deaktiviert Inline-Erweiterungen. In der Standardeinstellung Erweiterung erfolgt nach Ermessen des Compilers bei allen Funktionen, bezeichnet als *Automatisches inlining*.

**1**<br/>
Ermöglicht die Erweiterung wird nur für Funktionen mit dem [Inline](../../cpp/inline-functions-cpp.md), `__inline`, oder `__forceinline`, oder in einer C++-Memberfunktion, die in einer Klassendeklaration definiert.

**2**<br/>
Der Standardwert. Ermöglicht die Erweiterung von Funktionen, die als `inline`, `__inline` oder `__forceinline` gekennzeichnet sind, sowie aller anderen Funktionen, für die sich der Compiler entscheidet.

**/ Ob2** ist gültig, wenn [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder [/Ox (ermöglichen die meisten Geschwindigkeitsoptimierungen)](../../build/reference/ox-full-optimization.md) verwendet wird.

Diese Option erfordert, dass Sie Optimierungen mithilfe aktivieren **"/ O1"**, **"/ O2"**, **/Ox**, oder **"/ Og"**.

## <a name="remarks"></a>Hinweise

Der Compiler behandelt die Inlineerweiterungsoptionen und -Schlüsselwörter als Vorschläge. Es gibt keine Garantie dafür, dass eine bestimmte Funktion inline erweitert wird. Sie können die Inlineerweiterung deaktivieren, Sie können den Compiler aber nicht dazu zwingen, für eine bestimmte Funktion Inlining auszuführen, auch nicht mithilfe des Schlüsselworts `__forceinline`.

Sie können die `#pragma` [Auto_inline](../../preprocessor/auto-inline.md) Direktive, um die Funktionen von der Berücksichtigung als Kandidaten für die Inlineerweiterung auszuschließen. Siehe auch die `#pragma` [systeminterne](../../preprocessor/intrinsic.md) Richtlinie.

> [!NOTE]
> Informationen, die profilerstellung gesammelt werden, überschreiben Optimierungen, die andernfalls gültig wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen finden Sie unter [Profile-Guided Optimizations](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie **Konfigurationseigenschaften**, **C/C++-**, und wählen Sie **Optimierung**.

1. Ändern der **Inlinefunktionserweiterung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
