---
title: "3.2 Lock Functions"
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
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2 Lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Funktionen, die in diesem Abschnitt beschriebenen Sperren für die Synchronisierung verwendeten bearbeiten.  
  
 Für die folgenden Funktionen muss die Sperren variable Typ **omp\_lock\_t**haben.  Diese Variable muss durch diese Funktionen nur zugegriffen werden.  Alle Sperren von Funktionen erfordern ein Argument, das einen Zeiger auf **omp\_lock\_t**\-Typ verfügt.  
  
-   Die Funktion `omp_init_lock` eine einfache Zuweisung.  
  
-   Die `omp_destroy_lock`\-Funktion entfernt eine einfache Zuweisung.  
  
-   Die `omp_set_lock`\-Funktion wartet, bis eine einfache Sperre verfügbar ist.  
  
-   Die `omp_unset_lock` function gibt eine einfache Sperre.  
  
-   Die Funktion `omp_test_lock` Tests eine einfache Zuweisung.  
  
 Für die folgenden Funktionen muss die Sperren variable Typ **omp\_nest\_lock\_t**haben.  Diese Variable muss durch diese Funktionen nur zugegriffen werden.  Alle Features der schachtelbaren Sperren erfordern ein Argument, das einen Zeiger auf **omp\_nest\_lock\_t**\-Typ verfügt.  
  
-   Die `omp_init_nest_lock` eine Funktion schachtelbare Sperre.  
  
-   Die `omp_destroy_nest_lock`\-Funktion entfernt eine schachtelbare Sperre.  
  
-   Die `omp_set_nest_lock`\-Funktion wartet, bis eine schachtelbare Sperre verfügbar ist.  
  
-   Die `omp_unset_nest_lock` function gibt eine schachtelbare Sperre.  
  
-   Die Funktion `omp_test_nest_lock` Tests eine schachtelbare Sperre.  
  
 Die Funktionen OpenMP\-Sperren greifen auf die Sperren auf die Variable stets, dass sie lesen und den aktuellsten Wert der Sperren variable aktualisieren.  Daher ist es nicht notwendig für ein OpenMP\-Programm explizite **leer**\-Direktive einzufügen, um sicherzustellen, dass der Wert der Sperren variable unter verschiedenen Threads konsistent ist.  \(Es gibt möglicherweise eine Anforderung, für **leer**\-Direktive die Werte von anderen Variablen\) machen konsistent.