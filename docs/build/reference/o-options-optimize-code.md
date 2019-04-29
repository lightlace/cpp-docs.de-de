---
title: /O-Optionen (Code optimieren)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: ffd3023120f1d930a24ccef6fa297594062322df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320421"
---
# <a name="o-options-optimize-code"></a>/O-Optionen (Code optimieren)

Die **/o** Optionen steuern verschiedene Optimierungen, mit denen Sie Code für maximale Geschwindigkeit oder die minimale Größe zu erstellen.

- [/ O1](o1-o2-minimize-size-maximize-speed.md) legt eine Kombination verschiedener Optimierungen, die minimale Größencode generieren.

- [/ O2](o1-o2-minimize-size-maximize-speed.md) legt eine Kombination verschiedener Optimierungen, die Code für maximale Geschwindigkeit optimiert.

- [Tatsächlich](ob-inline-function-expansion.md) Inlinefunktionserweiterung steuert.

- [/ Od](od-disable-debug.md) deaktiviert die Optimierung, um die Kompilierung zu beschleunigen und das Debuggen vereinfachen.

- ["/ Og"](og-global-optimizations.md) aktiviert globale Optimierungen.

- [/ Oi](oi-generate-intrinsic-functions.md) erstellt systeminterne Funktionen für die entsprechende Funktionsaufrufen.

- [/ OS](os-ot-favor-small-code-favor-fast-code.md) weist den Compiler, Optimierungen der Größe gegenüber Optimierungen der Geschwindigkeit zu bevorzugen.

- [/ Ot](os-ot-favor-small-code-favor-fast-code.md) (Standardeinstellung) weist den Compiler, Optimierungen der Geschwindigkeit gegenüber Optimierungen der Größe zu bevorzugen.

- [/ Ox](ox-full-optimization.md) ist eine Kombination aus-Option, die einige der Optimierungen, die mit einem Schwerpunkt auf Geschwindigkeit auswählt. Es ist eine strikte Teilmenge der **"/ O2"** Optimierungen.

- [/ Oy](oy-frame-pointer-omission.md) unterdrückt die Erstellung von Framezeigern in der Aufrufliste für schnellere Funktionsaufrufe.

## <a name="remarks"></a>Hinweise

Sie können mehrere kombinieren **/o** Optionen in eine einzelne Option-Anweisung. Z. B. **/Odi** ist identisch mit **/od/Oi**. Bestimmte Optionen gegenseitig aus, und verursacht einen Compilerfehler, wenn Sie zusammen verwendet. Finden Sie unter den einzelnen **/o** Optionen für die Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
