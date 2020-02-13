---
title: 'Vorgehensweise: Auswählen von abgeschlossenen Aufgaben'
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: 75ecac8dd0e8845401e3e287e8c95ea614055970
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142474"
---
# <a name="how-to-select-among-completed-tasks"></a>Vorgehensweise: Auswählen von abgeschlossenen Aufgaben

In diesem Beispiel wird gezeigt, wie die Klassen " [parallelcurrency:: Choice](../../parallel/concrt/reference/choice-class.md) " und " [parallelcurrency:: Join](../../parallel/concrt/reference/join-class.md) " verwendet werden, um die erste Aufgabe zum Vervollständigen eines Suchalgorithmus auszuwählen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Suchalgorithmen parallel ausgeführt und der erste abzuschließende Algorithmus ausgewählt. In diesem Beispiel wird der `employee`-Typ definiert, der einen numerischen Bezeichner und ein Gehalt für einen Mitarbeiter enthält. Die `find_employee`-Funktion sucht den ersten Mitarbeiter, der über den bereitgestellten Bezeichner oder das bereitgestellte Gehalt verfügt. Die `find_employee`-Funktion verarbeitet auch den Fall, in dem kein Mitarbeiter über den bereitgestellten Bezeichner oder das Gehalt verfügt. Die `wmain`-Funktion erstellt ein Array von `employee`-Objekten und sucht nach mehreren Bezeichnern und Gehaltswerten.

Im Beispiel wird mithilfe eines `choice`-Objekts aus folgenden Fällen eine Auswahl getroffen:

1. Es ist ein Mitarbeiter vorhanden, der über den bereitgestellten Bezeichner verfügt.

1. Es ist ein Mitarbeiter vorhanden, der über das bereitgestellte Gehalt verfügt.

1. Es ist kein Mitarbeiter vorhanden, der über den bereitgestellten Bezeichner oder das Gehalt verfügt.

In den ersten beiden Fällen verwendet das Beispiel ein [parallelcurrency:: Single_assignment](../../parallel/concrt/reference/single-assignment-class.md) -Objekt, das den Bezeichner und ein weiteres `single_assignment` Objekt enthält, das das Gehalt enthalten soll. Für den dritten Fall wird im Beispiel ein `join`-Objekt verwendet. Das `join`-Objekt besteht aus zwei zusätzlichen `single_assignment`-Objekten. Eines dieser Objekte ist für den Fall, in dem kein Mitarbeiter vorhanden ist, der über den bereitgestellten Bezeichner verfügt, und das andere für den Fall, in dem kein Mitarbeiter vorhanden ist, der über das bereitgestellte Gehalt verfügt. Das `join`-Objekt sendet eine Meldung, wenn jedes seiner Member eine Meldung empfängt. In diesem Beispiel sendet das `join`-Objekt eine Meldung, wenn kein Mitarbeiter vorhanden ist, der über den bereitgestellten Bezeichner oder das Gehalt verfügt.

Im Beispiel wird ein [parallelcurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) -Objekt verwendet, um beide Suchalgorithmen parallel auszuführen. Bei jeder Suchaufgabe wird auf eines der `single_assignment`-Objekte geschrieben, um anzugeben, ob der bestimmte Mitarbeiter vorhanden ist. Im Beispiel wird die [parallelcurrency:: Receive](reference/concurrency-namespace-functions.md#receive) -Funktion verwendet, um den Index des ersten Puffers zu erhalten, der eine Meldung enthält, und einen `switch` Block, um das Ergebnis zu drucken.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

Folgende Ergebnisse werden zurückgegeben:

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

In diesem Beispiel wird die [Hilfsfunktion "parallelcurrency:: Make_choice](reference/concurrency-namespace-functions.md#make_choice) " verwendet, um `choice` Objekte zu erstellen, und die [Hilfsfunktion "parallelcurrency:: Make_join](reference/concurrency-namespace-functions.md#make_join) " zum Erstellen von `join` Objekten.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `find-employee.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc Find-Employee. cpp**

## <a name="see-also"></a>Weitere Informationen

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)<br/>
[choice-Klasse](../../parallel/concrt/reference/choice-class.md)<br/>
[join-Klasse](../../parallel/concrt/reference/join-class.md)
