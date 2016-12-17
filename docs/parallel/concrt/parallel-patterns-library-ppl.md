---
title: "Parallel Patterns Library (PPL)"
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
  - "Parallel Patterns Library (PPL)"
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "mblome"
manager: "ghogen"
---
# Parallel Patterns Library (PPL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Parallel Patterns Library (PPL) stellt ein obligatorisches Programmiermodell bereit, das die Skalierbarkeit und Benutzerfreundlichkeit beim Entwickeln gleichzeitiger Anwendungen fördert. Die PPL baut auf den Planungs- und Ressourcenverwaltungskomponenten der Concurrency Runtime auf. Sie stuft die Abstraktionebene zwischen dem Anwendungscode und dem zugrunde liegenden Threadingmechanismus herauf, indem sie generische, typsichere Algorithmen und Container bereitstellt, die Daten parallel verarbeiten. Mit der PPL können Sie auch Anwendungen entwickeln, die durch die Bereitstellung von Alternativen zum freigegebenen Status skalieren.  
  
 Die PPL bietet die folgenden Funktionen:  
  
- *Aufgabenparallelität*: ein Mechanismus, der zusätzlich zu den Windows-ThreadPool zur parallelen Ausführung mehrerer Arbeitsaufgaben (Aufgaben)  
  
- *Parallele Algorithmen*: generische Algorithmen, die über die Concurrency Runtime fungieren Auflistungen von Daten parallel funktioniert  
  
- *Parallele Container und Objekte*: generische Containertypen, die sicheren gleichzeitigen Zugriff auf ihre Elemente bieten  
  
## <a name="example"></a>Beispiel  
 Die PPL stellt ein Programmiermodell bereit, das der Standardvorlagenbibliothek (STL) ähnelt. Im folgenden Beispiel werden zahlreiche PPL-Funktionen veranschaulicht. Darin werden mehrere Fibonacci-Zahlen seriell sowie parallel berechnet. Beide Berechnungen werden für eine [Std:: Array](../../standard-library/array-class-stl.md) Objekt. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.  
  
 Die serielle Version mithilfe des STL- [Std:: for_each](../Topic/for_each.md) Algorithmus durchläuft das Array und speichert die Ergebnisse in einem [Std:: vector](vector%20Class.md) Objekt. Die parallele Version führt die gleiche Aufgabe, aber die PPL verwendet [Concurrency:: parallel_for_each](../Topic/parallel_for_each%20Function.md) -Algorithmus und speichert die Ergebnisse in einem [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) Objekt. Die `concurrent_vector`-Klasse aktiviert die einzelnen Schleifeniterationen, Elemente gleichzeitig hinzuzufügen, ohne dass erforderlich ist, den Schreibzugriff auf den Container zu synchronisieren.  
  
 Da `parallel_for_each` gleichzeitig ausführt, muss die parallele Version dieses Beispiels das `concurrent_vector`-Objekt so sortieren, dass die gleichen Ergebnisse wie bei der seriellen Version erzielt werden.  
  
 Beachten Sie, dass in dem Beispiel die Fibonacci-Zahlen mithilfe einer naiven Methode berechnet werden; diese Methode veranschaulicht jedoch, wie die Concurrency Runtime die Leistung bei langen Berechnungen verbessern kann.  
  
 [!CODE [concrt-parallel-fibonacci#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-fibonacci#1)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
```Output  
serial time: 9250 ms  
parallel time: 5726 ms  
 
fib(24): 46368  
fib(26): 121393  
fib(41): 165580141  
fib(42): 267914296  
```  
  
 Jede Iteration der Schleife erfordert eine unterschiedliche Zeit zum Beenden. Die Leistung von `parallel_for_each` wird von der Operation bestimmt, die als Letztes beendet wird. Daher sollten Sie keine linearen Leistungsverbesserungen zwischen den seriellen und parallelen Versionen dieses Beispiels erwarten.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Beschreibt die Rolle von Aufgaben und Aufgabengruppen in der PPL.|  
|[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)|Beschreibt die Verwendung parallele Algorithmen, wie z. B. `parallel_for` und `parallel_for_each`.|  
|[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)|Beschreibt die verschiedenen parallelen Container und die Objekte, die von der PPL bereitgestellt werden.|  
|[Abbruch](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation_in_the_ppl)|Erläutert, wie die von einem parallelen Algorithmus ausgeführte Verarbeitung abgebrochen wird.|  
|[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)|Beschreibt die Concurrency Runtime, die die parallele Programmierung vereinfacht, und stellt Links zu verwandten Themen bereit.|

