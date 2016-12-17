---
title: "OpenMP Clauses"
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
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Clauses
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Enthält Links zu den Klauseln bereit, die im OpenMP API verwendet werden.  
  
 Visual C\+\+ unterstützt die folgenden OpenMP\-Klauseln:  
  
|Klausel|Beschreibung|  
|-------------|------------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|Ermöglicht Threads, um den Wert des Masterthreads, für eine [threadprivate](../../../parallel/openmp/reference/threadprivate.md)\-Variable zuzugreifen.|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Gibt an, dass eine oder mehrere Variablen mit allen Threads freigegeben werden sollen.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|Gibt das Verhalten von unscoped Variablen in einem parallelen Bereich an.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Gibt an, dass jeder Thread seine eigene Instanz einer Variablen zugewiesen werden soll, und dass die Variable mit dem Wert der Variable initialisiert werden soll, da sie vor dem parallelen Konstrukt vorhanden ist.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|Gibt an, ob eine Schleife in der Serie oder parallel ausgeführt werden sollte.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Gibt an, dass die einschließende Version des Kontexts der Variablen gleich der private Version von festgelegt wird, welcher Thread die letzte Iteration \(for\-Schleifen\-Konstrukt\) oder letzten Abschnitt ausführt \(\#pragma Abschnitten\).|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|Überschreibt die Barriere, die in Direktive implizit ist.|  
|[num\_threads](../../../parallel/openmp/reference/num-threads.md)|Legt die Anzahl von Threads in einem Team Thread fest.|  
|[ordered](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Erforderlich auf einer parallelen [for](../../../parallel/openmp/reference/for-openmp.md)\-Anweisung, wenn [ordered](../../../parallel/openmp/reference/ordered-openmp-directives.md)\-Direktive in der Schleife verwendet werden sollen.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|Gibt an, dass jeder Thread seine eigene Instanz einer Variablen zugewiesen werden soll.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|Gibt an, dass eine oder mehrere Variablen, die für jeden Thread privat sind, den Betreff am Ende des Vorgangs Reduzierungs eines parallelen Bereichs liegen.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|Wendet [for](../../../parallel/openmp/reference/for-openmp.md) die Direktive an.|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|Gibt an, dass eine oder mehrere Variablen mit allen Threads freigegeben werden sollen.|  
  
## Siehe auch  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)