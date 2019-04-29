---
title: 'Vorgehensweise: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife'
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: 19d732d98f24172471d96cd5e2962b2a99ab0203
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409992"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Vorgehensweise: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife

In diesem Thema veranschaulicht das Schreiben ein Suchalgorithmus für eine einfache Struktur.

Das Thema [Abbruch](cancellation-in-the-ppl.md) erläutert die Rolle des Abbruchs in der Parallel Patterns Library. Die Verwendung der Ausnahmebehandlung ist eine weniger effiziente Möglichkeit zum Abbrechen paralleler Aufgaben als die Nutzung der [task_group](reference/task-group-class.md#cancel) und [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) Methoden. Ein Szenario, in denen die Verwendung der Ausnahmebehandlung, um die Arbeit abzubrechen eignet sich, ist jedoch, wenn Sie eine Drittanbieter-Bibliothek aufrufen, die Aufgaben oder parallelen Algorithmen verwendet, jedoch keiner `task_group` oder `structured_task_group` -Objekt abgebrochen wird.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine einfache `tree` Typ, der ein Datenelement und eine Liste mit untergeordneten Knoten enthält. Im folgenden Abschnitt wird den Hauptteil der `for_all` -Methode, die rekursiv eine Arbeitsfunktion, für jeden untergeordneten Knoten ausführt.

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die `for_all` Methode. Er verwendet den [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus, um eine Arbeitsfunktion auf jedem Knoten des Baums parallel auszuführen.

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die `search_for_value`-Funktion, die nach einem Wert im bereitgestellten `tree`-Objekt sucht. Diese Funktion übergibt an die `for_all` Methode eine Arbeitsfunktion, die ausgelöst wird, wenn es sich um einen Strukturknoten findet, die den angegebenen Wert enthält.

Vorausgesetzt, dass die `tree` Klasse wird von einer Drittanbieter-Bibliothek bereitgestellt, und Sie nicht mehr geändert werden. In diesem Fall die Verwendung der Ausnahmebehandlung eignet sich da die `for_all` Methode bietet keine `task_group` oder `structured_task_group` Objekt an den Aufrufer. Daher ist die Arbeitsfunktion kann nicht direkt auf die übergeordnete Aufgabengruppe abgebrochen.

Wenn die Arbeitsfunktion, die Sie, an einer Aufgabengruppe bereitstellen eine Ausnahme auslöst, wird die Runtime alle Aufgaben, die in der Aufgabengruppe (sowie alle untergeordneten Aufgabengruppen) beendet und alle, die noch nicht gestarteten Aufgaben verworfen. Die `search_for_value` Funktion verwendet einen `try` - `catch` Block, um die Ausnahme zu erfassen und das Ergebnis in der Konsole auszugeben.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt eine `tree` Objekt aus, und mehrere Werte gleichzeitig sucht. Die `build_tree` Funktion wird weiter unten in diesem Thema gezeigt.

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

Dieses Beispiel verwendet die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Algorithmus zum Suchen nach Werten parallel. Weitere Informationen zu diesem Algorithmus finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Beispiel

Im folgende vollständige Beispiel mithilfe der Ausnahmebehandlung auf die Suche nach Werten in eine einfache Struktur.

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe.

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `task-tree-search.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Task-Struktur-search.cpp**

## <a name="see-also"></a>Siehe auch

[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group-Klasse](reference/task-group-class.md)<br/>
[structured_task_group-Klasse](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)
