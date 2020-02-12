---
title: 'Gewusst wie: Angeben von bestimmten Planerrichtlinien'
ms.date: 11/04/2016
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
ms.openlocfilehash: bd5edfbdf6b0fda9c7e327dab9538bbf6b5e4b12
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142451"
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Gewusst wie: Angeben von bestimmten Planerrichtlinien

Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet. In diesem Thema wird veranschaulicht, wie eine Planerrichtlinie verwendet wird, um die Threadpriorität einer Aufgabe zu erhöhen, die eine Statusanzeige an die Konsole ausgibt.

Ein Beispiel, in dem benutzerdefinierte planerrichtlinien zusammen mit asynchronen Agents verwendet werden, finden Sie unter Gewusst [wie: Erstellen von Agents, die bestimmte planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Aufgaben parallel ausgeführt. Mit der ersten Aufgabe wird<sup>die n-</sup> te "fbonacci"-Zahl berechnet. Die zweite Aufgabe gibt eine Statusanzeige an die Konsole aus.

Die erste Aufgabe verwendet die rekursive Zerlegung zur Berechnung der Fibonacci-Zahl. Das heißt, jede Aufgabe erstellt rekursiv Unteraufgaben zur Berechnung des Gesamtergebnisses. Es kann vorkommen, dass eine Aufgabe, die rekursive Zerlegung verwendet, alle verfügbaren Ressourcen belegt, die anderen Aufgaben dann fehlen. In diesem Beispiel kann die Aufgabe zur Ausgabe der Statusanzeige möglicherweise nicht rechtzeitig auf Computerressourcen zugreifen.

Zum Bereitstellen der Aufgabe, die einen Status Nachrichten Zugriff auf Computerressourcen ausgibt, werden in diesem Beispiel die in Gewusst [wie: Verwalten einer planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) beschriebenen Schritte verwendet, um eine planerinstanz zu erstellen, die über eine benutzerdefinierte Richtlinie verfügt. Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.

In diesem Beispiel werden die Statusanzeige mithilfe der Klassen " [parallelcurrency:: Call"](../../parallel/concrt/reference/call-class.md) und " [parallelcurrency:: Timer](../../parallel/concrt/reference/timer-class.md) " gedruckt. Diese Klassen verfügen über Versionen ihrer Konstruktoren, die einen Verweis auf ein [parallelcurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) -Objekt akzeptieren, das Sie plant. In unserem Beispiel wird der Standardplaner zur Planung der Aufgabe verwendet, die die Fibonacci-Zahl berechnet, und die Planerinstanz wird zur Planung der Aufgabe verwendet, die die Statusanzeige ausgibt.

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

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `scheduler-policy.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc Scheduler-Policy. cpp**

## <a name="see-also"></a>Weitere Informationen

[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)<br/>
[Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
