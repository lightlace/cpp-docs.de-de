---
title: Häufig auftretende Probleme beim Erstellen eines Releasebuilds | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8860783a2cf9fb88b28e24e0bc16eb16c0dd5d77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373165"
---
# <a name="common-problems-when-creating-a-release-build"></a>Häufig auftretende Probleme beim Erstellen eines Releasebuilds
Während der Entwicklung können Sie in der Regel erstellen und Testen mit einem Debugbuild des Projekts. Wenn Sie dann die Anwendung für einen Releasebuild erstellen, erhalten Sie möglicherweise eine zugriffsverletzung.  
  
 Die folgende Liste zeigt die primären Unterschiede zwischen einem Debug- und Releasebuilds (aufgeführt). Andere Unterschiede bestehen, aber es folgen die wichtigsten Unterschiede, die eine Anwendung fehlschlagen in einem Releasebuild führen würde, wenn es in einem Debugbuild funktioniert.  
  
-   [Heap-Layout](#_core_heap_layout)  
  
-   [Kompilierung](#_core_compilation)  
  
-   [Zeiger-Unterstützung](#_core_pointer_support)  
  
-   [Optimierungen](#_core_optimizations)  
  
 Finden Sie unter der [/GZ (Catch Releasebuildfehlern in der Debugversion)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) Compileroption Informationen zum Abfangen von Version Buildfehler in Debugbuilds.  
  
##  <a name="_core_heap_layout"></a> Heap-Layout  
 Heap Layout werden die Fehlerursache zu über 90 Prozent der offensichtlichen Probleme, wenn eine Anwendung debuggen, jedoch nicht Version funktioniert.  
  
 Wenn Sie Ihr Projekt für das Debuggen erstellen, verwenden Sie das Debug-Speicherreservierungsfunktion. Dies bedeutet, dass alle speicherbelegungen Guard Bytes darum platziert haben. Diese Guard Bytes erkennen eine Speicher-Überschreibung. Da der Heap Layout zwischen Release- und Debugkonfigurationen unterscheidet Versionen Überschreiben einer Arbeitsspeicher möglicherweise keine Probleme in einem Debugbuild erstellt, aber möglicherweise schwerwiegende Auswirkungen in ein Releasebuild erstellt werden.  
  
 Weitere Informationen finden Sie unter [prüfen, ob Arbeitsspeicher überschreiben](../../build/reference/checking-for-memory-overwrites.md) und [verwenden das Debuggen erstellen, überprüfen Sie, für Arbeitsspeicher überschreiben](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md).  
  
##  <a name="_core_compilation"></a> Kompilierung  
 Viele der MFC-Makros sowie der Großteil der MFC-implementierungsänderungen beim Erstellen eines Version. Insbesondere wird die ASSERT-Makro zu "nothing" in einem Releasebuild kann ausgewertet, damit keine der Code, der in ASSERTs ausgeführt wird. Weitere Informationen finden Sie unter [ASSERT-Anweisungen untersuchen](../../build/reference/using-verify-instead-of-assert.md).  
  
 Einige Funktionen sind für höhere Geschwindigkeit im Releasebuild Inline. Optimierungen sind in der Regel in einem Releasebuild aktiviert. Außerdem wird eine andere Speicherbelegungsfunktion verwendet.  
  
##  <a name="_core_pointer_support"></a> Zeiger-Unterstützung  
 Das fehlen Debuginformationen entfernt die Auffüllung von Ihrer Anwendung. In einem Releasebuild haben verirrte Zeiger erhöht die Wahrscheinlichkeit auf nicht initialisierter Speicher, sondern zeigt Informationen zu debuggen.  
  
##  <a name="_core_optimizations"></a> Optimierungen  
 Je nach Art der bestimmte Codesegmente möglicherweise die Optimierungscompiler unerwarteten Code generieren. Dies ist die am wenigsten wahrscheinlichen Ursache von Problemen mit dem Releasebuild, aber es in manchen Fällen auftreten. Eine Lösung finden Sie unter [des Codes optimieren](../../build/reference/optimizing-your-code.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Releasebuilds](../../build/reference/release-builds.md)   
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)