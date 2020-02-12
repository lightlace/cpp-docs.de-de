---
title: 'Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse'
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 5075052592993f413290242e70206b1e227064aa
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141904"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Gewusst wie: Implementieren einer kooperativen Semaphore mithilfe der Context-Klasse

In diesem Thema wird erläutert, wie die concurrency::Context-Klasse verwendet wird, um eine kooperative Semaphorenklasse zu implementieren.

## <a name="remarks"></a>Bemerkungen

Mit der `Context`-Klasse können Sie den aktuellen Ausführungskontext blockieren oder zurückhalten. Das Blockieren oder Zurückhalten des aktuellen Kontexts ist nützlich, wenn der aktuelle Kontext nicht fortfahren kann, da eine Ressource nicht verfügbar ist. Ein *Semaphor* ist ein Beispiel für eine Situation, in der der aktuelle Ausführungs Kontext warten muss, bis eine Ressource verfügbar wird. Eine Semaphore ist wie ein kritisches Abschnittsobjekt ein Synchronisierungsobjekt, das dem Code in einem Kontext ermöglicht, exklusiv auf eine Ressource zuzugreifen. Im Gegensatz zu einem kritischen Abschnittsobjekt ermöglicht eine Semaphore jedoch mehr als einem Kontext, gleichzeitig auf die Ressource zuzugreifen. Wenn die maximale Anzahl von Kontexten eine Semaphorensperre hat, muss jeder zusätzliche Kontext warten, bis ein anderer Kontext die Sperre aufhebt.

### <a name="to-implement-the-semaphore-class"></a>So implementieren Sie die Semaphorenklasse

1. Deklarieren Sie eine Klasse mit dem Namen `semaphore`. Fügen Sie der Klasse einen `public`-Abschnitt und einen `private`-Abschnitt hinzu.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. Deklarieren Sie im `private` Abschnitt der `semaphore`-Klasse eine [Std:: Atomic](../../standard-library/atomic-structure.md) -Variable, die die Anzahl der Semaphor und ein [parallelcurrency:: Concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) -Objekt enthält, das die Kontexte enthält, die auf das Abrufen des Semaphors warten müssen.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse den Konstruktor. Der Konstruktor akzeptiert einen `long long`-Wert, der die maximale Anzahl von Kontexten angibt, die gleichzeitig über die Sperre verfügen können.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse die `acquire`-Methode. Diese Methode dekrementiert die Semaphorenanzahl als atomaren Vorgang. Wenn die Anzahl der Semaphor negativ wird, fügen Sie den aktuellen Kontext am Ende der Warteschlange hinzu, und wenden Sie die Methode " [parallelcurrency:: context:: Block](reference/context-class.md#block) " an, um den aktuellen Kontext zu blockieren.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. Implementieren Sie im `public`-Abschnitt der `semaphore`-Klasse die `release`-Methode. Diese Methode inkrementiert die Semaphorenanzahl als atomaren Vorgang. Wenn die Semaphorenanzahl vor dem Inkrementieren negativ ist, gibt es mindestens einen Kontext, der auf die Sperre wartet. Entsperren Sie in diesem Fall den Kontext, der sich am Anfang der Warteschlange befindet.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Beispiel

Die `semaphore`-Klasse in diesem Beispiel verhält sich kooperativ, da die `Context::Block`-Methode und `Context::Yield`-Methode die Ausführung zurückhalten, damit die Laufzeit andere Aufgaben ausführen kann.

Die `acquire`-Methode dekrementiert den Zähler, es kann jedoch sein, dass sie das Hinzufügen des Kontexts zur Warteschlange noch nicht abgeschlossen hat, bevor ein anderer Kontext die `release`-Methode aufruft. Um dies zu berücksichtigen, verwendet die `release`-Methode eine Spin-Schleife, die die [parallelcurrency:: context:: Yield](reference/context-class.md#yield) -Methode aufruft, um zu warten, bis die `acquire` Methode das Hinzufügen des Kontexts abgeschlossen hat.

Die `release`-Methode kann die `Context::Unblock`-Methode aufrufen, bevor die `acquire`-Methode die `Context::Block`-Methode aufruft. Sie müssen keinen Schutz vor dieser Racebedingung implementieren, da die Laufzeit diesen Methoden ermöglicht, in beliebiger Reihenfolge aufgerufen zu werden. Wenn die `release`-Methode `Context::Unblock` aufruft, bevor die `acquire`-Methode `Context::Block` für den gleichen Kontext aufruft, bleibt dieser Kontext weiterhin unblockiert. Die Laufzeit erfordert nur, dass für jeden Aufruf von `Context::Block` ein entsprechender Aufruf von `Context::Unblock` vorhanden ist.

Im folgenden Beispiel wird die vollständige `semaphore`-Klasse dargestellt. Die `wmain`-Funktion zeigt die grundlegende Verwendung dieser Klasse. Die `wmain`-Funktion verwendet den " [parallelcurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) "-Algorithmus, um mehrere Tasks zu erstellen, die Zugriff auf das Semaphor benötigen. Da drei Threads jederzeit über die Sperre verfügen können, müssen einige Aufgaben warten, bis eine andere Aufgabe abgeschlossen ist und die Sperre freigibt.

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

Weitere Informationen zum `concurrent_queue`-Klasse finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md). Weitere Informationen zum `parallel_for` Algorithmus finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `cooperative-semaphore.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc Cooperative-Semaphore. cpp**

## <a name="robust-programming"></a>Robuste Programmierung

Mit dem *Resource Acquisition Is Initialization* (RAII)-Muster können Sie den Zugriff auf ein `semaphore` Objekt auf einen bestimmten Bereich beschränken. Unter dem RAII-Muster wird dem Stapel eine Datenstruktur zugeordnet. Diese Datenstruktur initialisiert oder ruft eine Ressource ab, wenn sie erstellt wird, und zerstört oder gibt diese Ressource frei, wenn die Datenstruktur zerstört wird. Das RAII-Muster garantiert, dass der Destruktor aufgerufen wird, bevor der einschließende Bereich beendet wird. Daher wird die Ressource ordnungsgemäß verwaltet, wenn eine Ausnahme ausgelöst wird, oder wenn eine Funktion mehrere `return`-Anweisungen enthält.

Im folgenden Beispiel wird eine Klasse mit dem Namen `scoped_lock` definiert, die im `public`-Abschnitt der `semaphore`-Klasse definiert ist. Die `scoped_lock`-Klasse ähnelt der Klasse [parallelcurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) und [parallelcurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) . Der Konstruktor der `semaphore::scoped_lock`-Klasse erhält Zugriff auf das angegebene `semaphore`-Objekt, und der Destruktor gibt den Zugriff auf dieses Objekt frei.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
Im folgenden Beispiel wird der Text der Arbeitsfunktion geändert, die an den `parallel_for`-Algorithmus übergeben wird, damit RAII verwendet wird um sicherzustellen, dass die Semaphore vor der Rückkehr der Funktion freigegeben wird. Durch diese Methode wird sichergestellt, dass die Arbeitsfunktion sicher vor Ausnahmen ist.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>Weitere Informationen

[Kontext](../../parallel/concrt/contexts.md)<br/>
[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)
