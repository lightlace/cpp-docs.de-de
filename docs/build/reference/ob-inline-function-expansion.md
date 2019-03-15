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
ms.openlocfilehash: 6bf16e5725916e81e64d80c0a1f96bf502c8826c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807496"
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

**/ Ob2** ist gültig, wenn [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](o1-o2-minimize-size-maximize-speed.md) oder [/Ox (ermöglichen die meisten Geschwindigkeitsoptimierungen)](ox-full-optimization.md) verwendet wird.

Diese Option erfordert, dass Sie Optimierungen mithilfe aktivieren **"/ O1"**, **"/ O2"**, **/Ox**, oder **"/ Og"**.

## <a name="remarks"></a>Hinweise

Der Compiler behandelt die Inlineerweiterungsoptionen und -Schlüsselwörter als Vorschläge. Es gibt keine Garantie dafür, dass eine bestimmte Funktion inline erweitert wird. Sie können die Inlineerweiterung deaktivieren, Sie können den Compiler aber nicht dazu zwingen, für eine bestimmte Funktion Inlining auszuführen, auch nicht mithilfe des Schlüsselworts `__forceinline`.

Sie können die `#pragma` [Auto_inline](../../preprocessor/auto-inline.md) Direktive, um die Funktionen von der Berücksichtigung als Kandidaten für die Inlineerweiterung auszuschließen. Siehe auch die `#pragma` [systeminterne](../../preprocessor/intrinsic.md) Richtlinie.

> [!NOTE]
> Informationen, die profilerstellung gesammelt werden, überschreiben Optimierungen, die andernfalls gültig wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen finden Sie unter [Profile-Guided Optimizations](../profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie **Konfigurationseigenschaften**, **C/C++-**, und wählen Sie **Optimierung**.

1. Ändern der **Inlinefunktionserweiterung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](o-options-optimize-code.md)<br/>
[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
