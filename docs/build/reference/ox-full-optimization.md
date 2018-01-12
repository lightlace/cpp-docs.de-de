---
title: -Ox (die meisten Geschwindigkeit Optimierungen aktivieren) | Microsoft Docs
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /ox
dev_langs: C++
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85efa8a2beab34d0dcf1bdb74e3cf89008b10d6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ox-enable-most-speed-optimizations"></a>/ Ox (die meisten Geschwindigkeit Optimierungen aktivieren)

Die **/Ox** Compileroption ermöglicht eine Kombination von Optimierungen, die Geschwindigkeit zu bevorzugen. In einigen Versionen von Visual Studio-IDE und den Hilfetext für den Compiler, heißt dies *Komplette Optimierung*, aber die **/Ox** -Compileroption kann nur eine Teilmenge der aktiviert, indem Optionen für die Optimierung der Geschwindigkeit **/O2**.

## <a name="syntax"></a>Syntax

> /Ox

## <a name="remarks"></a>Hinweise

Die **/Ox** Compiler Option ermöglicht die **/o** Compileroptionen, Geschwindigkeit bevorzugen. Die **/Ox** Compileroption enthält keine zusätzlichen [/GF (Doppelte Zeichenfolgen beseitigen)](../../build/reference/gf-eliminate-duplicate-strings.md) und [/Gy (Funktionslevel Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md) AktivierteOptionen[/O1 oder/O2 (Größe minimieren, Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md). Die zusätzlichen Optionen angewendet, indem **/O1** und **/O2** kann dazu führen, dass Zeiger auf Zeichenfolgen oder auf Funktionen eine Zieladresse, was Debuggen beeinträchtigen kann und die Sprache strikte Konformität freigeben. Die **/Ox** Option ist eine einfache Möglichkeit, die meisten Optimierungen zu aktivieren, ohne einschließlich **/GF** und **/Gy**. Weitere Informationen finden Sie unter der Beschreibung der [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) und [/Gy](../../build/reference/gy-enable-function-level-linking.md) Optionen.

Die **/Ox** Compileroption ist identisch mit den folgenden Optionen zusammen:

- [/ Ob (Inlinefunktionserweiterung)](../../build/reference/ob-inline-function-expansion.md), wobei der Optionsparameter 2 ist (**/Ob2**)

- [/ Og (globale Optimierungen)](../../build/reference/og-global-optimizations.md)

- [/ Oi (systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/ Ot (schnellen Code bevorzugen)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [Oy (Framezeiger)](../../build/reference/oy-frame-pointer-omission.md)

**/ Ox** ist gegenseitig aus:

- [/ O1 (Größe minimieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/ O2 (Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/ Od (deaktivieren (Debuggen))](../../build/reference/od-disable-debug.md)

Können Sie die Verschiebung in Richtung der Geschwindigkeit des Abbrechen der **/Ox** Compileroption bei Angabe von **/Oxs**, kombiniert die **/Ox** Compileroption mit  [ /OS (kompakten klein Code)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md). Die Kombination beider Optionen Codegröße kleinere.

Um alle verfügbaren auf Dateiebene Optimierungen für Releasebuilds anzuwenden, die Sie angeben, sollten [/O2 (Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) anstelle von **/Ox**, und [/O1 (Größe minimieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) stattdessen der **/Oxs**. Für noch mehr Optimierung in Version erstellt wurde, sollten Sie auch die [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md) (Compileroption) und [/LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md) (Linkeroption).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie unter **Konfigurationseigenschaften**öffnen **C/C++-** und wählen Sie dann die **Optimierung** Eigenschaftenseite.

1. Ändern der **Optimierung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Siehe auch

[/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)  
[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)