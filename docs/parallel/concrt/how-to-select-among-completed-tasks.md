---
title: "Gewusst wie: Ausw&#228;hlen von abgeschlossenen Aufgaben"
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
  - "Auswählen von abgeschlossenen Aufgaben [Concurrency Runtime]"
  - "Abgeschlossene Aufgaben, Auswählen [Concurrency Runtime]"
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: 17
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Ausw&#228;hlen von abgeschlossenen Aufgaben
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird gezeigt, wie die [concurrency::choice](../../parallel/concrt/reference/choice-class.md)\-Klasse und die [concurrency::join](../../parallel/concrt/reference/join-class.md)\-Klasse verwendet werden, um die erste Aufgabe auszuwählen, die zum Abschließen eines Suchalgorithmus durchzuführen ist.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Suchalgorithmen parallel ausgeführt und der erste abzuschließende Algorithmus ausgewählt.  In diesem Beispiel wird der `employee`\-Typ definiert, der einen numerischen Bezeichner und ein Gehalt für einen Mitarbeiter enthält.  Die `find_employee`\-Funktion sucht den ersten Mitarbeiter, der über den bereitgestellten Bezeichner oder das bereitgestellte Gehalt verfügt.  Die `find_employee`\-Funktion verarbeitet auch den Fall, in dem kein Mitarbeiter über den bereitgestellten Bezeichner oder das Gehalt verfügt.  Die `wmain`\-Funktion erstellt ein Array von `employee`\-Objekten und sucht nach mehreren Bezeichnern und Gehaltswerten.  
  
 Im Beispiel wird mithilfe eines `choice`\-Objekts aus folgenden Fällen eine Auswahl getroffen:  
  
1.  Es ist ein Mitarbeiter vorhanden, der über den bereitgestellten Bezeichner verfügt.  
  
2.  Es ist ein Mitarbeiter vorhanden, der über das bereitgestellte Gehalt verfügt.  
  
3.  Es ist kein Mitarbeiter vorhanden, der über den bereitgestellten Bezeichner oder das Gehalt verfügt.  
  
 Für die ersten beiden Fälle wird im Beispiel für den Bezeichner ein [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md)\-Objekt verwendet und für das Gehalt ein `single_assignment`\-Objekt.  Für den dritten Fall wird im Beispiel ein `join`\-Objekt verwendet.  Das `join`\-Objekt besteht aus zwei zusätzlichen `single_assignment`\-Objekten. Eines dieser Objekte ist für den Fall, in dem kein Mitarbeiter vorhanden ist, der über den bereitgestellten Bezeichner verfügt, und das andere für den Fall, in dem kein Mitarbeiter vorhanden ist, der über das bereitgestellte Gehalt verfügt.  Das `join`\-Objekt sendet eine Meldung, wenn jedes seiner Member eine Meldung empfängt.  In diesem Beispiel sendet das `join`\-Objekt eine Meldung, wenn kein Mitarbeiter vorhanden ist, der über den bereitgestellten Bezeichner oder das Gehalt verfügt.  
  
 Im Beispiel wird ein [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Objekt verwendet, um beide Suchalgorithmen parallel auszuführen.  Bei jeder Suchaufgabe wird auf eines der `single_assignment`\-Objekte geschrieben, um anzugeben, ob der bestimmte Mitarbeiter vorhanden ist.  Im Beispiel wird die [concurrency::receive](../Topic/receive%20Function.md)\-Funktion verwendet, um den Index des ersten Puffers abzurufen, der eine Nachricht enthält, und ein `switch`\-Block, um das Ergebnis auszugeben.  
  
 [!CODE [concrt-find-employee#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-find-employee#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Employee with id 14758 has salary 27780.00.**  
**Employee with salary 29150.00 has id 84345.**  
**Employee with id 61935 has salary 29905.00.**  
**No employee has id 899 or salary 31223.00.** In diesem Beispiel wird die [concurrency::make\_choice](../Topic/make_choice%20Function.md)\-Hilfsfunktion zum Erstellen von `choice`\-Objekten und die [concurrency::make\_join](../Topic/make_join%20Function.md)\-Hilfsfunktion zum Erstellen von `join`\-Objekten verwendet.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `find-employee.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc find\-employee.cpp**  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Funktionen zum Übergeben von Meldungen](../../parallel/concrt/message-passing-functions.md)   
 [choice\-Klasse](../../parallel/concrt/reference/choice-class.md)   
 [join\-Klasse](../../parallel/concrt/reference/join-class.md)