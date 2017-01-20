---
title: "Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife"
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
  - "Suchalgorithmus, Schreiben [Concurrency Runtime]"
  - "Schreiben eines Suchalgorithmus [Concurrency Runtime]"
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: 15
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden der Ausnahmebehandlung zum Verlassen einer Parallel-Schleife
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie ein Suchalgorithmus für eine einfache Baumstruktur geschrieben wird.  
  
 Das Thema [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md) erläutert die Rolle des Abbruchs in der Parallel Patterns Library.  Die Verwendung der Ausnahmebehandlung ist weniger effizient, parallele Arbeitsvorgänge als die Verwendung von den Methoden [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) und [concurrency::structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md).  Die Verwendung der Ausnahmebehandlung zum Abbrechen eines Arbeitsvorgangs ist jedoch angemessen, wenn Sie die Bibliothek eines Drittanbieters mit Aufgaben oder parallelen Algorithmen aufrufen, diese jedoch kein `task_group`\- oder `structured_task_group`\-Objekt zum Abbrechen bereitstellt.  
  
## Beispiel  
 Im folgenden Beispiel wird ein grundlegender `tree`\-Typ dargestellt, der ein Datenelement und eine Liste untergeordneter Knoten enthält.  Der folgende Abschnitt zeigt den Text der `for_all`\-Methode an, der rekursiv eine Arbeitsfunktion für jeden untergeordneten Knoten ausführt.  
  
 [!CODE [concrt-task-tree-search#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree-search#2)]  
  
## Beispiel  
 Im folgenden Beispiel wird die `for_all`\-Methode dargestellt.  Es verwendet den [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) \- Algorithmus, um eine Arbeitsfunktion für jeden Knoten in der Baumstruktur parallel auszuführen.  
  
 [!CODE [concrt-task-tree-search#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree-search#1)]  
  
## Beispiel  
 Im folgenden Beispiel wird die `search_for_value`\-Funktion veranschaulicht, die nach einem Wert im bereitgestellten `tree`\-Objekt sucht.  Diese Funktion übergibt eine Arbeitsfunktion an die `for_all`\-Methode; diese Arbeitsfunktion wird ausgelöst, wenn sie auf einen Strukturknoten trifft, der den bereitgestellten Wert enthält.  
  
 Angenommen, die `tree`\-Klasse wird von der Bibliothek eines Drittanbieters bereitgestellt und kann nicht geändert werden.  Die Verwendung der Ausnahmebehandlung ist für dieses Beispiel geeignet, da die `for_all`\-Methode dem Aufrufer kein `task_group`\-Objekt oder `structured_task_group`\-Objekt bereitstellt.  Daher kann die Arbeitsfunktion nicht direkt ihre übergeordnete Aufgabengruppe abbrechen.  
  
 Wenn die Arbeitsfunktion, die Sie für eine Aufgabengruppe bereitstellen, eine Ausnahme auslöst, beendet die Laufzeit alle Aufgaben in der Aufgabengruppe \(einschließlich aller untergeordneten Aufgabengruppen\) und verwirft alle Aufgaben, die noch nicht gestartet wurden.  Die `search_for_value`\-Funktion verwendet einen `try`\-`catch`\-Block, um die Ausnahme zu erfassen und das Ergebnis in der Konsole auszugeben.  
  
 [!CODE [concrt-task-tree-search#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree-search#3)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein `tree`\-Objekt erstellt und darin parallel nach mehreren Werten gesucht.  Die `build_tree`\-Funktion wird weiter unten in diesem Thema dargestellt.  
  
 [!CODE [concrt-task-tree-search#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree-search#4)]  
  
 Dieses Beispiel verwendet den [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md), um für Algorithmus parallel nach Werten.  Weitere Informationen zu diesem Algorithmus finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## Beispiel  
 Im folgenden vollständigen Beispiel wird anhand der Ausnahmebehandlung nach Werten in einer einfachen Baumstruktur gesucht.  
  
 [!CODE [concrt-task-tree-search#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-tree-search#5)]  
  
 Dieses Beispiel erzeugt die folgende Beispielausgabe.  
  
  **Starten Sie einen Knoten mit Wert 32614.**  
**Starten Sie einen Knoten mit Wert 86131.**  
**Hat keine Knoten mit Wert 17522.**   
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `task-tree-search.cpp` ein, und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderung ausgeführt.  
  
 **cl.exe \/EHsc task\-tree\-search.cpp**  
  
## Siehe auch  
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [task\_group\-Klasse](../Topic/task_group%20Class.md)   
 [structured\_task\_group\-Klasse](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel\_for\_each\-Funktion](../Topic/parallel_for_each%20Function.md)