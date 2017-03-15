---
title: "Gewusst wie: Konvertieren einer OpenMP-Schleife mit Abbruch zur Verwendung der Concurrency Runtime"
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
  - "Konvertierung von OpenMP in die Concurrency Runtime, Abbruch"
  - "Abbruch, Konvertierung von OpenMP in die Concurrency Runtime"
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 11
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Konvertieren einer OpenMP-Schleife mit Abbruch zur Verwendung der Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei einigen parallelen Schleifen müssen nicht alle Iterationen ausgeführt werden.  Beispielsweise kann ein Algorithmus, mit dem nach einem Wert gesucht wird, beendet werden, sobald der Wert gefunden wurde.  OpenMP stellt keinen Mechanismus bereit, um aus einer parallelen Schleife auszubrechen.  Sie können jedoch einen booleschen Wert oder ein Flag verwenden, damit die Iteration einer Schleife angeben kann, dass der gesuchte Wert gefunden wurde.  Die Concurrency Runtime stellt Funktionen bereit, mit denen eine Aufgabe andere Aufgaben abbrechen kann, die noch nicht gestartet wurden.  
  
 In diesem Beispiel wird veranschaulicht, wie eine OpenMP [parallel](../../parallel/openmp/reference/parallel.md)\_[for](../../parallel/openmp/reference/for-openmp.md)\-Schleife konvertiert wird, bei der die Ausführung aller Iterationen keine Voraussetzung für die Verwendung des Concurrency Runtime\-Abbruchmechanismus ist.  
  
## Beispiel  
 In diesem Beispiel wird mit OpenMP und der Concurrency Runtime eine parallele Version des [std::any\_of](../Topic/any_of.md)\-Algorithmus implementiert.  In der OpenMP\-Version in diesem Beispiel wird mit einem Flag die Erfüllung der Bedingung für alle parallelen Schleifeniterationen koordiniert.  In der Version mit der Concurrency Runtime wird mit der [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md)\-Methode der Gesamtvorgang beendet, wenn die Bedingung erfüllt ist.  
  
 [!CODE [concrt-openmp#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-openmp#2)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Using OpenMP...**  
**9114046 is in the array.**  
**Using the Concurrency Runtime...**  
**9114046 is in the array.** In der Version mit OpenMP werden, auch wenn das Flag festgelegt ist, alle Schleifeniterationen ausgeführt.  Bei einer Aufgabe mit untergeordneten Aufgaben müsste das Flag darüber hinaus auch für diese verfügbar sein, um den Abbruch des Vorgangs zu signalisieren.  In der Concurrency Runtime wird beim Abbrechen einer Aufgabengruppe die gesamte Arbeitsstruktur einschließlich der untergeordneten Aufgaben von der Laufzeit abgebrochen.  Der [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md)\-Algorithmus führt Arbeiten mit Aufgaben aus.  Wenn die Stammaufgabe durch eine Iteration der Schleife abgebrochen wird, wird daher die gesamte Struktur der Berechnung abgebrochen.  Wenn eine Arbeitsstruktur abgebrochen wird, werden von der Laufzeit keine neuen Aufgaben gestartet.  Aufgaben, die bereits gestartet wurden, wird von der Laufzeit jedoch eine Fertigstellung ermöglicht.  Aktive Schleifeniterationen können im Falle des `parallel_for_each`\-Algorithmus also ihre Ressourcen bereinigen.  
  
 Im Beispiel kann das Ergebnis in beiden Versionen durch mehrere Schleifeniterationen parallel festgelegt und der Gesamtvorgang kann abgebrochen werden, wenn das Array mehr als eine Kopie des gesuchten Werts enthält.  Mit einem Synchronisierungsprimitiven wie einem kritischen Abschnitt können Sie ggf. sicherstellen, dass Arbeiten nur von einer Aufgabe ausgeführt werden, wenn eine Bedingung erfüllt ist.  
  
 Sie können Aufgaben mit der PPL auch mit der Ausnahmebehandlung abbrechen.  Weitere Informationen über das Abbrechen finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
 Weitere Informationen zu `parallel_for_each` und anderen parallelen Algorithmen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `concrt-omp-parallel-any-of.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-parallel\-any\-of.cpp**  
  
## Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)