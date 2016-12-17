---
title: "Verwenden des Debugbuilds zur Suche nach Speicher&#252;berschreibungen"
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
  - "Speicher, Überschreibungen"
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden des Debugbuilds zur Suche nach Speicher&#252;berschreibungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um das Debugbuild zur Suche nach Speicherüberschreibungen verwenden zu können, müssen Sie das Projekt zunächst als Debugbuild neu erstellen.  Suchen Sie dann den Anfang der `InitInstance`\-Funktion in der Anwendung, und fügen Sie die folgende Zeile hinzu:  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 Die Debug\-Speicherbelegungsfunktion umgibt alle belegten Speicherbereiche mit Schutzbytes.  Diese Schutzbytes sind jedoch nur dann von Nutzen, wenn Sie überprüfen, ob sie geändert wurden \(was auf eine Speicherüberschreibung hindeuten würde\).  Andererseits stellen die Schutzbytes auch einen Puffer dar, durch den eine Speicherüberschreibung u. U. noch toleriert werden kann.  
  
 Durch Aktivieren von `checkAlwaysMemDF` können Sie erzwingen, dass bei jedem Aufruf von **new** oder **delete** die `AfxCheckMemory`\-Funktion von MFC aufgerufen wird.  Im Falle einer Speicherüberschreibung wird eine mit der folgenden Meldung vergleichbare **TRACE**\-Meldung generiert:  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Wenn eine dieser Meldungen angezeigt wird, müssen Sie den Code durchlaufen, um die beschädigte Stelle zu ermitteln.  Um die Speicherüberschreibung noch genauer zu isolieren, können Sie `AfxCheckMemory` auch selbst explizit aufrufen.  Beispiel:  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 Wenn die erste **ASSERT**\-Anweisung erfolgreich ist, die zweite jedoch fehlschlägt, bedeutet dies, dass die Speicherüberschreibung zwischen den beiden Aufrufen stattgefunden haben muss.  
  
 Je nach Art der Anwendung kann es vorkommen, dass das Programm aufgrund von `afxMemDF` selbst für einen Debugvorgang zu langsam ausgeführt wird.  Die `afxMemDF`\-Variable bewirkt, dass bei jedem Aufruf von **new** und **delete** die `AfxCheckMemory`\-Funktion aufgerufen wird.  In diesem Fall sollten Sie Ihre eigenen Aufrufe von `AfxCheckMemory`\( \), wie oben gezeigt, verteilt einsetzen und dadurch versuchen, die Speicherüberschreibung zu isolieren.  
  
## Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)