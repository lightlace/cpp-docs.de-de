---
title: "Gewusst wie: Kombinieren von Gruppen mithilfe von combinable"
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
helpviewer_keywords: 
  - "combinable-Klasse, Beispiel"
  - "Kombinieren von Sätzen mit Combinable [Concurrency Runtime]"
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
caps.latest.revision: 14
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Kombinieren von Gruppen mithilfe von combinable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die Verwendung der [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)\-Klasse zum Berechnen der Primzahlengruppe beschrieben.  
  
## Beispiel  
 Im folgenden Beispiel wird die Primzahlengruppe zweimal berechnet.  Bei jeder Berechnung wird das Ergebnis in einem [std::bitset](../../standard-library/bitset-class.md)\-Objekt gespeichert.  Im Beispiel wird die Primzahlengruppe zunächst seriell und anschließend parallel berechnet.  Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.  
  
 In diesem Beispiel werden zum Berechnen von lokalen Threadgruppen der [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)\-Algorithmus und ein `combinable`\-Objekt verwendet.  Anschließend werden die lokalen Threadgruppen mithilfe der [concurrency::combine\_each](../Topic/combinable::combine_each%20Method.md)\-Methode zu einer endgültigen Gruppe gruppiert.  
  
 [!CODE [concrt-parallel-combine-primes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-combine-primes#1)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
  **serielle Uhrzeit: 312 ms**  
**parallele Uhrzeit: 78 ms**   
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `parallel-combine-primes.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc parallel\-combine\-primes.cpp**  
  
## Siehe auch  
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable\-Klasse](../../parallel/concrt/reference/combinable-class.md)   
 [combinable::combine\_each\-Methode](../Topic/combinable::combine_each%20Method.md)