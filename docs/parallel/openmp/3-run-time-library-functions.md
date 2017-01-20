---
title: "3. Run-Time Library-Funktionen"
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
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3. Run-Time Library-Funktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieser Abschnitt beschreibt die Funktionen der OpenMP-C- und C++-Laufzeitbibliothek. Der Header **\< comp.h >** deklariert zwei Typen, die verschiedene Funktionen zum Steuern und Abfragen die parallele ausführungsumgebung und Sperren von Funktionen, die zum Synchronisieren des Zugriffs auf Daten verwendet werden können.  
  
 Der Typ **Omp_lock_t** ist ein Objekt ausgedrückt werden können, dass eine Sperre verfügbar ist, oder ein Thread eine Sperre besitzt. Diese Sperren werden als bezeichnet *einfache Sperren*.  
  
 Der Typ **aufgerufen** wird ein Objekttyp ausgedrückt werden können, dass eine Sperre verfügbar oder sowohl die Identität des Threads, die die Sperre besitzt und eine *Schachteln von Count* (siehe unten). Diese Sperren werden als bezeichnet *von schachtelbaren Sperren*.  
  
 Die Bibliotheksfunktionen weisen externe Funktionen mit C-Bindung.  
  
 Die Beschreibungen in diesem Kapitel sind in den folgenden Themen unterteilt:  
  
-   Ausführungsumgebungsfunktionen (siehe [Abschnitt 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) auf Seite 35).  
  
-   Sperren von Funktionen (siehe [Abschnitt 3.2](../../parallel/openmp/3-2-lock-functions.md) auf Seite 41).