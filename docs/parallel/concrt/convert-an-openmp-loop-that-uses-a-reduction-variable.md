---
title: "Gewusst wie: Konvertieren einer OpenMP-Schleife, in der eine reduction-Variable verwendet wird, zur Verwendung der Concurrency Runtime"
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
  - "Konvertierung von OpenMP in die Concurrency Runtime, reduction-Variablen"
  - "reduction-Variablen, Konvertierung von OpenMP in die Concurrency Runtime"
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
caps.latest.revision: 13
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Konvertieren einer OpenMP-Schleife, in der eine reduction-Variable verwendet wird, zur Verwendung der Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird gezeigt, wie eine OpenMP\-[parallel](../../parallel/openmp/reference/parallel.md) [for](../../parallel/openmp/reference/for-openmp.md)\-Schleife, in der die [reduction](../../parallel/openmp/reference/reduction.md)\-Klausel verwendet wird, für die Verwendung der Concurrency Runtime konvertiert wird.  
  
 Mit der OpenMP\-`reduction`\-Klausel können Sie eine oder mehrere private Variablen im Thread angeben, auf die am Ende des parallelen Bereichs ein Reduzierungsvorgang angewendet wird.  OpenMP enthält einen Satz vordefinierter Reduzierungsoperatoren.  Jede Reduzierungsvariable muss ein Skalar sein \(z. B. `int`, `long` und `float`\).  OpenMP definiert außerdem einige Einschränkungen für die Verwendung von Reduzierungsvariablen in einem parallelen Bereich.  
  
 Die Parallel Patterns Library \(PPL\) stellt die [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)\-Klasse bereit, die einen wiederverwendbaren lokalen Threadspeicher bietet, mit dem Sie differenzierte Berechnungen ausführen und diese dann zu einem Endergebnis zusammenführen können.  Die `combinable`\-Klasse ist eine Vorlage, die sowohl auf skalare als auch auf komplexe Typen angewendet wird.  Führen Sie für die Verwendung der `combinable`\-Klasse Unterberechnungen im Text eines parallelen Konstrukts aus, und rufen Sie dann die [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md)\-Methode oder die [concurrency::combinable::combine\_each](../Topic/combinable::combine_each%20Method.md)\-Methode auf, um das Endergebnis zu erzeugen.  Die `combine`\-Methode und die `combine_each`\-Methode akzeptieren jeweils eine *combine\-Funktion*, die angibt, wie jedes Elementpaar kombiniert wird.  Daher ist die `combinable`\-Klasse nicht auf einen festen Satz von Reduzierungsoperatoren beschränkt.  
  
## Beispiel  
 In diesem Beispiel wird mit OpenMP und der Concurrency Runtime die Summe der ersten 35 Fibonacci\-Zahlen berechnet.  
  
 [!CODE [concrt-openmp#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-openmp#7)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Using OpenMP...**  
**The sum of the first 35 Fibonacci numbers is 14930351.**  
**Using the Concurrency Runtime...**  
**The sum of the first 35 Fibonacci numbers is 14930351.** Weitere Informationen über die `combinable`\-Klasse finden Sie unter [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `concrt-omp-fibonacci-reduction.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-fibonacci\-reduction.cpp**  
  
## Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)