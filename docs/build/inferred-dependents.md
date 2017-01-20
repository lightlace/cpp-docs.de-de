---
title: "Hergeleitete abh&#228;ngige Dateien"
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
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Hergeleitete abh&#228;ngige Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine hergeleitete abhängige Datei wird von einer Rückschlussregel abgeleitet und vor expliziten abhängigen Dateien ausgewertet.  Wenn eine hergeleitete abhängige Datei in Bezug auf ihr Ziel nicht mehr aktuell ist, wird von NMAKE der Befehlsblock für die Abhängigkeit aufgerufen.  Wenn eine hergeleitete abhängige Datei nicht vorhanden oder in Bezug auf eigene abhängige Dateien nicht mehr aktuell ist, wird die hergeleitete abhängige Datei zuerst aktualisiert.  Weitere Informationen über hergeleitete abhängige Dateien finden Sie unter [Rückschlussregeln](../build/inference-rules.md).  
  
## Siehe auch  
 [Abhängige Dateien](../build/dependents.md)