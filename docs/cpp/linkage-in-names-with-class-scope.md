---
title: "Verkn&#252;pfung in Namen mit Klassenbereich | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassennamen [C++], Verknüpfung"
  - "Klassenbereich [C++], Verknüpfung in Namen mit"
  - "Klassen [C++], Namen"
  - "Klassen [C++], Gültigkeitsbereich"
  - "Externe Verknüpfung, Bereich der Verknüpfungsregeln"
  - "Verknüpfung [C++], Bereich der Verknüpfungsregeln"
  - "Namen [C++], Bereich der Verknüpfungsregeln"
  - "Bereich [C++], Klassennamen"
  - "Bereich [C++], Verknüpfungsregeln"
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verkn&#252;pfung in Namen mit Klassenbereich
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Verknüpfungsregeln gelten für Namen mit Klassenbereich:  
  
-   Statische Klassenmember verfügen über externe Verknüpfungen.  
  
-   Klassenmemberfunktionen weisen externe Verknüpfungen auf.  
  
-   Enumeratoren und `typedef`\-Namen haben keine Verknüpfungen.  
  
 **Microsoft\-spezifisch**  
  
-   Die als `friend`\-Funktionen deklarierten Funktionen müssen externe Verknüpfungen aufweisen.  Das Deklarieren einer statischen Funktion als ein `friend` generiert einen Fehler.  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)