---
title: "Gewusst wie: Erh&#246;hen der Effizienz mithilfe von parallelen Containern"
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
  - "Verbessern der Effizienz mit parallelen Containern [Concurrency Runtime]"
  - "concurrent_queue-Klasse, Beispiele"
  - "concurrent_vector-Klasse, Beispiele"
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
caps.latest.revision: 13
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erh&#246;hen der Effizienz mithilfe von parallelen Containern
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird aufgezeigt, wie parallele Container verwendet werden, um Daten effizient zu speichern und parallel auf sie zuzugreifen.  
  
 Im Beispielcode werden der Satz von Primzahlen und Carmichael\-Zahlen parallel berechnet.  Anschließend berechnet der Code für jede Carmichael\-Zahl die Primfaktoren dieser Zahl.  
  
## Beispiel  
 Im folgenden Beispiel wird die `is_prime`\-Funktion gezeigt, durch die bestimmt wird, ob ein Eingabewert eine Primzahl ist, und die `is_carmichael`\-Funktion, durch die bestimmt wird, ob der Eingabewert eine Carmichael\-Zahl ist.  
  
 [!CODE [concrt-carmichael-primes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-carmichael-primes#1)]  
  
## Beispiel  
 Im folgenden Beispiel werden die Funktionen `is_prime` und `is_carmichael` zum Berechnen der Sätze von Primzahlen und Carmichael\-Zahlen verwendet.  Im Beispiel werden der [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md)\-Algorithmus und der [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)\-Algorithmus zum parallelen Berechnen der einzelnen Sätze verwendet.  Weitere Informationen zu parallelen Algorithmen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 In diesem Beispiel wird ein [concurrency::concurrent\_queue](../../parallel/concrt/reference/concurrent-queue-class.md)\-Objekt für den Satz von Carmichael\-Zahlen verwendet, da dieses Objekt später als Arbeitswarteschlange eingesetzt wird.  Es enthält den Satz von Primzahlen in Form eines [concurrency::concurrent\_vector](../../parallel/concrt/reference/concurrent-vector-class.md)\-Objekts, da es später diesen Satz durchläuft, um Primfaktoren zu suchen.  
  
 [!CODE [concrt-carmichael-primes#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-carmichael-primes#2)]  
  
## Beispiel  
 Im folgenden Beispiel wird die `prime_factors_of`\-Funktion veranschaulicht, von der die Versuchsdivision verwendet wird, um alle Primfaktoren des angegebenen Werts zu suchen.  
  
 Diese Funktion durchläuft die Auflistung von Primzahlen mithilfe des [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md)\-Algorithmus.  Das `concurrent_vector`\-Objekt macht es möglich, dass die parallele Schleife dem Ergebnis gleichzeitig Primfaktoren hinzufügen kann.  
  
 [!CODE [concrt-carmichael-primes#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-carmichael-primes#3)]  
  
## Beispiel  
 In diesem Beispiel wird jedes Element in der Warteschlange von Carmichael\-Zahlen verarbeitet, indem zum Berechnen der Primfaktoren die `prime_factors_of`\-Funktion aufgerufen wird.  Es führt diese Arbeit mithilfe einer Aufgabengruppe parallel aus.  Weitere Informationen zu Aufgabengruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 In diesem Beispiel werden die Primfaktoren für jede Carmichael\-Zahl gedruckt, wenn diese Zahl mehr als vier Primfaktoren hat.  
  
 [!CODE [concrt-carmichael-primes#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-carmichael-primes#4)]  
  
## Beispiel  
 Im folgenden Code wird das vollständige Beispiel veranschaulicht, in dem parallele Container zum Berechnen der Primfaktoren der Carmichael\-Zahlen verwendet werden.  
  
 [!CODE [concrt-carmichael-primes#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-carmichael-primes#5)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
  **Prime factors of 9890881 are: 7 11 13 41 241.**  
**Prime factors of 825265 are: 5 7 17 19 73.**  
**Prime factors of 1050985 are: 5 13 19 23 37.**   
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `carmichael-primes.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc carmichael\-primes.cpp**  
  
## Siehe auch  
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [concurrent\_vector\-Klasse](../../parallel/concrt/reference/concurrent-vector-class.md)   
 [concurrent\_queue\-Klasse](../../parallel/concrt/reference/concurrent-queue-class.md)   
 [parallel\_invoke\-Funktion](../Topic/parallel_invoke%20Function.md)   
 [parallel\_for\-Funktion](../Topic/parallel_for%20Function.md)   
 [task\_group\-Klasse](../Topic/task_group%20Class.md)