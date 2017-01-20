---
title: "Releasebuilds"
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
  - "Debugbuilds, Konvertieren in Releasebuild"
  - "Debuggen [C++], Releasebuilds"
  - "Releasebuilds"
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Releasebuilds
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Releasebuilds verwenden standardmäßig Optimierungen.  Wenn Sie für die Erstellung eines Releasebuilds Optimierungen verwenden, stellt der Compiler keine symbolischen Debuginformationen zur Verfügung.  Das Fehlen symbolischer Debuginformationen sowie die Tatsache, dass für **TRACE**\- und **ASSERT**\-Aufrufe kein Code generiert wird, hat zur Folge, dass die Größe der ausführbaren Datei verringert und die Datei schneller ausgeführt wird.  
  
 Dieser Abschnitt enthält Informationen darüber, weshalb und wann Sie von einem Debugbuild zu einem Releasebuild wechseln können.  Zusätzlich werden einige Probleme behandelt, die bei einem derartigen Wechsel auftreten können.  
  
-   [Erstellen eines Releasebuilds](../../build/reference/how-to-create-a-release-build.md)  
  
-   [Häufig auftretende Probleme beim Erstellen eines Releasebuilds](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)  
  
    -   [Untersuchen von ASSERT\-Anweisungen](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [Verwenden des Debugbuilds zur Suche nach Speicherüberschreibungen](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)  
  
    -   [Debuggen eines Releasebuilds](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [Suchen nach Speicherüberschreibungen](../../build/reference/checking-for-memory-overwrites.md)  
  
## Siehe auch  
 [Erstellen von C\+\+\-Projekten in Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)   
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)