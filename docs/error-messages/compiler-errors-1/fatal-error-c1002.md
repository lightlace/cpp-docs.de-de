---
title: "Schwerwiegender Fehler C1002"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1002"
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kein Heapspeicher für Compiler im 2. Durchlauf mehr verfügbar  
  
 Dem Compiler stand während des zweiten Durchlaufs möglicherweise aufgrund eines Programms mit zu vielen Symbolen oder komplexen Ausdrücken nicht genügend dynamischer Arbeitsspeicher zur Verfügung.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Unterteilen Sie die Quelldatei in mehrere kleinere Dateien.  
  
2.  Teilen Sie Ausdrücke in kleinere Teilausdrücke auf.  
  
3.  Entfernen Sie andere Programme oder Treiber, die Arbeitsspeicher belegen.