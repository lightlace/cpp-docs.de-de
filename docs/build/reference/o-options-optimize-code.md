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
ms.openlocfilehash: f4e2bf8b848654f7b87c59e7a54994448ee62d51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481327"
---
# <a name="o-options-optimize-code"></a>/O-Optionen (Code optimieren)

Die **/o** Optionen steuern verschiedene Optimierungen, mit denen Sie Code für maximale Geschwindigkeit oder die minimale Größe zu erstellen.

- [/ O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) legt eine Kombination verschiedener Optimierungen, die minimale Größencode generieren.

- [/ O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) legt eine Kombination verschiedener Optimierungen, die Code für maximale Geschwindigkeit optimiert.

- [Tatsächlich](../../build/reference/ob-inline-function-expansion.md) Inlinefunktionserweiterung steuert.

- [/ Od](../../build/reference/od-disable-debug.md) deaktiviert die Optimierung, um die Kompilierung zu beschleunigen und das Debuggen vereinfachen.

- ["/ Og"](../../build/reference/og-global-optimizations.md) aktiviert globale Optimierungen.

- [/ Oi](../../build/reference/oi-generate-intrinsic-functions.md) erstellt systeminterne Funktionen für die entsprechende Funktionsaufrufen.

- [/ OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) weist den Compiler, Optimierungen der Größe gegenüber Optimierungen der Geschwindigkeit zu bevorzugen.

- [/ Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (Standardeinstellung) weist den Compiler, Optimierungen der Geschwindigkeit gegenüber Optimierungen der Größe zu bevorzugen.

- [/ Ox](../../build/reference/ox-full-optimization.md) ist eine Kombination aus-Option, die einige der Optimierungen, die mit einem Schwerpunkt auf Geschwindigkeit auswählt. Es ist eine strikte Teilmenge der **"/ O2"** Optimierungen.

- [/ Oy](../../build/reference/oy-frame-pointer-omission.md) unterdrückt die Erstellung von Framezeigern in der Aufrufliste für schnellere Funktionsaufrufe.

## <a name="remarks"></a>Hinweise

Sie können mehrere kombinieren **/o** Optionen in eine einzelne Option-Anweisung. Z. B. **/Odi** ist identisch mit **/od/Oi**. Bestimmte Optionen gegenseitig aus, und verursacht einen Compilerfehler, wenn Sie zusammen verwendet. Finden Sie unter den einzelnen **/o** Optionen für die Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)