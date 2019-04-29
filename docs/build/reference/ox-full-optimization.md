---
title: / Ox (die meisten Geschwindigkeitsoptimierungen aktivieren)
ms.date: 10/18/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: e39905608087425fe5a445f4ef88434d73bb2ded
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320096"
---
# <a name="ox-enable-most-speed-optimizations"></a>/ Ox (die meisten Geschwindigkeitsoptimierungen aktivieren)

Die **/Ox** -Compileroption ermöglicht es, eine Kombination verschiedener Optimierungen, die Geschwindigkeit zu bevorzugen. In einigen Versionen von Visual Studio-IDE und die hilfemeldung für den Compiler, heißt dies *Komplette Optimierung*, aber die **/Ox** Compileroption kann nur eine Teilmenge der aktiviert, indem Optionen für die Optimierung der Geschwindigkeit **"/ O2"**.

## <a name="syntax"></a>Syntax

> **/Ox**

## <a name="remarks"></a>Hinweise

Die **/Ox** Compiler-Option ermöglicht die **/o** Compileroptionen, Geschwindigkeit bevorzugen. Die **/Ox** Compileroption schließt nicht die zusätzlichen [/GF (Doppelte Zeichenfolgen beseitigen)](gf-eliminate-duplicate-strings.md) und [/Gy (Funktionslevel-Linking aktivieren)](gy-enable-function-level-linking.md) Optionen aktiviert, indem ["/ O1" oder "/ O2" (Größe minimieren, Geschwindigkeit maximieren)](o1-o2-minimize-size-maximize-speed.md). Die zusätzlichen Optionen angewendet, indem **"/ O1"** und **"/ O2"** kann dazu führen, dass Zeiger auf Zeichenfolgen und Funktionen für die eine Zieladresse, was Debuggen beeinträchtigen kann und die strikte Konformität. Die **/Ox** Option ist eine einfache Möglichkeit zum Aktivieren von den meisten Optimierungen ohne **/GF** und **/Gy**. Weitere Informationen finden Sie unter der Beschreibung der Argumente der [/GF](gf-eliminate-duplicate-strings.md) und [/Gy](gy-enable-function-level-linking.md) Optionen.

Die **/Ox** Compileroption ist identisch mit den folgenden Optionen zusammen:

- [/ Ob (Inlinefunktionserweiterung)](ob-inline-function-expansion.md), wobei die Option-Parameter 2 ist (**/Ob2**)

- [/Og (Globale Optimierungen)](og-global-optimizations.md)

- [/Oi (Intrinsische Funktionen generieren)](oi-generate-intrinsic-functions.md)

- [/ Ot (schnellen Code bevorzugen)](os-ot-favor-small-code-favor-fast-code.md)

- [/ Oy (Framezeiger unterdrücken)](oy-frame-pointer-omission.md)

**/ Ox** ist gegenseitig aus:

- [/ O1 (Größe minimieren)](o1-o2-minimize-size-maximize-speed.md)

- [/ O2 (Geschwindigkeit maximieren)](o1-o2-minimize-size-maximize-speed.md)

- [/Od (Deaktivieren (Debuggen))](od-disable-debug.md)

Können Sie die Verschiebung in Richtung der Geschwindigkeit der Abbrechen der **/Ox** Compileroption, wenn Sie angeben, **/Oxs**, welche kombiniert die **/Ox** Compileroption mit  [ /OS (so klein Code)](os-ot-favor-small-code-favor-fast-code.md). Die Kombination beider Optionen Codegröße kleinere.  Die **/Oxs** Option ist genau derselbe, als wenn **/Ox** **/OS** Wenn die Optionen in dieser Reihenfolge angezeigt werden.

Um alle verfügbaren auf Dateiebene Optimierungen für Releasebuilds anzuwenden, die Sie angeben, sollten ["/ O2" (Geschwindigkeit maximieren)](o1-o2-minimize-size-maximize-speed.md) anstelle von **/Ox**, und [/O1 (Größe minimieren)](o1-o2-minimize-size-maximize-speed.md) stattdessen der **/Oxs**. Für noch mehr Optimierung in Version erstellt wurde, berücksichtigen Sie auch die [/GL (Whole Program Optimization)](gl-whole-program-optimization.md) Compileroption und [/LTCG (Link-Time Code Generation)](ltcg-link-time-code-generation.md) -Linkeroption.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie unter **Konfigurationseigenschaften**öffnen **C/C++-** und wählen Sie dann die **Optimierung** Eigenschaftenseite.

1. Ändern der **Optimierung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](o-options-optimize-code.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
