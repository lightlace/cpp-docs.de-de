---
title: 'Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread'
ms.date: 11/04/2016
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 85622b68f94342ece2c9fc666b9ff6d515cfe10b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472436"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>Exemplarische Vorgehensweise: Entfernen von Arbeit aus einem Benutzeroberflächenthread

Dieses Dokument veranschaulicht, wie die Concurrency Runtime verwenden, um die Arbeit zu verschieben, die von der Benutzeroberfläche (UI) Thread in einer Microsoft Foundation Classes (MFC)-Anwendung auf einem Arbeitsthread ausgeführt wird. In diesem Dokument wird veranschaulicht, wie die Leistung eines langwierigen Zeichenvorgangs zu verbessern.

Entfernen von Arbeit aus dem UI-Thread durch Auslagern von blockiervorgängen ist, kann z. B. zeichnen, um die Anzahl der Arbeitsthreads die Reaktionsfähigkeit Ihrer Anwendung verbessern. In dieser exemplarischen Vorgehensweise verwendet eine zeichnen-Routine, die der Mandelbrotfraktal zur Veranschaulichung eines längeren blockierenden Vorgangs generiert. Die Generierung der Mandelbrotfraktal ist auch ein guter Kandidat für die Parallelisierung, da die Berechnung der einzelnen Pixel von allen anderen Berechnungen unabhängig ist.

## <a name="prerequisites"></a>Vorraussetzungen

Lesen Sie sich folgende Themen durch, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:

- [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)

- [Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)

- [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)

- [Abbruch in der PPL](cancellation-in-the-ppl.md)

