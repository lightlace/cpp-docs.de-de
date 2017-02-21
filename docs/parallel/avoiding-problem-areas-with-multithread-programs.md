---
title: "Vermeiden von Problembereichen bei Multithreadprogrammen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fehler [C++], Multithreadprogramme"
  - "Multithreading [C++], Problembehandlung"
  - "Threading [C++], Problembehandlung"
  - "Problembehandlung [C++], Multithreading"
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Vermeiden von Problembereichen bei Multithreadprogrammen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der Erstellung, Bindung oder Ausführung eines C\-Multithreadprogramms können verschiedene Probleme auftreten.  Einige der allgemeineren Probleme werden in der folgenden Tabelle beschrieben. \(Eine vergleichbare Erläuterung in Bezug auf MFC finden Sie unter [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md).\)  
  
|Problem|Mögliche Ursache|  
|-------------|----------------------|  
|Es wird eine Meldung ausgegeben, der zufolge durch das Programm eine allgemeine Schutzverletzung verursacht wurde.|Durch viele Win32\-Programmierfehler werden allgemeine Schutzverletzungen verursacht.  Eine häufige Ursache für allgemeine Schutzverletzungen ist die indirekte Zuweisung von Daten zu NULL\-Zeigern.  Da dies dazu führt, dass ein Programm versucht, auf Speicher zuzugreifen, der ihm nicht zugewiesen ist, wird eine allgemeine Schutzverletzung verursacht.<br /><br /> Die Ursache einer allgemeinen Schutzverletzung lässt sich am einfachsten ermitteln, indem Sie ein Programm mit Debuginformationen kompilieren und es anschließend in der Visual C\+\+\-Umgebung mit dem Debugger überprüfen.  Wenn der Schutzverletzungsfehler auftritt, übergibt Windows die Steuerung an den Debugger, und der Cursor wird in der Zeile positioniert, durch die das Problem verursacht wurde.|  
|Ein Programm generiert zahlreiche Fehler beim Kompilieren und Binden.|Sie können viele potenzielle Probleme beseitigen, indem Sie die Warnstufe des Compilers auf einen der höchsten Werte einstellen und die Warnungen beachten.  Mit den Warnstufen 3 oder 4 lassen sich unbeabsichtigte Datenkonvertierungen, fehlende Funktionsprototypen und die Verwendung von Nicht\-ANSI\-Funktionen feststellen.|  
  
## Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)