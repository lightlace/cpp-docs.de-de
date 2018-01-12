---
title: O - Optionen (Code optimieren) | Microsoft Docs
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs: C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7da04384d0c4ea00c2eaaedbcf0ec770e216289
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="o-options-optimize-code"></a>/O-Optionen (Code optimieren)

Die **/o** Optionen steuern verschiedene Optimierungen, mit denen Sie Code für maximale Geschwindigkeit oder die minimale Größe erstellen.

- [/ O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) legt eine Kombination von Optimierungen, die minimale Größencode zu generieren.

- [/ O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) legt eine Kombination von Optimierungen, die Code für maximale Geschwindigkeit optimiert wird.

- [Tatsächlich](../../build/reference/ob-inline-function-expansion.md) Inlinefunktionserweiterung steuert.

- [/ Od](../../build/reference/od-disable-debug.md) deaktiviert Optimierung, um die Kompilierung zu beschleunigen und zu debuggen zu vereinfachen.

- [/ Og](../../build/reference/og-global-optimizations.md) globale Optimierungen aktiviert.

- [/ Oi](../../build/reference/oi-generate-intrinsic-functions.md) erstellt systeminterne Funktionen für entsprechende Funktionsaufrufe.

- [/ OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) teilt dem Compiler mit Optimierungen für Größe Optimierungen für Geschwindigkeit vorzuziehen.

- [/ Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (Standardeinstellung) teilt dem Compiler mit Optimierungen für Geschwindigkeit Optimierungen für Größe vorzuziehen.

- [/ Ox](../../build/reference/ox-full-optimization.md) ist eine Kombination aus-Option, die einige der Optimierungen mit Schwerpunkt auf Geschwindigkeit auswählt. Es ist eine strikte Teilmenge der **/O2** Optimierungen.

- [/ Oy](../../build/reference/oy-frame-pointer-omission.md) unterdrückt die Erstellung von Framezeigern in der Aufrufliste für schnellere Funktionsaufrufe.

## <a name="remarks"></a>Hinweise

Sie können mehrere kombinieren **/o** Optionen in eine einzelne Option-Anweisung. Beispielsweise **/Odi** ist identisch mit **/od/Oi**. Bestimmte Optionen gegenseitig aus und einen Compilerfehler verursacht, wenn Sie zusammen verwendet. Finden Sie unter der einzelnen **/o** Optionen für Weitere Informationen.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)