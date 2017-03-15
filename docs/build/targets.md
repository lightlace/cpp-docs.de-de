---
title: "Ziele | Microsoft Docs"
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
  - "Ziele, Angeben in NMAKE"
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ziele
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Abhängigkeitszeile wird mindestens ein Ziel angegeben, indem ein gültiger Dateiname, ein Verzeichnisname oder ein [Pseudoziel](../build/pseudotargets.md) verwendet wird.  Mehrere Ziele werden durch ein oder mehrere Leerzeichen oder Tabstopps getrennt.  Bei Zielen wird die Groß\-\/Kleinschreibung nicht beachtet.  Pfade mit Dateinamen sind zulässig.  Ein Ziel darf 256 Zeichen nicht überschreiten.  Besteht das Ziel vor dem Doppelpunkt aus einem einzelnen Zeichen, wird ein trennendes Leerzeichen verwendet. Andernfalls wird die Kombination aus Buchstabe und Doppelpunkt von NMAKE als Laufwerkbuchstabe interpretiert.  
  
## Worüber möchten Sie mehr erfahren?  
 [Pseudoziele](../build/pseudotargets.md)  
  
 [Mehrere Ziele](../build/multiple-targets.md)  
  
 [Kumulative Abhängigkeiten](../build/cumulative-dependencies.md)  
  
 [Ziele in mehreren Beschreibungsblöcken](../build/targets-in-multiple-description-blocks.md)  
  
 [Nebeneffekte bei Abhängigkeiten](../build/dependency-side-effects.md)  
  
## Siehe auch  
 [Beschreibungsblöcke](../build/description-blocks.md)