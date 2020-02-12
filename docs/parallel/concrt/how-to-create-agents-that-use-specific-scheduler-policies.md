---
title: 'Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden'
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies, agents [Concurrency Runtime]
- creating agents that use specific policies [Concurrency Runtime]
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
ms.openlocfilehash: ece6b113e3fe10c2c3179517f73137df281acf87
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141736"
---
# <a name="how-to-create-agents-that-use-specific-scheduler-policies"></a>Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden

Ein Agent ist eine Anwendungskomponente, die asynchron mit anderen Komponenten arbeitet, um größere Rechenaufgaben zu lösen. Ein Agent hat in der Regel einen festgelegten Lebenszyklus und behält den Zustand bei.

Dabei kann jeder Agent eigene Anwendungsanforderungen haben. Ein Agent, der eine Benutzerinteraktion ermöglicht (Abrufen einer Eingabe oder Anzeigen einer Ausgabe), benötigt z. B. für Computerressourcen möglicherweise Zugriff mit höherer Priorität. Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet. In diesem Thema wird die Erstellung von Agents beschrieben, die bestimmte Planerrichtlinien verwenden.

Ein einfaches Beispiel, in dem benutzerdefinierte planerrichtlinien zusammen mit asynchronen Nachrichten Blöcken verwendet werden, finden Sie unter Gewusst [wie: Angeben spezifischer Scheduler-Richtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

In diesem Thema werden mithilfe der Funktionalität der Asynchronous Agents Library Arbeiten ausgeführt, z. B. mithilfe von Agents, Nachrichtenblöcken und Nachrichtenübergabefunktionen. Weitere Informationen zur Asynchronous Agents Library finden Sie unter [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Klassen definiert, die von " [parallelcurrency:: Agent](../../parallel/concrt/reference/agent-class.md): `permutor`" und "`printer`" abgeleitet werden. Die `permutor`-Klasse berechnet alle Permutationen einer gegebenen Eingabezeichenfolge. Die `printer`-Klasse gibt Statusmeldungen an der Konsole aus. Die `permutor`-Klasse führt einen rechenintensiven Vorgang aus, der möglicherweise alle verfügbaren Computerressourcen erfordert. Für eine sinnvolle Nutzung muss die `printer`-Klasse alle Statusmeldungen zeitnah ausgeben.

Um dem `printer`-Klasse einen angemessenen Zugriff auf Computerressourcen zu ermöglichen, werden in diesem Beispiel die in Gewusst [wie: Verwalten einer planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) beschriebenen Schritte verwendet, um eine planerinstanz zu erstellen, die über eine benutzerdefinierte Richtlinie verfügt. Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.

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

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `permute-strings.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc permute-Strings. cpp**

## <a name="see-also"></a>Weitere Informationen

[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)<br/>
[Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)
