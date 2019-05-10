---
title: 'Exemplarische Vorgehensweise: Implementieren von Futures'
ms.date: 04/25/2019
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 00ad8bbe6f950ad531bad751686393dce66643bb
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857066"
---
# <a name="walkthrough-implementing-futures"></a>Exemplarische Vorgehensweise: Implementieren von Futures

In diesem Thema erfahren Sie, wie Sie Futures in Ihre Anwendung implementieren. Es wird veranschaulicht, wie Sie die vorhandenen Funktionen in der Concurrency Runtime kombinieren können, um mehr Funktionalität zu erzielen.

> [!IMPORTANT]
>  In diesem Thema wird das Konzept von Futures zu Demonstrationszwecken veranschaulicht. Wir empfehlen die Verwendung [Std:: Future](../../standard-library/future-class.md) oder [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) Wenn gewünscht, eine asynchrone Aufgabe, die einen Wert zur späteren Verwendung berechnet.

Ein *Aufgabe* ist eine Berechnung, die in weitere, differenziertere Berechnungen unterteilt werden kann. Ein *zukünftige* ist eine asynchrone Aufgabe, die einen Wert zur späteren Verwendung berechnet.

Zur Implementierung von Futures wird in diesem Thema die `async_future`-Klasse definiert. Die `async_future` Klasse verwendet die folgenden Komponenten der Concurrency Runtime: die [Concurrency:: task_group](reference/task-group-class.md) Klasse und die [Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) Klasse. Die `async_future`-Klasse verwendet die `task_group`-Klasse zur asynchronen Berechnung eines Werts und die `single_assignment`-Klasse zum Speichern des Ergebnisses. Der Konstruktor der `async_future`-Klasse akzeptiert eine Arbeitsfunktion, die das Ergebnis berechnet, das mit der `get`-Methode abgerufen wird.

### <a name="to-implement-the-asyncfuture-class"></a>So implementieren Sie die async_future-Klasse

1. Deklarieren Sie eine Vorlagenklasse mit dem Namen `async_future`, die auf der Grundlage des Typs der resultierenden Berechnung parametrisiert wird. Fügen Sie der Klasse einen `public`-Abschnitt und einen `private`-Abschnitt hinzu.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. Deklarieren Sie im `private`-Abschnitt der `async_future`-Klasse ein `task_group`-Datenmember und ein `single_assignment`-Datenmember.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `async_future`-Klasse den Konstruktor. Der Konstruktor ist eine Vorlage, die auf Grundlage der Arbeitsfunktion, die zur Berechnung des Ergebnisses dient, parametrisiert wird. Der Konstruktor führt die Arbeitsfunktion in asynchron aus der `task_group` -Datenmember und verwendet die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion, um das Ergebnis, das Schreiben der `single_assignment` -Datenmember.

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `async_future`-Klasse den Destruktor. Der Destruktor wartet auf das Beenden der Aufgabe.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `async_future`-Klasse die `get`-Methode. Diese Methode verwendet die [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) Funktion, um das Ergebnis der Arbeitsfunktion abzurufen.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt die vollständige `async_future`-Klasse mit einer Verwendungsmöglichkeit. Die `wmain` -Funktion erstellt eine std::[Vektor](../../standard-library/vector-class.md) Objekt, das 10.000 zufällige Ganzzahlwerte enthält. Anschließend werden mithilfe von `async_future`-Objekten der kleinste und der größte Wert im `vector`-Objekt gesucht.

### <a name="code"></a>Code

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>Kommentare

Dieses Beispiel erzeugt die folgende Ausgabe:

```Output
smallest: 0
largest:  9999
average:  4981
```

Im Beispiel werden die Ergebnisse der Berechnung mit der `async_future::get`-Methode abgerufen. Die `async_future::get`-Methode wartet, bis die Berechnung beendet ist.

## <a name="robust-programming"></a>Stabile Programmierung

Erweitern der `async_future` Klasse zum Behandeln von Ausnahmen, die von der Arbeitsfunktion ausgelöst werden, Ändern der `async_future::get` aufzurufende Methode der [Concurrency:: task_group::](reference/task-group-class.md#wait) Methode. Die `task_group::wait`-Methode löst alle von der Arbeitsfunktion generierten Ausnahmen aus.

Das folgende Beispiel zeigt die geänderte Version der `async_future`-Klasse. Die `wmain` Funktion verwendet einen `try` - `catch` Block, um das Ergebnis des der `async_future` Objekt oder den Wert der Ausnahme, die von der Arbeitsfunktion generiert wird, zu drucken.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

Dieses Beispiel erzeugt die folgende Ausgabe:

```Output
caught exception: error
```

Weitere Informationen über das Modell der Ausnahmebehandlung in der Concurrency Runtime finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `futures.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc futures.cpp**

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[task_group-Klasse](reference/task-group-class.md)<br/>
[single_assignment-Klasse](../../parallel/concrt/reference/single-assignment-class.md)
