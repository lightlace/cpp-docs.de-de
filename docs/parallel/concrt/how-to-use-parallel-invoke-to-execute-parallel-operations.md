---
title: "Gewusst wie: Ausf&#252;hren von parallelen Vorg&#228;ngen mithilfe von parallel_invoke"
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
  - "parallel_invoke-Funktion, Beispiel"
  - "Paralleles Aufrufen mehrerer Funktionen [Concurrency Runtime]"
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
caps.latest.revision: 18
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Ausf&#252;hren von parallelen Vorg&#228;ngen mithilfe von parallel_invoke
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im folgenden Beispiel wird gezeigt, wie mit dem [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md)\-Algorithmus die Leistung eines Programms verbessert werden kann, das mehrere Vorgänge in einer freigegebenen Datenquelle ausführt.  Da die Quelle durch keinen der Vorgänge geändert wird, können diese auf einfache Weise parallel ausgeführt werden.  
  
## Beispiel  
 Betrachten Sie das folgende Codebeispiel, in dem eine Variable vom Typ `MyDataType` erstellt wird, eine Funktion zum Initialisieren dieser Variablen aufgerufen wird und dann mehrere langwierige Operationen mit diesen Daten ausgeführt werden.  
  
 [!CODE [concrt-parallel-word-mining#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-word-mining#1)]  
  
 Wenn die Funktionen `lengthy_operation1`, `lengthy_operation2` und `lengthy_operation3` die `MyDataType`\-Variable nicht ändern, können sie ohne weitere Änderungen parallel ausgeführt werden.  
  
## Beispiel  
 Im folgenden Beispiel wird das vorhergehende Beispiel geändert, um es parallel auszuführen.  Der `parallel_invoke`\-Algorithmus führt jede Aufgabe parallel aus und wird zurückgegeben, nachdem alle Aufgaben beendet wurden.  
  
 [!CODE [concrt-parallel-word-mining#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-word-mining#2)]  
  
## Beispiel  
 Im folgenden Beispiel wird *Die Ilias* von Homer von gutenberg.org heruntergeladen, und es werden mehrere Vorgänge mit dieser Datei ausgeführt.  Im Beispiel werden diese Vorgänge zunächst seriell und dann parallel ausgeführt.  
  
 [!CODE [concrt-parallel-word-mining#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-word-mining#3)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
  **Downloading 'The Iliad'...**  
**Running serial version... took 953 ms.**  
**Running parallel version... took 656 ms.**  
**The most common words that have five or more letters are:**  
 **their \(953\)**  
 **shall \(444\)**  
 **which \(431\)**  
 **great \(398\)**  
 **Hector \(349\)**  
 **Achilles \(309\)**  
 **through \(301\)**  
 **these \(268\)**  
 **chief \(259\)**  
**The longest sequence of words that have the same first letter is:**  
 **through the tempest to the tented**  
**The following palindromes appear in the text:**  
 **spots stops**  
 **speed deeps**  
 **keels sleek** In diesem Beispiel werden mit dem `parallel_invoke`\-Algorithmus mehrere Funktionen aufgerufen, die auf dieselbe Datenquelle angewendet werden.  Sie können mit dem `parallel_invoke`\-Algorithmus jeden Satz von Funktionen parallel aufrufen, nicht nur Funktionen, die auf dieselben Daten angewendet werden.  
  
 Da der `parallel_invoke`\-Algorithmus die Arbeitsfunktionen parallel aufruft, liegt die Leistungsgrenze bei der Funktion, die am längsten braucht \(wenn die Runtime jede Funktion auf einem separaten Prozessor ausführt\).  Wenn mehr Aufgaben parallel ausgeführt werden, als Prozessoren verfügbar sind, können auf jedem Prozessor mehrere Aufgaben ausgeführt werden.  In diesem Fall liegt die Leistungsgrenze bei der Aufgabengruppe, die am längsten braucht.  
  
 Da in diesem Beispiel drei Aufgaben parallel ausgeführt werden, sollten Sie keine Leistungsskalierung auf Computern mit mehr als drei Prozessoren erwarten.  Um die Leistung zusätzlich zu steigern, können Sie die Aufgaben mit der längsten Ausführungsdauer in kleinere Aufgaben aufteilen und diese Aufgaben parallel ausführen.  
  
 Sie können statt der [concurrency::task\_group](../Topic/task_group%20Class.md)\-Klasse und der [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Klasse den `parallel_invoke`\-Algorithmus verwenden, wenn Sie keine Abbruchunterstützung benötigen.  Ein Beispiel, in dem die Verwendung des `parallel_invoke`\-Algorithmus mit der Verwendung von Aufgabengruppen verglichen wird, finden Sie unter [Gewusst wie: Verwenden von parallel\_invoke zum Schreiben einer Runtime für paralleles Sortieren](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).  
  
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-word-mining.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe \/EHsc \/MD \/DUNICODE \/D\_AFXDLL parallel\-word\-mining.cpp**  
  
## Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_invoke\-Funktion](../Topic/parallel_invoke%20Function.md)