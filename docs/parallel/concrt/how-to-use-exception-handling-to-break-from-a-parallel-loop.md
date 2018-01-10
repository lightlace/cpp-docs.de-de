---
title: 'Vorgehensweise: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29140c339614e572733988bd7ca5e14561cee5dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife
In diesem Thema wird gezeigt, wie ein Suchalgorithmus für eine einfache Baumstruktur geschrieben wird.  
  
 Das Thema [Abbruch](cancellation-in-the-ppl.md) erläutert die Rolle des Abbruchs in der Parallel Patterns Library. Die Verwendung der Ausnahmebehandlung ist eine weniger effiziente Möglichkeit zum Abbrechen paralleler Aufgaben als die Verwendung der [task_group](reference/task-group-class.md#cancel) und [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) Methoden. Ein Szenario, in denen die Verwendung der Ausnahmebehandlung abbrechen Aufgaben eignet sich, ist jedoch, wenn Sie in einer Bibliothek eines Drittanbieters, die Aufgaben oder parallelen Algorithmen verwendet aufrufen, bietet jedoch eine `task_group` oder `structured_task_group` Objekt auf "Abbrechen".  

  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine grundlegende `tree` Typ, der einem Datenelement und eine Liste mit untergeordneten Knoten enthält. Der folgende Abschnitt zeigt den Hauptteil der `for_all` -Methode, der rekursiv eine Arbeitsfunktion für jeden untergeordneten Knoten ausführt.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die `for_all` Methode. Er verwendet die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus eine Arbeitsfunktion auf jedem Knoten der Struktur parallel ausgeführt.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die `search_for_value`-Funktion, die nach einem Wert im bereitgestellten `tree`-Objekt sucht. Diese Funktion übergibt an die `for_all` -Methode eine Arbeitsfunktion, die ausgelöst wird, wenn einen Strukturknoten gefunden wird, die den angegebenen Wert enthält.  
  
 Vorausgesetzt, dass die `tree` Klasse wird von einer Bibliothek eines Drittanbieters bereitgestellt und können nicht geändert. In diesem Fall die Verwendung der Ausnahmebehandlung ist sinnvoll, da der `for_all` Methode bietet eine `task_group` oder `structured_task_group` Objekt an den Aufrufer. Daher ist die Arbeitsfunktion kann nicht direkt auf die übergeordnete Aufgabengruppe abgebrochen wird.  
  
 Wenn die Arbeitsfunktion, die Sie, an einer Aufgabengruppe bereitstellen eine Ausnahme auslöst, wird die Common Language Runtime alle Aufgaben, die in der Aufgabengruppe (sowie alle untergeordneten Aufgabengruppen) beendet und alle, die noch nicht gestarteten Aufgaben verworfen. Die `search_for_value` Funktion verwendet eine `try` - `catch` Block, um die Ausnahme zu erfassen und das Ergebnis in der Konsole auszugeben.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine `tree` -Objekt und mehrere Werte gleichzeitig sucht. Die `build_tree` Funktion wird weiter unten in diesem Thema gezeigt.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 Dieses Beispiel verwendet die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Algorithmus, parallel nach Werten gesucht werden soll. Weitere Informationen zu diesem Algorithmus finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende vollständige Beispiel mithilfe der Ausnahmebehandlung zum Suchen nach Werten in eine einfache Struktur.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
```Output  
Found a node with value 32614.  
Found a node with value 86131.  
Did not find node with value 17522.  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `task-tree-search.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Task-Struktur-search.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Abbruch in der PPL](cancellation-in-the-ppl.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Task_group-Klasse](reference/task-group-class.md)   
 [Structured_task_group-Klasse](../../parallel/concrt/reference/structured-task-group-class.md)   
 [Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)


