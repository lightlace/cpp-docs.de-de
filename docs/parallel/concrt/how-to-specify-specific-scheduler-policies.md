---
title: 'Vorgehensweise: Angeben von bestimmten Planerrichtlinien | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af30b38a89eb7e4b50c7d31be2d3ba6572843b1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Gewusst wie: Angeben von bestimmten Planerrichtlinien
Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet. In diesem Thema wird veranschaulicht, wie eine Planerrichtlinie verwendet wird, um die Threadpriorität einer Aufgabe zu erhöhen, die eine Statusanzeige an die Konsole ausgibt.  
  
 Ein Beispiel, benutzerdefinierte Planerrichtlinien zusammen mit asynchronen Agents verwendet, finden Sie unter [Vorgehensweise: Erstellen von Agents, bestimmte Planerrichtlinien der verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Aufgaben parallel ausgeführt. Die erste Aufgabe berechnet die n<sup>ten</sup> Fibonacci-Zahl. Die zweite Aufgabe gibt eine Statusanzeige an die Konsole aus.  
  
 Die erste Aufgabe verwendet die rekursive Zerlegung zur Berechnung der Fibonacci-Zahl. Das heißt, jede Aufgabe erstellt rekursiv Unteraufgaben zur Berechnung des Gesamtergebnisses. Es kann vorkommen, dass eine Aufgabe, die rekursive Zerlegung verwendet, alle verfügbaren Ressourcen belegt, die anderen Aufgaben dann fehlen. In diesem Beispiel kann die Aufgabe zur Ausgabe der Statusanzeige möglicherweise nicht rechtzeitig auf Computerressourcen zugreifen.  
  
 Um die Aufgabe zu ermöglichen, die einen Zugriff auf Computerressourcen ausgibt, in diesem Beispiel verwendet, die in beschriebenen Schritte [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) um eine Planerinstanz zu erstellen, eine benutzerdefinierte Richtlinie verfügt. Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.  
  
 Dieses Beispiel verwendet die [Call](../../parallel/concrt/reference/call-class.md) und [Concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) Klassen, die Statusanzeige zu drucken. Diese Klassen weisen allerdings Versionen auf der ihre Konstruktoren, die einen Verweis auf eine [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) -Objekt, das sie plant. In unserem Beispiel wird der Standardplaner zur Planung der Aufgabe verwendet, die die Fibonacci-Zahl berechnet, und die Planerinstanz wird zur Planung der Aufgabe verwendet, die die Statusanzeige ausgibt.  
  
 Um die Vorteile der Verwendung eines Planers mit einer benutzerdefinierten Richtlinie aufzuzeigen, wird in diesem Beispiel die gesamte Aufgabe zweimal ausgeführt. Dabei werden im Beispiel zunächst beide Aufgaben mithilfe des Standardplaners geplant. Beim zweiten Durchlauf wird die erste Aufgabe mithilfe des Standardplaners und die zweite Aufgabe mithilfe eines Planers mit einer benutzerdefinierten Richtlinie geplant.  
  
 [!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 Obwohl beide Durchläufe zum gleichen Ergebnis führen, ermöglicht die Version mit der benutzerdefinierten Richtlinie die Ausführung der Aufgabe zur Ausgabe der Statusanzeige mit erhöhter Priorität, das heißt mit höherer Reaktionsgeschwindigkeit.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `scheduler-policy.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Scheduler-policy.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)   
 [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

