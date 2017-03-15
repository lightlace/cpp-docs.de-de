---
title: "Schwerwiegender Fehler C1002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1002"
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kein Heapspeicher für Compiler im 2. Durchlauf mehr verfügbar  
  
 Dem Compiler stand während des zweiten Durchlaufs möglicherweise aufgrund eines Programms mit zu vielen Symbolen oder komplexen Ausdrücken nicht genügend dynamischer Arbeitsspeicher zur Verfügung.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Unterteilen Sie die Quelldatei in mehrere kleinere Dateien.  
  
2.  Teilen Sie Ausdrücke in kleinere Teilausdrücke auf.  
  
3.  Entfernen Sie andere Programme oder Treiber, die Arbeitsspeicher belegen.