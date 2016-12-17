---
title: "Hergeleitete abh&#228;ngige Dateien und Regeln"
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
  - "Abhängige Dateien, Hergeleitet"
  - "Hergeleitete abhängige Elemente in NMAKE"
  - "Hergeleitete Regeln in NMAKE"
  - "Regeln, Hergeleitet"
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Hergeleitete abh&#228;ngige Dateien und Regeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE geht von einer hergeleiteten abhängigen Datei als einem Ziel aus, wenn eine anwendbare Rückschlussregel vorhanden ist.  Eine Regel ist anwendbar, wenn:  
  
-   *toext* mit der Erweiterung des Ziels übereinstimmt.  
  
-   *fromext* mit der Erweiterung einer Datei übereinstimmt, die den Basisnamen des Ziels aufweist und im aktuellen oder angegebenen Verzeichnis vorhanden ist.  
  
-   *fromext* ist in [.SUFFIXES](../build/dot-directives.md) aufgelistet; keine andere mit *fromext* übereinstimmende Regel besitzt eine höhere **.SUFFIXES**\-Priorität.  
  
-   Keine andere explizite abhängige Datei besitzt eine höhere **.SUFFIXES**\-Priorität.  
  
 Hergeleitete abhängige Dateien können unerwartete Nebeneffekte verursachen.  Wenn der Beschreibungsblock des Ziels Befehle enthält, werden diese Befehle von NMAKE anstelle der Befehle in der Regel ausgeführt.  
  
## Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)