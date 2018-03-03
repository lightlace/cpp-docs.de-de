---
title: 'Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden | Microsoft Docs'
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
- scheduler policies, agents [Concurrency Runtime]
- creating agents that use specific policies [Concurrency Runtime]
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d465b39e00bee0911fb5b04bbe60af68e1f296c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-agents-that-use-specific-scheduler-policies"></a>Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden
Ein Agent ist eine Anwendungskomponente, die asynchron mit anderen Komponenten arbeitet, um größere Rechenaufgaben zu lösen. Ein Agent hat in der Regel einen festgelegten Lebenszyklus und behält den Zustand bei.  
  
 Dabei kann jeder Agent eigene Anwendungsanforderungen haben. Ein Agent, der eine Benutzerinteraktion ermöglicht (Abrufen einer Eingabe oder Anzeigen einer Ausgabe), benötigt z. B. für Computerressourcen möglicherweise Zugriff mit höherer Priorität. Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet. In diesem Thema wird die Erstellung von Agents beschrieben, die bestimmte Planerrichtlinien verwenden.  
  
 Ein einfaches Beispiel, das benutzerdefinierte Planerrichtlinien zusammen mit asynchrone Meldungsblöcke verwendet, finden Sie unter [Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
 In diesem Thema werden mithilfe der Funktionalität der Asynchronous Agents Library Arbeiten ausgeführt, z. B. mithilfe von Agents, Nachrichtenblöcken und Nachrichtenübergabefunktionen. Weitere Informationen über die Asynchronous Agents Library finden Sie unter [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert zwei Klassen, die Ableitung [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md): `permutor` und `printer`. Die `permutor`-Klasse berechnet alle Permutationen einer gegebenen Eingabezeichenfolge. Die `printer`-Klasse gibt Statusmeldungen an der Konsole aus. Die `permutor`-Klasse führt einen rechenintensiven Vorgang aus, der möglicherweise alle verfügbaren Computerressourcen erfordert. Für eine sinnvolle Nutzung muss die `printer`-Klasse alle Statusmeldungen zeitnah ausgeben.  
  
 Bereitstellen der `printer` Klasse fairen Zugriff auf Computerressourcen, in diesem Beispiel verwendet die in beschriebenen Schritte [wie: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) um eine Planerinstanz zu erstellen, eine benutzerdefinierte Richtlinie verfügt. Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.  
  
 Um die Vorteile der Verwendung eines Planers mit einer benutzerdefinierten Richtlinie aufzuzeigen, wird in diesem Beispiel die gesamte Aufgabe zweimal ausgeführt. Dabei werden im Beispiel zunächst beide Aufgaben mithilfe des Standardplaners geplant. Anschließend werden mithilfe des Standardplaners das `permutor`-Objekt sowie ein Planer geplant, der eine benutzerdefinierte Richtlinie zum Planen des `printer`-Objekts enthält.  
  
 [!code-cpp[concrt-permute-strings#1](../../parallel/concrt/codesnippet/cpp/how-to-create-agents-that-use-specific-scheduler-policies_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
With default scheduler:  
Computing all permutations of 'Grapefruit'...  
100% complete...  
 
With higher context priority:  
Computing all permutations of 'Grapefruit'...  
100% complete...  
```  
  
 Beide Aufgabengruppen führen zum gleichen Ergebnis, aber nur die Version mit einer benutzerdefinierten Richtlinie ermöglicht die Ausführung des `printer`-Objekts mit einer höheren Priorität, sodass diese ein besseres Reaktionsverhalten aufweist.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `permute-strings.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / permute-strings.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 

