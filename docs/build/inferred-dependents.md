---
title: "Hergeleitete abh&#228;ngige Dateien | Microsoft Docs"
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
  - "Abhängige Dateien, Hergeleitet"
  - "Hergeleitete abhängige Elemente in NMAKE"
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Hergeleitete abh&#228;ngige Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine hergeleitete abhängige Datei wird von einer Rückschlussregel abgeleitet und vor expliziten abhängigen Dateien ausgewertet.  Wenn eine hergeleitete abhängige Datei in Bezug auf ihr Ziel nicht mehr aktuell ist, wird von NMAKE der Befehlsblock für die Abhängigkeit aufgerufen.  Wenn eine hergeleitete abhängige Datei nicht vorhanden oder in Bezug auf eigene abhängige Dateien nicht mehr aktuell ist, wird die hergeleitete abhängige Datei zuerst aktualisiert.  Weitere Informationen über hergeleitete abhängige Dateien finden Sie unter [Rückschlussregeln](../build/inference-rules.md).  
  
## Siehe auch  
 [Abhängige Dateien](../build/dependents.md)