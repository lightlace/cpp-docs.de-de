---
title: "Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden"
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
  - "Planerrichtlinien, Agents [Concurrency Runtime]"
  - "Erstellen von Agents, die bestimmte Richtlinien verwenden [Concurrency Runtime]"
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
caps.latest.revision: 14
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Agent ist eine Anwendungskomponente, die asynchron mit anderen Komponenten arbeitet, um größere Rechenaufgaben zu lösen.  Ein Agent hat in der Regel einen festgelegten Lebenszyklus und behält den Zustand bei.  
  
 Dabei kann jeder Agent eigene Anwendungsanforderungen haben.  Ein Agent, der eine Benutzerinteraktion ermöglicht \(Abrufen einer Eingabe oder Anzeigen einer Ausgabe\), benötigt z. B. für Computerressourcen möglicherweise Zugriff mit höherer Priorität.  Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet.  In diesem Thema wird die Erstellung von Agents beschrieben, die bestimmte Planerrichtlinien verwenden.  
  
 Ein einfaches Beispiel für die Verwendung von benutzerdefinierten Planerrichtlinien zusammen mit asynchronen Nachrichtenblöcken finden Sie unter [Gewusst wie: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
 In diesem Thema werden mithilfe der Funktionalität der Asynchronous Agents Library Arbeiten ausgeführt, z. B. mithilfe von Agents, Nachrichtenblöcken und Nachrichtenübergabefunktionen.  Weitere Informationen zur Asynchronous Agents Library finden Sie unter [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md).  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Klassen definiert, die vom [concurrency::agent](../../parallel/concrt/reference/agent-class.md) abgeleitet werden: `permutor` und `printer`.  Die `permutor`\-Klasse berechnet alle Permutationen einer gegebenen Eingabezeichenfolge.  Die `printer`\-Klasse gibt Statusmeldungen an der Konsole aus.  Die `permutor`\-Klasse führt einen rechenintensiven Vorgang aus, der möglicherweise alle verfügbaren Computerressourcen erfordert.  Für eine sinnvolle Nutzung muss die `printer`\-Klasse alle Statusmeldungen zeitnah ausgeben.  
  
 Um der `printer`\-Klasse einen fairen Zugriff auf Computerressourcen zu ermöglichen, wird in diesem Beispiel mithilfe der unter [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) beschriebenen Schritte eine Planerinstanz erstellt, die über eine benutzerdefinierte Richtlinie verfügt.  Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.  
  
 Um die Vorteile der Verwendung eines Planers mit einer benutzerdefinierten Richtlinie aufzuzeigen, wird in diesem Beispiel die gesamte Aufgabe zweimal ausgeführt.  Dabei werden im Beispiel zunächst beide Aufgaben mithilfe des Standardplaners geplant.  Anschließend werden mithilfe des Standardplaners das `permutor`\-Objekt sowie ein Planer geplant, der eine benutzerdefinierte Richtlinie zum Planen des `printer`\-Objekts enthält.  
  
 [!CODE [concrt-permute-strings#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-permute-strings#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **With default scheduler:**  
**Computing all permutations of 'Grapefruit'...**  
**100% complete...**  
**With higher context priority:**  
**Computing all permutations of 'Grapefruit'...**  
**100% complete...** Beide Aufgabengruppen führen zum gleichen Ergebnis, aber nur die Version mit einer benutzerdefinierten Richtlinie ermöglicht die Ausführung des `printer`\-Objekts mit einer höheren Priorität, sodass diese ein besseres Reaktionsverhalten aufweist.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `permute-strings.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc permute\-strings.cpp**  
  
## Siehe auch  
 [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 