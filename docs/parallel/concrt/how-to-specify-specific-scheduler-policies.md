---
title: 'Vorgehensweise: Angeben von bestimmten Planerrichtlinien'
ms.date: 11/04/2016
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
ms.openlocfilehash: 3c03ef6661ebefe0bfe9fab62938ce9987a4bca1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410031"
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Vorgehensweise: Angeben von bestimmten Planerrichtlinien

Mithilfe von Planerrichtlinien können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet. In diesem Thema wird veranschaulicht, wie eine Planerrichtlinie verwendet wird, um die Threadpriorität einer Aufgabe zu erhöhen, die eine Statusanzeige an die Konsole ausgibt.

Ein Beispiel für die benutzerdefinierte Planerrichtlinien zusammen mit asynchronen Agents finden Sie unter [Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Aufgaben parallel ausgeführt. Die erste Aufgabe berechnet die<sup>th</sup> Fibonacci-Zahl. Die zweite Aufgabe gibt eine Statusanzeige an die Konsole aus.

Die erste Aufgabe verwendet die rekursive Zerlegung zur Berechnung der Fibonacci-Zahl. Das heißt, jede Aufgabe erstellt rekursiv Unteraufgaben zur Berechnung des Gesamtergebnisses. Es kann vorkommen, dass eine Aufgabe, die rekursive Zerlegung verwendet, alle verfügbaren Ressourcen belegt, die anderen Aufgaben dann fehlen. In diesem Beispiel kann die Aufgabe zur Ausgabe der Statusanzeige möglicherweise nicht rechtzeitig auf Computerressourcen zugreifen.

Um die Aufgabe zu ermöglichen, die einen Zugriff auf Computerressourcen ausgibt, verwendet in diesem Beispiel wird die Schritte, die im Abschnitt [Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) um eine Planerinstanz zu erstellen, eine benutzerdefinierte Richtlinie verfügt. Die benutzerdefinierte Richtlinie gibt die Threadpriorität für die höchste Prioritätsklasse an.

Dieses Beispiel verwendet die [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) und [Concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) Klassen, die Statusanzeige zu drucken. Diese Klassen weisen Konstruktorversionen auf, die einen Verweis auf eine [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) -Objekt, das sie plant. In unserem Beispiel wird der Standardplaner zur Planung der Aufgabe verwendet, die die Fibonacci-Zahl berechnet, und die Planerinstanz wird zur Planung der Aufgabe verwendet, die die Statusanzeige ausgibt.

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

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `scheduler-policy.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Scheduler-policy.cpp**

## <a name="see-also"></a>Siehe auch

[Planerrichtlinien](../../parallel/concrt/scheduler-policies.md)<br/>
[Vorgehensweise: Verwalten einer Planerinstanz](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
