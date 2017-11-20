---
title: "Vorgehensweise: Auswählen von abgeschlossenen Aufgaben | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a36e871c8cea0a1ed16362ab7d8683151fe17825
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-select-among-completed-tasks"></a>Gewusst wie: Auswählen von abgeschlossenen Aufgaben
Dieses Beispiel zeigt, wie die [Choice](../../parallel/concrt/reference/choice-class.md) und [Concurrency:: Join](../../parallel/concrt/reference/join-class.md) Klassen, die die erste Aufgabe zum Abschließen eines Suchalgorithmus auszuwählen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Suchalgorithmen parallel ausgeführt und der erste abzuschließende Algorithmus ausgewählt. In diesem Beispiel wird der `employee`-Typ definiert, der einen numerischen Bezeichner und ein Gehalt für einen Mitarbeiter enthält. Die `find_employee`-Funktion sucht den ersten Mitarbeiter, der über den bereitgestellten Bezeichner oder das bereitgestellte Gehalt verfügt. Die `find_employee`-Funktion verarbeitet auch den Fall, in dem kein Mitarbeiter über den bereitgestellten Bezeichner oder das Gehalt verfügt. Die `wmain`-Funktion erstellt ein Array von `employee`-Objekten und sucht nach mehreren Bezeichnern und Gehaltswerten.  
  
 Im Beispiel wird mithilfe eines `choice`-Objekts aus folgenden Fällen eine Auswahl getroffen:  
  
1.  Es ist ein Mitarbeiter vorhanden, der über den bereitgestellten Bezeichner verfügt.  
  
2.  Es ist ein Mitarbeiter vorhanden, der über das bereitgestellte Gehalt verfügt.  
  
3.  Es ist kein Mitarbeiter vorhanden, der über den bereitgestellten Bezeichner oder das Gehalt verfügt.  
  
 Die ersten beiden Fälle wird im Beispiel verwendet eine [Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) Objekt, das den Bezeichner und in einem anderen `single_assignment` -Objekt, das Gehalt. Für den dritten Fall wird im Beispiel ein `join`-Objekt verwendet. Das `join`-Objekt besteht aus zwei zusätzlichen `single_assignment`-Objekten. Eines dieser Objekte ist für den Fall, in dem kein Mitarbeiter vorhanden ist, der über den bereitgestellten Bezeichner verfügt, und das andere für den Fall, in dem kein Mitarbeiter vorhanden ist, der über das bereitgestellte Gehalt verfügt. Das `join`-Objekt sendet eine Meldung, wenn jedes seiner Member eine Meldung empfängt. In diesem Beispiel sendet das `join`-Objekt eine Meldung, wenn kein Mitarbeiter vorhanden ist, der über den bereitgestellten Bezeichner oder das Gehalt verfügt.  
  
 Im Beispiel wird eine [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objekt, das beide Suchalgorithmen parallel ausgeführt werden. Bei jeder Suchaufgabe wird auf eines der `single_assignment`-Objekte geschrieben, um anzugeben, ob der bestimmte Mitarbeiter vorhanden ist. Im Beispiel wird die [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) Funktion, um den Index des ersten Puffers abzurufen, die eine Nachricht enthält und eine `switch` Block, um das Ergebnis auszugeben.  
  
 [!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Employee with id 14758 has salary 27780.00.  
Employee with salary 29150.00 has id 84345.  
Employee with id 61935 has salary 29905.00.  
No employee has id 899 or salary 31223.00.  
```  
  
 Dieses Beispiel verwendet die [Concurrency:: make_choice](reference/concurrency-namespace-functions.md#make_choice) -Hilfsfunktion zum Erstellen `choice` Objekte und die [Concurrency:: make_join](reference/concurrency-namespace-functions.md#make_join) -Hilfsfunktion zum Erstellen `join` Objekte.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `find-employee.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Find-employee.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)   
 [Choice-Klasse](../../parallel/concrt/reference/choice-class.md)   
 [join-Klasse](../../parallel/concrt/reference/join-class.md)