Außerdem wird empfohlen, dass Sie die Grundlagen der Entwicklung von MFC-Anwendungen und GDI + verstehen, bevor Sie in dieser exemplarischen Vorgehensweise beginnen. Weitere Informationen über MFC finden Sie unter [MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md). Weitere Informationen zu GDI +, finden Sie unter [GDI +](https://msdn.microsoft.com/library/windows/desktop/ms533798).

##  <a name="top"></a> Abschnitte

Diese exemplarische Vorgehensweise enthält folgende Abschnitte:

- [Erstellen der Mfc_anwendung](#application)

- [Implementieren die serielle Version der Mandelbrot-Anwendung](#serial)

- [Entfernen von Arbeit aus dem UI-Thread](#removing-work)

- [Verbessern der Leistung zeichnen](#performance)

- [Hinzufügen von Unterstützung für Abbrüche](#cancellation)

##  <a name="application"></a> Erstellen der Mfc_anwendung

Dieser Abschnitt beschreibt, wie Sie die grundlegenden MFC-Anwendung zu erstellen.

### <a name="to-create-a-visual-c-mfc-application"></a>Zum Erstellen einer Visual C++-MFC-Anwendung

1. Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.

1. In der **neues Projekt** Dialogfeld die **installierte Vorlagen** wählen Sie im Bereich **Visual C++**, und klicken Sie dann in der **Vorlagen** wählen Sie im Bereich **MFC-Anwendung**. Geben Sie einen Namen für das Projekt, z. B. `Mandelbrot`, und klicken Sie dann auf **OK** zum Anzeigen der **MFS-Anwendungsassistenten**.

1. In der **Anwendungstyp** wählen Sie im Bereich **einzelnes Dokument**. Sicherstellen, dass die **Unterstützung für die Dokument-/Ansicht** Kontrollkästchen deaktiviert ist.

1. Klicken Sie auf **Fertig stellen** zum Erstellen des Projekts, und schließen Sie die **MFS-Anwendungsassistenten**.

   Überprüfen Sie, ob die Anwendung erfolgreich erstellt wurde, indem Sie sie erstellen und ausführen. Erstellen Sie die Anwendung, auf die **erstellen** im Menü klicken Sie auf **Projektmappe**. Wenn die Anwendung erfolgreich erstellt wurde, führen Sie die Anwendung, indem Sie auf **Debuggen starten** auf die **Debuggen** Menü.

##  <a name="serial"></a> Implementieren die serielle Version der Mandelbrot-Anwendung

Dieser Abschnitt beschreibt, wie die Mandelbrotfraktal gezeichnet wird. Diese Version zeichnet die Mandelbrotfraktal in eine GDI + [Bitmap](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) Objekt aus, und klicken Sie dann den Inhalt dieser Bitmap für das Clientfenster kopiert.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Um die serielle Version der Mandelbrot-Anwendung zu implementieren.

1. Fügen Sie in "stdafx.h" die folgenden `#include` Richtlinie:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. In ChildView.h nach der `pragma` -Direktive definieren die `BitmapPtr` Typ. Die `BitmapPtr` Typ ermöglicht, einen Zeiger auf eine `Bitmap` Objekt, das von mehreren Komponenten gemeinsam genutzt werden. Die `Bitmap` Objekt gelöscht, wenn es nicht mehr von keiner Komponente verwiesen wird.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. Fügen Sie den folgenden Code hinzu, in ChildView.h der `protected` Teil der `CChildView` Klasse:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. Klicken Sie in ChildView.cpp kommentieren Sie aus oder entfernen Sie die folgenden Zeilen.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   In Debug-Builds: Dieser Schritt verhindert, die Anwendung die `DEBUG_NEW` Zuweisung, die mit GDI + nicht kompatibel ist.

1. Fügen Sie in ChildView.cpp eine `using` die Anweisung die `Gdiplus` Namespace.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. Fügen Sie den folgenden Code zum Konstruktor und Destruktor, der die `CChildView` Klasse zu initialisieren und Herunterfahren von GDI +.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. Implementieren Sie die `CChildView::DrawMandelbrot`-Methode. Diese Methode die Mandelbrotfraktal zeichnet, mit dem angegebenen `Bitmap` Objekt.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. Implementieren Sie die `CChildView::OnPaint`-Methode. Diese Methode ruft `CChildView::DrawMandelbrot` und kopiert dann den Inhalt der `Bitmap` Objekt an das Fenster.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

9. Stellen Sie sicher, dass die Anwendung erfolgreich aktualisiert wurde, indem Sie erstellen und ausführen.

Die folgende Abbildung zeigt die Ergebnisse der Mandelbrot-Anwendung.

![Die Mandelbrot-Anwendung](../../parallel/concrt/media/mandelbrot.png "Mandelbrot")

Da die Berechnung für jedes Pixel rechenintensiv ist, kann nicht im UI-Thread zusätzliche Nachrichten verarbeiten, bis die gesamte Berechnung abgeschlossen ist. Dies konnte die Reaktionszeit der Anwendung verringern. Allerdings können Sie dieses Problem reduzieren, durch das Entfernen von Arbeit aus dem UI-Thread.

[[Nach oben](#top)]

##  <a name="removing-work"></a> Entfernen von Arbeit aus dem UI-Thread

In diesem Abschnitt veranschaulicht, wie die Zeichnen Arbeit vom UI-Thread in der Mandelbrot-Anwendung zu entfernen. Durch Zeichnen Arbeit vom UI-Thread auf einen Arbeitsthread verschoben wurde, kann der UI-Thread Nachrichten verarbeiten, da der Arbeitsthread im Hintergrund wird das Bild generiert.

Die Concurrency Runtime bietet drei Möglichkeiten zum Ausführen von Aufgaben: [Aufgabengruppen](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [asynchrone Agents](../../parallel/concrt/asynchronous-agents.md), und [einfache Aufgaben](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Auch wenn Sie eine der folgenden Mechanismen zum Entfernen von Arbeit aus dem UI-Thread verwenden können, um dieses Beispiel verwendet eine [Concurrency:: task_group](reference/task-group-class.md) Objekt, da der Aufgabengruppen Abbruch unterstützen. In dieser exemplarischen Vorgehensweise verwendet später Abbruch der verbleibende Arbeitsaufwand zu reduzieren, die ausgeführt wird, wenn der Client-Fenster geändert wird und Cleanup auszuführen, wenn das Fenster zerstört wird.

Dieses Beispiel verwendet außerdem eine [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) Objekt, das im UI-Thread und der Arbeitsthread für die Kommunikation untereinander zu ermöglichen. Nachdem der Arbeitsthread das Image erstellt wird, sendet er einen Zeiger auf die `Bitmap` -Objekt an die `unbounded_buffer` Objekt aus, und klicken Sie dann sendet eine Paint-Meldung an den UI-Thread. Der UI-Thread empfängt dann von der `unbounded_buffer` Objekt die `Bitmap` Objekt aus, und zeichnet es auf dem Client-Fenster.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>So entfernen Sie die Zeichnung Arbeit vom UI-thread

1. Fügen Sie in "stdafx.h" die folgenden `#include` Anweisungen:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. Fügen Sie in ChildView.h `task_group` und `unbounded_buffer` Membervariablen des Typs der `protected` Teil der `CChildView` Klasse. Die `task_group` -Objekt enthält die Aufgaben, die Zeichnung; führen Sie die `unbounded_buffer` -Objekt enthält die abgeschlossenen Mandelbrot-Images.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. Fügen Sie in ChildView.cpp eine `using` die Anweisung die `concurrency` Namespace.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. In der `CChildView::DrawMandelbrot` Methode, nach dem Aufruf von `Bitmap::UnlockBits`, rufen Sie die [Concurrency:: Send](reference/concurrency-namespace-functions.md#send) Funktion übergeben die `Bitmap` Objekt an den UI-Thread. Klicken Sie dann veröffentlichen Sie eine Paint-Meldung an den UI-Thread aus, und das den Clientbereich ungültig.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. Update der `CChildView::OnPaint` Methode, um die aktualisierte empfangen `Bitmap` Objekt aus, und zeichnen Sie das Bild an das Clientfenster.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   Die `CChildView::OnPaint` Methode erstellt eine Aufgabe, um die Mandelbrot-Image zu generieren, wenn noch nicht in den Nachrichtenpuffer vorhanden ist. Der der Nachrichtenpuffer enthält keine `Bitmap` Objekt in Fällen, z. B. die anfängliche Paint-Meldung, und wenn ein anderes Fenster vor der Client-Fenster verschoben wird.

1. Stellen Sie sicher, dass die Anwendung erfolgreich aktualisiert wurde, indem Sie erstellen und ausführen.

Die Benutzeroberfläche ist nun reaktionsfähiger, da die Zeichnen Arbeit im Hintergrund ausgeführt wird.

[[Nach oben](#top)]

##  <a name="performance"></a> Verbessern der Leistung zeichnen

Die Generierung der Mandelbrotfraktal ist ein guter Kandidat für die Parallelisierung, da die Berechnung der einzelnen Pixel unabhängig von allen anderen Berechnungen ist. Um das Zeichnen Verfahren zu parallelisieren, konvertieren Sie die äußere `for` wurde eine Schleife in der `CChildView::DrawMandelbrot` Methode, um einen Aufruf der [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus wie folgt.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

Da die Berechnung der einzelnen Bitmap-Elemente unabhängig ist, müssen Sie nicht die Zeichenoperationen zu synchronisieren, die auf den Bitmapspeicher zugreifen. Dadurch wird die Leistung als die Anzahl der verfügbaren Prozessoren skaliert.

[[Nach oben](#top)]

##  <a name="cancellation"></a> Hinzufügen von Unterstützung für Abbrüche

In diesem Abschnitt wird beschrieben, wie der Größenänderung behandelt und wie Sie alle aktiven Zeichenaufgaben Abbrechen, wenn das Fenster zerstört wird.

Das Dokument [Abbruch in der PPL](cancellation-in-the-ppl.md) wird erläutert, wie Abbrüche in der Runtime funktionieren. Abbruch ist kooperativ. aus diesem Grund tritt er nicht sofort auf. Um eine abgebrochene Aufgabe zu beenden, löst die Runtime eine interne Ausnahme bei einem nachfolgenden Aufruf von der Aufgabe in der Laufzeit. Der vorherige Abschnitt zeigt, wie Sie mit der `parallel_for` Algorithmus zur Verbesserung der Leistung des Tasks "Zeichnen". Der Aufruf von `parallel_for` ermöglicht der Laufzeit, die Tasks beendet und Abbrüche funktionieren.

### <a name="cancelling-active-tasks"></a>Abbrechen von aktiven Aufgaben

Die Mandelbrot-Anwendung erstellt `Bitmap` Objekte, deren Dimensionen, die Größe des Clientfensters entsprechen. Jedes Mal, wenn das Clientfenster Größe geändert wird, erstellt die Anwendung eine zusätzliche Hintergrundaufgabe um ein Bild für die neue Fenstergröße zu generieren. Die Anwendung erfordert keine diese intermediate-Images. nur das Image erforderlich für die Größe des letzten Fensters. Um die Anwendung von der Durchführung dieser zusätzliche Arbeitsaufwand zu verhindern, können Sie Abbrechen, alle aktiven Zeichenaufgaben in der Message-Handler für die `WM_SIZE` und `WM_SIZING` Nachrichten und zeichnen Sie dann erneut planen funktionieren nach der Größe des Fensters geändert wird.

Um die aktive Zeichenaufgaben Abbrechen, wenn die Größe des Fensters geändert wird, ruft die Anwendung die [task_group](reference/task-group-class.md#cancel) -Methode in der der Handler für die `WM_SIZING` und `WM_SIZE` Nachrichten. Der Handler für die `WM_SIZE` Nachricht auch Aufrufe der [Concurrency:: task_group::](reference/task-group-class.md#wait) Methode zu warten, bis alle aktiven Aufgaben zum Abschließen und dann erneut plant die Zeichnen Aufgabe für die Größe des aktuellen Fensters.

Wenn der Client-Fenster zerstört wird, ist es empfiehlt sich, alle aktiven Zeichenaufgaben abzubrechen. Alle aktiven Zeichenaufgaben Abbrechen, wird sichergestellt, dass es sich bei Arbeitsthreads keine buchen Nachrichten an den UI-Thread nach dem das Clientfenster zerstört wird. Bricht alle aktiven Zeichenaufgaben im Ereignishandler für die Anwendung die `WM_DESTROY` Nachricht.

### <a name="responding-to-cancellation"></a>Auf den Abbruch reagieren

Die `CChildView::DrawMandelbrot` -Methode, die die Zeichnen Aufgabe ausführt, muss auf den Abbruch reagieren. Da die Common Language Runtime zum Abbrechen von Aufgaben, für die Ausnahmebehandlung verwendet die `CChildView::DrawMandelbrot` Methode muss einen ausnahmesicher-Mechanismus verwenden, um sicherzustellen, dass alle Ressourcen ordnungsgemäß bereinigt werden. Dieses Beispiel verwendet die *Resource Acquisition Is Initialization* (RAII)-Muster können Sie sicherstellen, dass die Bitmapbits entsperrt werden, wenn die Aufgabe abgebrochen wird.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Zum Hinzufügen der Unterstützung für den Abbruch in der Mandelbrot-Anwendung

1. In ChildView.h in die `protected` Teil der `CChildView` -Klasse verwenden, fügen Sie die Deklarationen für die `OnSize`, `OnSizing`, und `OnDestroy` Nachrichtenfunktionen Zuordnung.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. In ChildView.cpp ändern Sie die meldungszuordnung, um Handler für enthalten die `WM_SIZE`, `WM_SIZING`, und `WM_DESTROY` Nachrichten.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. Implementieren Sie die `CChildView::OnSizing`-Methode. Diese Methode bricht alle vorhandenen Zeichenaufgaben ab.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. Implementieren Sie die `CChildView::OnSize`-Methode. Diese Methode bricht alle vorhandenen Zeichenaufgaben ab und erstellt eine neue Zeichnung Aufgabe für die Fenstergröße des aktualisierten Clients.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. Implementieren Sie die `CChildView::OnDestroy`-Methode. Diese Methode bricht alle vorhandenen Zeichenaufgaben ab.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. Definieren Sie in ChildView.cpp der `scope_guard` -Klasse, die das RAII-Muster implementiert.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. Fügen Sie den folgenden Code der `CChildView::DrawMandelbrot` Methode nach dem Aufruf von `Bitmap::LockBits`:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   Dieser Code verwaltet den Abbruch durch das Erstellen einer `scope_guard` Objekt. Wenn das Objekt den Gültigkeitsbereich verlässt, entsperrt den Bitmap-Bits.

1. Ändern Sie das Ende der `CChildView::DrawMandelbrot` Methode zum Schließen der `scope_guard` Objekt, nachdem die Bitmapbits nicht gesperrt sind, aber vor dem Senden von Nachrichten an den UI-Thread. Dadurch wird sichergestellt, dass der UI-Thread nicht aktualisiert werden, bevor der Bitmap-Bits entsperrt werden.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. Stellen Sie sicher, dass die Anwendung erfolgreich aktualisiert wurde, indem Sie erstellen und ausführen.

Wenn Sie die Größe des Fensters ändern, erfolgt nur für die Größe des letzten Fensters zeichnen Arbeit. Alle aktiven Zeichenaufgaben werden auch abgebrochen, wenn das Fenster zerstört wird.

[[Nach oben](#top)]

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Funktionen zum Übergeben von Nachrichten](../../parallel/concrt/message-passing-functions.md)<br/>
[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)
