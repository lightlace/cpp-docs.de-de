---
title: "Gewusst wie: Angeben von bestimmten Planerrichtlinien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Angeben von Planerrichtlinien [Concurrency Runtime]"
  - "Planerrichtlinien, Angeben [Concurrency Runtime]"
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Gewusst wie: Angeben von bestimmten Planerrichtlinien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet. In diesem Thema wird veranschaulicht, wie eine Planerrichtlinie verwendet wird, um die Threadpriorität einer Aufgabe zu erhöhen, die eine Statusanzeige an die Konsole ausgibt.  
  
 Ein Beispiel für die benutzerdefinierte Planerrichtlinien zusammen mit asynchronen Agents finden Sie unter [Gewusst wie: Erstellen von Agents, Use Specific Scheduler Policies](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Aufgaben parallel ausgeführt. Die erste Aufgabe berechnet die n<sup>te</sup> Fibonacci-Zahl. Die zweite Aufgabe gibt eine Statusanzeige an die Konsole aus.  
  
 Die erste Aufgabe verwendet die rekursive Zerlegung zur Berechnung der Fibonacci-Zahl. Das heißt, jede Aufgabe erstellt rekursiv Unteraufgaben zur Berechnung des Gesamtergebnisses. Es kann vorkommen, dass eine Aufgabe, die rekursive Zerlegung verwendet, alle verfügbaren Ressourcen belegt, die anderen Aufgaben dann fehlen. In diesem Beispiel kann die Aufgabe zur Ausgabe der Statusanzeige möglicherweise nicht rechtzeitig auf Computerressourcen zugreifen.  
  
 Um die Aufgabe zu ermöglichen, die einen Zugriff auf Computerressourcen ausgibt, dieses Beispiel verwendet die in beschriebenen Schritte [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) eine Planerinstanz zu erstellen, die eine benutzerdefinierte Richtlinie verfügt. Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.  
  
 Dieses Beispiel verwendet die [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) und [Concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) Klassen, die Statusanzeige zu drucken. Diese Klassen weisen Konstruktorversionen auf, die einen Verweis auf eine [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) Objekt, das zur Planung. In unserem Beispiel wird der Standardplaner zur Planung der Aufgabe verwendet, die die Fibonacci-Zahl berechnet, und die Planerinstanz wird zur Planung der Aufgabe verwendet, die die Statusanzeige ausgibt.  
  
 Um die Vorteile der Verwendung eines Planers mit einer benutzerdefinierten Richtlinie aufzuzeigen, wird in diesem Beispiel die gesamte Aufgabe zweimal ausgeführt. Dabei werden im Beispiel zunächst beide Aufgaben mithilfe des Standardplaners geplant. Beim zweiten Durchlauf wird die erste Aufgabe mithilfe des Standardplaners und die zweite Aufgabe mithilfe eines Planers mit einer benutzerdefinierten Richtlinie geplant.  
  
 [!CODE [concrt-scheduler-policy#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-scheduler-policy#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 Obwohl beide Durchläufe zum gleichen Ergebnis führen, ermöglicht die Version mit der benutzerdefinierten Richtlinie die Ausführung der Aufgabe zur Ausgabe der Statusanzeige mit erhöhter Priorität, das heißt mit höherer Reaktionsgeschwindigkeit.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `scheduler-policy.cpp` und dann den folgenden Befehl in ein Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc Scheduler-policy.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)   
 [Gewusst wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

