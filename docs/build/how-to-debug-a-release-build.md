---
title: 'Vorgehensweise: Debuggen eines Releasebuilds'
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
ms.openlocfilehash: 6d93fac4e980085c322acb55e6f8758e6cea0a00
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826171"
---
# <a name="how-to-debug-a-release-build"></a>Vorgehensweise: Debuggen eines Releasebuilds

Sie können einen Releasebuild einer Anwendung debuggen.

### <a name="to-debug-a-release-build"></a>Debuggen ein Releasebuilds

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](working-with-project-properties.md).

1. Klicken Sie auf die **C/C++-** Knoten. Legen Sie **Debuginformationsformat** zu [C7-kompatibel (/ Z7)](reference/z7-zi-zi-debug-information-format.md) oder **Programmdatenbank (/ Zi)**.

1. Erweitern Sie **Linker** , und klicken Sie auf die **allgemeine** Knoten. Legen Sie **inkrementelles Verknüpfen aktivieren** zu [No (/ INCREMENTAL: NO)](reference/incremental-link-incrementally.md).

1. Wählen Sie die **Debuggen** Knoten. Legen Sie **Debuginfo generieren** zu [Ja (/ DEBUG)](reference/debug-generate-debug-info.md).

1. Wählen Sie die **Optimierung** Knoten. Legen Sie **Verweise** zu [/OPT: REF](reference/opt-optimizations.md) und **COMDAT-Faltung aktivieren** zu [/OPT: ICF](reference/opt-optimizations.md).

1. Sie können jetzt das Releasebuild der Anwendung debuggen. Finden ein Problem, durchlaufen Sie den Code (oder mit Just-In-Time-Debuggen), bis Sie gefunden haben, in dem der Fehler auftritt, und ermitteln Sie dann auf die falsche Parameter oder den Code.

   Wenn eine Anwendung in einem Debugbuild funktioniert, aber in einem Releasebuild fehlschlägt, kann eine der compileroptimierungen einen Fehler im Quellcode ausgesetzt werden. Um das Problem zu isolieren, deaktivieren Sie ausgewählte Optimierungen für jede Quellcodedatei, bis Sie finden die Datei und die Optimierung, die das Problem verursacht. (Um den Prozess zu beschleunigen, können Sie die Dateien in zwei Gruppen unterteilen, deaktivieren Optimierung für eine Gruppe, und wenn Sie ein Problem in einer Gruppe finden weiterhin geteilt, bis Sie die problematische Datei isolieren.)

   Sie können [/RTC](reference/rtc-run-time-error-checks.md) versuchen, diese Art von Fehlern in den Debugbuilds verfügbar zu machen.

   Weitere Informationen finden Sie unter [optimieren Sie Ihren Code](optimizing-your-code.md).

## <a name="see-also"></a>Siehe auch

[Beheben von Problemen mit dem Releasebuild](fixing-release-build-problems.md)
