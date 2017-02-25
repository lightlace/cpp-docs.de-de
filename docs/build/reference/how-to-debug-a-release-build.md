---
title: "Gewusst wie: Debuggen eines Releasebuilds | Microsoft Docs"
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
  - "Debuggen [C++], Releasebuilds"
  - "Releasebuilds, Debuggen"
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Gewusst wie: Debuggen eines Releasebuilds
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können einen Releasebuild einer Anwendung debuggen.  
  
### So debuggen Sie einen Releasebuild  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Knoten **C\/C\+\+**.  Legen Sie **Debuginformationsformat** auf [C7\-kompatibel \(\/Z7\)](../../build/reference/z7-zi-zi-debug-information-format.md) oder **Programmdatenbank \(\/Zi\)** fest.  
  
3.  Erweitern Sie **Linker**, und klicken Sie auf den Knoten **Allgemein**.  Legen Sie **Inkrementelles Verknüpfen aktivieren** auf [Nein \(\/INCREMENTAL: NO\)](../../build/reference/incremental-link-incrementally.md) fest.  
  
4.  Wählen Sie den Knoten **Debuggen** aus.  Legen Sie **Debuginfo generieren** auf [Ja \(\/DEBUG\)](../../build/reference/debug-generate-debug-info.md) fest.  
  
5.  Wählen Sie den Knoten **Optimierung** aus.  Legen Sie **Verweise** auf [\/OPT:REF](../../build/reference/opt-optimizations.md) und  **COMDAT\-Faltung aktivieren** auf [\/OPT:ICF](../../build/reference/opt-optimizations.md) fest.  
  
6.  Sie können nun das Releasebuild der Anwendung debuggen.  Sie ermitteln ein Problem, indem Sie den Code schrittweise durchlaufen \(oder das Just\-In\-Time\-Debuggen verwenden\), bis Sie die beschädigte Stelle gefunden haben, um dann die falschen Parameter oder den fehlerhaften Code ausfindig zu machen.  
  
     Wenn eine Anwendung in einem Debugbuild funktioniert, in einem Releasebuild jedoch nicht ausgeführt werden kann, legt eine der Compileroptimierungen möglicherweise einen Fehler im Quellcode offen.  Deaktivieren Sie zum Isolieren des Problems die ausgewählten Optimierungen für jede Quellcodedatei, bis Sie die Datei und die Optimierung, durch die das Problem verursacht wird, gefunden haben. \(Zur Beschleunigung des Prozesses können Sie die Dateien in zwei Gruppen unterteilen, die Optimierung für eine Gruppe deaktivieren und bei Auftreten eines Problems in einer Gruppe die Unterteilung so lange fortsetzen, bis Sie die problematische Datei isoliert haben.\)  
  
     Sie können auch [\/RTC](../../build/reference/rtc-run-time-error-checks.md) verwenden, um solche Fehler in Debugbuilds offen zu legen.  
  
     Weitere Informationen finden Sie unter [Codeoptimierung](../../build/reference/optimizing-your-code.md).  
  
## Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)