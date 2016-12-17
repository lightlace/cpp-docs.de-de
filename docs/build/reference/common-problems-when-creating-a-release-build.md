---
title: "H&#228;ufig auftretende Probleme beim Erstellen eines Releasebuilds"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Debugbuilds, Unterschied zu Releasebuilds"
  - "Debug-Speicherreservierungsfunktion"
  - "Debuggen [MFC], Releasebuilds"
  - "Heap-Layoutprobleme"
  - "Speicher [C++], Überschreibungen"
  - "MFC [C++], Releasebuilds"
  - "Optimierung [C++], Compiler"
  - "Zeiger, Verirrt"
  - "Projekte [C++], Debugkonfiguration"
  - "Releasebuilds, Erstellen von Anwendungen"
  - "Releasebuilds, Problembehandlung"
  - "Verirrte Zeiger"
  - "Problembehandlung bei Releasebuilds"
  - "Problembehandlung in Visual C++"
  - "Unerwartete Codegenerierung"
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# H&#228;ufig auftretende Probleme beim Erstellen eines Releasebuilds
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Während der Entwicklung werden Sie zum Erstellen und Testen in der Regel ein Debugbuild des Projekts verwenden.  Wenn Sie dann die Anwendung in ein Releasebuild umwandeln, kann u. U. eine Zugriffsverletzung auftreten.  
  
 In der nachfolgenden Liste sind die Hauptunterschiede zwischen einem Debugbuild und einem Releasebuild aufgeführt.  Obwohl es noch mehr Unterschiede gibt, sind im Folgenden die Hauptunterschiede aufgelistet, die dazu führen können, dass eine Anwendung im Releasebuild fehlschlägt, obwohl sie im Debugbuild fehlerfrei arbeitet.  
  
-   [Heaplayout](#_core_heap_layout)  
  
-   [Kompilierung](#_core_compilation)  
  
-   [Zeigerunterstützung](#_core_pointer_support)  
  
-   [Optimierungen](#_core_optimizations)  
  
 Weitere Informationen über das Abfangen von Releasebuildfehlern im Debugbuild finden Sie unter der Compileroption [\/GZ \(Laufzeitfehlerüberprüfung für Stapelrahmen aktivieren\)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md).  
  
##  <a name="_core_heap_layout"></a> Heaplayout  
 Wenn eine Anwendung als Debugbuild, nicht aber als Releasebuild fehlerfrei ausgeführt wird, liegt der Grund in neunzig Prozent aller Fälle beim Heaplayout.  
  
 Wenn Sie das Projekt für das Debuggen erstellen, verwenden Sie die Debug\-Speicherbelegungsfunktion.  Das bedeutet, dass alle Speicherbelegungen mit Schutzbytes umgeben werden.  Durch diese Schutzbytes werden Speicherüberschreibungen ermittelt.  Da Releasebuilds und Debugbuilds über unterschiedliche Heaplayouts verfügen, kann es vorkommen, dass eine Speicherüberschreibung in einem Debugbuild keinerlei Probleme verursacht, in einem Releasebuild jedoch drastische Auswirkungen hat.  
  
 Weitere Informationen finden Sie unter [Suchen nach Speicherüberschreibungen](../../build/reference/checking-for-memory-overwrites.md) und [Verwenden des Debugbuilds zur Suche nach Speicherüberschreibungen](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md).  
  
##  <a name="_core_compilation"></a> Kompilierung  
 Zahlreiche MFC\-Makros und ein großer Teil der MFC\-Implementierung ändern sich, wenn Sie ein Releasebuild erstellen.  Insbesondere nimmt das **ASSERT**\-Makro in einem Releasebuild keine Auswertung vor, sodass kein **ASSERT**\-Code ausgeführt wird.  Weitere Informationen finden Sie unter [Untersuchen von ASSERT\-Anweisungen](../../build/reference/using-verify-instead-of-assert.md).  
  
 Einige Funktionen werden im Releasebuild implementiert, um die Verarbeitungsgeschwindigkeit als Inlinecode zu erhöhen.  Optimierungen werden im Releasebuild in der Regel aktiviert.  Außerdem wird eine andere Speicherbelegungsfunktion verwendet.  
  
##  <a name="_core_pointer_support"></a> Zeigerunterstützung  
 Durch das Fehlen von Debuginformationen wird eine Art Schutzhülle aus der Anwendung entfernt.  Daher ist es in einem Releasebuild wahrscheinlicher, dass "verirrte" Zeiger auf nicht initialisierten Speicher statt auf Debuginformationen zeigen.  
  
##  <a name="_core_optimizations"></a> Optimierungen  
 Je nach der Art bestimmter Codesegmente kann der optimierende Compiler unerwarteten Code generieren.  Obwohl diese Situation relativ selten eintritt, kann sie gelegentlich zu Problemen mit dem Releasebuild führen.  Unter [Codeoptimierung](../../build/reference/optimizing-your-code.md) finden Sie einen Lösungsansatz.  
  
## Siehe auch  
 [Releasebuilds](../../build/reference/release-builds.md)   
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)