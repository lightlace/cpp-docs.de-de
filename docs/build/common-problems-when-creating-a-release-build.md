---
title: Häufig auftretende Probleme beim Erstellen eines Releasebuilds
ms.date: 11/04/2016
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting Visual C++
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
ms.openlocfilehash: 7420fd5bbdeec30e9839206803952c02b8b56421
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825916"
---
# <a name="common-problems-when-creating-a-release-build"></a>Häufig auftretende Probleme beim Erstellen eines Releasebuilds

Während der Entwicklung können Sie in der Regel zu erstellen und Testen mit einem Debugbuild Ihres Projekts. Wenn Sie dann Ihre Anwendung für einen Releasebuild erstellen, erhalten Sie möglicherweise eine zugriffsverletzung.

Die nachstehende Liste zeigt die wichtigsten Unterschiede zwischen einem Debugbuild und ein Releasebuild (aufgeführt). Es gibt weitere Unterschiede, aber es folgen die wichtigsten Unterschiede, die fehlschlagen eine Anwendung in einem Releasebuild führen würde, wenn es in einem Debugbuild funktioniert.

- [Heap-Layout](#_core_heap_layout)

- [Kompilierung](#_core_compilation)

- [Zeiger-Unterstützung](#_core_pointer_support)

- [Optimierungen](#_core_optimizations)

Finden Sie unter den [/GZ (Catch Releasebuildfehlern in der Debugversion)](reference/gz-enable-stack-frame-run-time-error-checking.md) Compileroption für Informationen zum Abfangen von Version Buildfehler in Debugbuilds.

##  <a name="_core_heap_layout"></a> Heap-Layout

Heap-Layout werden die Ursache von ca. 90 Prozent der offensichtlichen Probleme, wenn eine Anwendung debuggen, aber nicht funktioniert.

Wenn Sie Ihr Projekt für das Debuggen erstellen, verwenden Sie die Debug-Speicherreservierungsfunktion. Dies bedeutet, dass alle speicherbelegungen Guard Bytes, die eingeschlossen werden. Diese Guard Bytes ein speicherüberschreibungen zu erkennen. Da Heap-Layout zwischen Release- und Debugkonfigurationen unterscheidet Versionen einer speicherüberschreibungen erstellen u. u. keine Probleme in einem Debugbuild, aber möglicherweise in einem Releasebuild schwerwiegende Auswirkungen.

Weitere Informationen finden Sie unter [prüfen, ob Speicher überschreiben](checking-for-memory-overwrites.md) und [verwenden Sie das Debuggen zu erstellen, überprüfen Sie für die Speicher überschreiben](using-the-debug-build-to-check-for-memory-overwrite.md).

##  <a name="_core_compilation"></a> Kompilierung

Viele der MFC-Makros und einen Großteil der MFC-Implementierung, Änderungen bei der Erstellung für Version. Insbesondere ergibt die ASSERT-Makro "nothing" in einem Releasebuild, damit kein Teil des Codes finden Sie in den Assertionen ausgeführt wird. Weitere Informationen finden Sie unter [ASSERT-Anweisungen untersuchen](using-verify-instead-of-assert.md).

Einige Funktionen sind für höhere Geschwindigkeit im Releasebuild Inline ersetzt. Optimierungen sind in der Regel in einem Releasebuild aktiviert. Außerdem wird eine andere speicherbelegung verwendet.

##  <a name="_core_pointer_support"></a> Zeiger-Unterstützung

Das Fehlen der debugging-Informationen wird die Auffüllung von Ihrer Anwendung entfernt. In einem Releasebuild haben verirrte Zeiger eine größere Chance von nicht initialisiertem Speicher anstelle von Verweisen auf Informationen zu debuggen.

##  <a name="_core_optimizations"></a> Optimierungen

Je nach Art der bestimmte Codesegmente könnte der optimierende Compiler unerwarteten Code generieren. Dies ist die wahrscheinliche Ursache von Problemen mit dem Releasebuild, aber sie gelegentlich auftreten. Für eine Lösung finden Sie unter [optimieren Sie Ihren Code](optimizing-your-code.md).

## <a name="see-also"></a>Siehe auch

[Releasebuilds](release-builds.md)<br/>
[Beheben von Problemen mit dem Releasebuild](fixing-release-build-problems.md)
