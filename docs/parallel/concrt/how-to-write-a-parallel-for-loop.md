---
title: "Gewusst wie: Schreiben einer parallel_for-Schleife | Microsoft Docs"
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
  - "Schreiben einer parallel_for-Schleife [Concurrency Runtime]"
  - "parallel_for-Funktion, Beispiel"
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Schreiben einer parallel_for-Schleife
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird veranschaulicht, wie [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) verwendet wird, um das Produkt von zwei Matrizen zu berechnen.  
  
## Beispiel  
 Das folgende Beispiel zeigt die `matrix_multiply`\-Funktion, die das Produkt von zwei quadratischen Matrizen berechnet.  
  
 [!CODE [concrt-parallel-matrix-multiply#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-matrix-multiply#1)]  
  
## Beispiel  
 Das folgende Beispiel zeigt die `parallel_matrix_multiply`\-Funktion, die den `parallel_for`\-Algorithmus zur parallelen Ausführung der äußeren Schleife verwendet.  
  
 [!CODE [concrt-parallel-matrix-multiply#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-matrix-multiply#2)]  
  
 In diesem Beispiel wird nur die äußere Schleife parallelisiert, da diese genügend Arbeitsvorgänge ausführt, um von dem zusätzlichen Aufwand für die parallele Verarbeitung zu profitieren.  Durch die Parallelisierung der inneren Schleife erzielen Sie keine Leistungssteigerung, da die innere Schleife nicht genügend Arbeitsvorgänge ausführt, um den zusätzlichen Aufwand für die parallele Verarbeitung zu kompensieren.  Daher ist eine Parallelisierung der äußeren Schleife die beste Möglichkeit, die Vorteile der Parallelität in den meisten Systemen zu maximieren.  
  
## Beispiel  
 Im folgenden ausführlicheren Beispiel wird die Leistung der `matrix_multiply`\-Funktion mit der Leistung der `parallel_matrix_multiply`\-Funktion verglichen.  
  
 [!CODE [concrt-parallel-matrix-multiply#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-matrix-multiply#3)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
  **serial: 3853**  
**parallel: 1311**   
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-matrix-multiply.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe \/EHsc parallel\-matrix\-multiply.cpp**  
  
## Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for\-Funktion](../Topic/parallel_for%20Function.md)