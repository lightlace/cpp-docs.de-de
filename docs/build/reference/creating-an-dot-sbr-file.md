---
title: "Erstellen einer SBR-Datei"
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
  - ".sbr-Dateien"
  - "BSCMAKE, Eingabedateien"
  - "Lokale Symbole in den Browseinformationen"
  - "SBR-Dateien"
  - "Quellbrowserdateien"
  - "Symbole"
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen einer SBR-Datei
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SBR\-Dateien stellen die Eingabedateien für BSCMAKE dar.  Der Compiler legt für jede kompilierte Objektdatei \(.obj\) eine SBR\-Datei an.  Wenn Sie die Browserinformationsdatei erstellen oder aktualisieren möchten, müssen alle SBR\-Dateien für das Projekt auf dem Datenträger verfügbar sein.  
  
 Um eine SBR\-Datei mit allen möglichen Informationen zu erstellen, geben Sie [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) an.  
  
 Um eine SBR\-Datei zu erstellen, die keine lokalen Symbole enthält, geben Sie [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) an.  Wenn die SBR\-Dateien lokale Symbole enthalten, können Sie diese dennoch mit der [\/El\-Option](../../build/reference/bscmake-options.md) von BSCMAKE aus der BSC\-Datei ausschließen`.`  
  
 Eine SBR\-Datei kann ohne eine vollständige Kompilierung erstellt werden.  Beispielsweise können Sie den Compiler mit der \/Zs\-Option veranlassen, eine Syntaxprüfung auszuführen, und dennoch durch Angabe von \/FR oder \/Fr eine SBR\-Datei generieren.  
  
 Der Erstellungsprozess kann effizienter sein, wenn die SBR\-Dateien zunächst gepackt werden. So können Definitionen, auf die nicht verwiesen wird, entfernt werden.  Der Compiler packt SBR\-Dateien automatisch.  
  
## Siehe auch  
 [Erstellen einer BSC\-Datei](../../build/reference/building-a-dot-bsc-file.md)