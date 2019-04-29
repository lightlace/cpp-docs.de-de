---
title: 'Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse'
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 92f77fade972bff1528bc9a22416670354c70f34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366705"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Vorgehensweise: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse

In diesem Thema zeigt, wie die Concurrency:: Context-Klasse, die zum Implementieren einer kooperativen Semaphore-Klasse verwendet wird.

Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Das Blockieren oder Zurückhalten des aktuellen Kontexts ist nützlich, wenn der aktuelle Kontext nicht fortfahren kann, da eine Ressource nicht verfügbar ist. Ein *Semaphor* ist ein Beispiel für eine Situation, in dem der aktuelle Ausführungskontext warten muss, eine Ressource verfügbar wird. Eine Semaphore ist wie ein kritisches Abschnittsobjekt ein Synchronisierungsobjekt, das dem Code in einem Kontext ermöglicht, exklusiv auf eine Ressource zuzugreifen. Im Gegensatz zu einem kritischen Abschnittsobjekt ermöglicht eine Semaphore jedoch mehr als einem Kontext, gleichzeitig auf die Ressource zuzugreifen. Wenn die maximale Anzahl von Kontexten eine Semaphorensperre hat, muss jeder zusätzliche Kontext warten, bis ein anderer Kontext die Sperre aufhebt.

### <a name="to-implement-the-semaphore-class"></a>So implementieren Sie die Semaphorenklasse

1. Deklarieren Sie eine Klasse mit dem Namen `semaphore`. Fügen Sie der Klasse einen `public`-Abschnitt und einen `private`-Abschnitt hinzu.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. In der `private` Teil der `semaphore` Klasse, deklarieren Sie eine [Std:: Atomic](../../standard-library/atomic-structure.md) Variablen, die die Semaphorenanzahl enthält und eine [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) Objekt, das die Kontexte enthält die müssen mit dem das Abrufen der Semaphore warten.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse den Konstruktor. Der Konstruktor akzeptiert einen `long long`-Wert, der die maximale Anzahl von Kontexten angibt, die gleichzeitig über die Sperre verfügen können.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse die `acquire`-Methode. Diese Methode dekrementiert die Semaphorenanzahl als atomaren Vorgang. Wenn die Semaphorenanzahl negativ wird, fügen Sie den aktuellen Kontext am Ende der Warteschlange und rufen die [Concurrency::Context::Block](reference/context-class.md#block) Methode blockiert den aktuellen Kontext.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse die `release`-Methode. Diese Methode inkrementiert die Semaphorenanzahl als atomaren Vorgang. Wenn die Semaphorenanzahl vor dem Inkrementieren negativ ist, gibt es mindestens einen Kontext, der auf die Sperre wartet. Entsperren Sie in diesem Fall den Kontext, der sich am Anfang der Warteschlange befindet.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Beispiel

Die `semaphore`-Klasse in diesem Beispiel verhält sich kooperativ, da die `Context::Block`-Methode und `Context::Yield`-Methode die Ausführung zurückhalten, damit die Laufzeit andere Aufgaben ausführen kann.

Die `acquire`-Methode dekrementiert den Zähler, es kann jedoch sein, dass sie das Hinzufügen des Kontexts zur Warteschlange noch nicht abgeschlossen hat, bevor ein anderer Kontext die `release`-Methode aufruft. Um dies zu berücksichtigen die `release` Methode verwendet eine Spinschleife, die aufruft, die [yield](reference/context-class.md#yield) Methode warten, die `acquire` Methode zum Hinzufügen des Kontexts abgeschlossen.

Die `release`-Methode kann die `Context::Unblock`-Methode aufrufen, bevor die `acquire`-Methode die `Context::Block`-Methode aufruft. Sie müssen keinen Schutz vor dieser Racebedingung implementieren, da die Laufzeit diesen Methoden ermöglicht, in beliebiger Reihenfolge aufgerufen zu werden. Wenn die `release`-Methode `Context::Unblock` aufruft, bevor die `acquire`-Methode `Context::Block` für den gleichen Kontext aufruft, bleibt dieser Kontext weiterhin unblockiert. Die Laufzeit erfordert nur, dass für jeden Aufruf von `Context::Block` ein entsprechender Aufruf von `Context::Unblock` vorhanden ist.

Im folgenden Beispiel wird die vollständige `semaphore`-Klasse dargestellt. Die `wmain`-Funktion zeigt die grundlegende Verwendung dieser Klasse. Die `wmain` Funktion verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus, um verschiedene Aufgaben zu erstellen, die Zugriff auf die Semaphore benötigen. Da drei Threads jederzeit über die Sperre verfügen können, müssen einige Aufgaben warten, bis eine andere Aufgabe abgeschlossen ist und die Sperre freigibt.

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe.

```Output
In loop iteration 5...
In loop iteration 0...
In loop iteration 6...
In loop iteration 1...
In loop iteration 2...
In loop iteration 7...
In loop iteration 3...
In loop iteration 8...
In loop iteration 9...
In loop iteration 4...
```

Weitere Informationen zu den `concurrent_queue` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md). Weitere Informationen zu den `parallel_for` -Algorithmus finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `cooperative-semaphore.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Cooperative-semaphore.cpp**

## <a name="robust-programming"></a>Stabile Programmierung

Können Sie die *Resource Acquisition Is Initialization* (RAII)-Muster können Sie beschränken den Zugriff auf eine `semaphore` Objekt, das einem bestimmten Bereich. Unter dem RAII-Muster wird dem Stapel eine Datenstruktur zugeordnet. Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird. Das RAII-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird. Daher wird die Ressource ordnungsgemäß verwaltet, wenn eine Ausnahme ausgelöst wird, oder wenn eine Funktion mehrere `return`-Anweisungen enthält.

Im folgenden Beispiel wird eine Klasse mit dem Namen `scoped_lock` definiert, die im `public`-Abschnitt der `semaphore`-Klasse definiert ist. Die `scoped_lock` -Klasse ähnelt der [Concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) und [Concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) Klassen. Der Konstruktor der `semaphore::scoped_lock`-Klasse erhält Zugriff auf das angegebene `semaphore`-Objekt, und der Destruktor gibt den Zugriff auf dieses Objekt frei.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
Im folgenden Beispiel wird der Text der Arbeitsfunktion geändert, die an den `parallel_for`-Algorithmus übergeben wird, damit RAII verwendet wird um sicherzustellen, dass die Semaphore vor der Rückkehr der Funktion freigegeben wird. Durch diese Methode wird sichergestellt, dass die Arbeitsfunktion sicher vor Ausnahmen ist.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>Siehe auch

[Kontext](../../parallel/concrt/contexts.md)<br/>
[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)
