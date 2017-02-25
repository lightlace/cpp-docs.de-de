---
title: "Pseudoziele | Microsoft Docs"
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
  - "Makefiles, Pseudoziele"
  - "NMAKE (Programm), Pseudoziele"
  - "NMAKE (Programm), Ziele"
  - "Pseudoziele und NMAKE"
  - "Timestamps, Makefile-Pseudoziele"
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Pseudoziele
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Pseudoziel stellt eine Bezeichnung dar, die an Stelle eines Dateinamens in einer Abhängigkeitszeile verwendet wird.  Sie wird als nicht vorhandene Datei und somit als nicht mehr aktuell interpretiert.  NMAKE geht davon aus, dass es sich bei dem Timestamp des Pseudoziels um den aktuellsten der abhängigen Dateien handelt.  Wenn es keine abhängigen Dateien besitzt, wird von der aktuellen Uhrzeit ausgegangen.  Wenn ein Pseudoziel als Ziel verwendet wird, werden dessen Befehle immer ausgeführt.  Ein Pseudoziel, das als abhängige Datei verwendet wird, muss auch als Ziel in einer anderen Abhängigkeit verwendet werden.  Für diese Abhängigkeit ist jedoch kein Befehlsblock notwendig.  
  
 Für Namen von Pseudozielen gelten die Syntaxregeln für Ziele.  Wenn der Name jedoch keine Erweiterung \(d. h. keinen Punkt\) besitzt, kann die 8\-Zeichen\-Grenze für Dateinamen überschritten werden, und der Name kann bis zu 256 Zeichen lang sein.  
  
## Siehe auch  
 [Ziele](../build/targets.md)