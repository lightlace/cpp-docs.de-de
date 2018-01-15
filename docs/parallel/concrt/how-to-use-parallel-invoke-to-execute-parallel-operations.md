---
title: "Vorgehensweise: Verwenden von Parallel_invoke zum Ausführen von parallelen Vorgängen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cefabd21e04c4c3cc39934de111fe94151317ca5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Gewusst wie: Ausführen von parallelen Vorgängen mithilfe von parallel_invoke
Dieses Beispiel zeigt, wie die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) -Algorithmus die Leistung eines Programms verbessert werden kann, die mehrere Vorgänge in einer freigegebenen Datenquelle ausführt. Da die Quelle durch keinen der Vorgänge geändert wird, können diese auf einfache Weise parallel ausgeführt werden.  

  
## <a name="example"></a>Beispiel  
 Betrachten Sie das folgende Codebeispiel, in dem eine Variable vom Typ `MyDataType` erstellt wird, eine Funktion zum Initialisieren dieser Variablen aufgerufen wird und dann mehrere langwierige Operationen mit diesen Daten ausgeführt werden.  
  
 [!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]  
  
 Wenn die Funktionen `lengthy_operation1`, `lengthy_operation2` und `lengthy_operation3` die `MyDataType`-Variable nicht ändern, können sie ohne weitere Änderungen parallel ausgeführt werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das vorhergehende Beispiel geändert, um es parallel auszuführen. Der `parallel_invoke`-Algorithmus führt jede Aufgabe parallel aus und wird zurückgegeben, nachdem alle Aufgaben beendet wurden.  
  
 [!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird *die Ilias* von Homer von Gutenberg.org heruntergeladen und führt mehrere Vorgänge in dieser Datei. Im Beispiel werden diese Vorgänge zunächst seriell und dann parallel ausgeführt.  
  
 [!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
```Output  
Downloading 'The Iliad'...  
 
Running serial version... took 953 ms.  
Running parallel version... took 656 ms.  
 
The most common words that have five or more letters are:  
    their (953)  
    shall (444)  
    which (431)  
    great (398)  
    Hector (349)  
    Achilles (309)  
    through (301)  
    these (268)  
    chief (259)  
The longest sequence of words that have the same first letter is:  
    through the tempest to the tented  
The following palindromes appear in the text:  
    spots stops  
    speed deeps  
    keels sleek  
```  
  
 In diesem Beispiel werden mit dem `parallel_invoke`-Algorithmus mehrere Funktionen aufgerufen, die auf dieselbe Datenquelle angewendet werden. Sie können mit dem `parallel_invoke`-Algorithmus jeden Satz von Funktionen parallel aufrufen, nicht nur Funktionen, die auf dieselben Daten angewendet werden.  
  
 Da der `parallel_invoke`-Algorithmus die Arbeitsfunktionen parallel aufruft, liegt die Leistungsgrenze bei der Funktion, die am längsten braucht (wenn die Runtime jede Funktion auf einem separaten Prozessor ausführt). Wenn mehr Aufgaben parallel ausgeführt werden, als Prozessoren verfügbar sind, können auf jedem Prozessor mehrere Aufgaben ausgeführt werden. In diesem Fall liegt die Leistungsgrenze bei der Aufgabengruppe, die am längsten braucht.  
  
 Da in diesem Beispiel drei Aufgaben parallel ausgeführt werden, sollten Sie keine Leistungsskalierung auf Computern mit mehr als drei Prozessoren erwarten. Um die Leistung zusätzlich zu steigern, können Sie die Aufgaben mit der längsten Ausführungsdauer in kleinere Aufgaben aufteilen und diese Aufgaben parallel ausführen.  
  
 Können Sie die `parallel_invoke` Algorithmus anstelle von der [Concurrency:: task_group](reference/task-group-class.md) und [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Klassen, wenn Sie keinen Support für den Abbruch benötigen. Ein Beispiel, das die Verwendung von vergleicht die `parallel_invoke` Algorithmus Aufgabengruppen, finden Sie unter [Vorgehensweise: mithilfe von Parallel_invoke zum parallelen sortieren Schreiben einer](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-word-mining.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc/MD/DUNICODE /D_AFXDLL Parallel-Word-mining.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallel_invoke-Funktion](reference/concurrency-namespace-functions.md#parallel_invoke)


