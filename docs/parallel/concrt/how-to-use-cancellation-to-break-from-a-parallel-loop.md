---
title: "Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife | Microsoft Docs"
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
  - "Paralleler Suchalgorithmus, Schreiben [Concurrency Runtime]"
  - "Schreiben eines parallelen Suchalgorithmus [Concurrency Runtime]"
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie Abbrüche verwendet, um einen einfachen Algorithmus paralleler Suchalgorithmus implementiert wird.  
  
## Beispiel  
 Das folgende Beispiel verwendet das Abbrechen, um in einem Array nach einem Element zu suchen.  Die Funktion `parallel_find_any` wird der Algorithmus [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) und die [concurrency::run\_with\_cancellation\_token](../Topic/run_with_cancellation_token%20Function.md)\-Funktion, die die Position zu suchen, die den angegebenen Wert enthält.  Wenn von der parallelen Schleife den Wert ermittelt, ruft sie die [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md)\-Methode auf, um die weitere Verarbeitung abzubrechen.  
  
 [!CODE [concrt-parallel-array-search#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-array-search#1)]  
  
 Der [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) \- Algorithmus handelt gleichzeitig.  Daher führt er die Operationen nicht in einer vorgegebenen Reihenfolge aus.  Wenn das Array mehrere Instanzen des Werts enthält, kann das Ergebnis eine beliebige seiner Positionen sein.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-array-search.cpp` ein, und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderung ausgeführt.  
  
 **cl.exe \/EHsc parallel\-array\-search.cpp**  
  
## Siehe auch  
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for\-Funktion](../Topic/parallel_for%20Function.md)   
 [cancellation\_token\_source\-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)